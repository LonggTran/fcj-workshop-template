---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 10:

* Triển khai Payment Service với cơ chế idempotency và state machine bảo đảm một giao dịch không bị ghi nợ nhiều lần.
* Xử lý cạnh tranh giữa nhiều request đồng thời bằng Redis distributed lock và thao tác cập nhật trạng thái có điều kiện tại PostgreSQL.
* Tích hợp Payment Service với Account Service thông qua OpenFeign, Retry và Circuit Breaker.
* Hoàn thiện API Gateway và rate limiting theo `userId` bằng Redis Lua Script.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Xây dựng Payment Service và mô hình dữ liệu thanh toán<br>&emsp; + Tạo Payment entity, API tạo/tra cứu thanh toán và unique constraint cho `idempotencyKey`<br>&emsp; + Chuẩn hóa amount, currency, userId và accountId | 22/06/2026 | 22/06/2026 | Mã nguồn Payment Service |
| 3 | - Triển khai state machine cho thanh toán<br>&emsp; + Sử dụng chuỗi trạng thái `PENDING → PROCESSING → SUCCESS/FAILED`<br>&emsp; + Claim quyền xử lý bằng câu lệnh cập nhật có điều kiện khi trạng thái đang là PENDING<br>&emsp; + Chỉ tiến trình claim thành công mới được phép gọi Account Service để debit | 23/06/2026 | 23/06/2026 | Spring Data JPA và PostgreSQL |
| 4 | - Xây dựng Redis distributed lock và idempotency<br>&emsp; + Khóa theo `idempotencyKey` với TTL để ngăn nhiều request xử lý cùng lúc<br>&emsp; + Giải phóng lock an toàn bằng Lua Script so sánh lock value<br>&emsp; + Kiểm tra payload của request trùng lặp trước khi trả kết quả thanh toán hiện có | 24/06/2026 | 24/06/2026 | <https://redis.io/docs/latest/> |
| 5 | - Tích hợp Payment Service với Account Service<br>&emsp; + Gọi API debit bằng OpenFeign và truyền payment ID làm `transactionId`<br>&emsp; + Cấu hình timeout, Retry và Circuit Breaker bằng Resilience4j<br>&emsp; + Phân biệt lỗi nghiệp vụ với lỗi tạm thời để tránh đánh dấu FAILED sai khi Account Service chưa phản hồi | 25/06/2026 | 25/06/2026 | <https://resilience4j.readme.io/> |
| 6 | - Hoàn thiện API Gateway và cơ chế giới hạn lưu lượng<br>&emsp; + Định tuyến request đến Account, Payment và Transaction Service<br>&emsp; + Xây dựng Token Bucket rate limiter bằng Redis Lua Script<br>&emsp; + Giới hạn theo `X-User-Id` hoặc query parameter `userId`, fallback theo IP khi thiếu thông tin người dùng | 26/06/2026 | 26/06/2026 | Mã nguồn API Gateway |

### Kết quả đạt được tuần 10:

* Hoàn thiện Payment Service với idempotency nhiều lớp:
  * `idempotencyKey` được đặt unique tại PostgreSQL để ngăn tạo nhiều bản ghi thanh toán cho cùng một yêu cầu.
  * Redis distributed lock hạn chế nhiều tiến trình xử lý đồng thời trước khi thao tác với cơ sở dữ liệu.
  * Request trùng lặp có cùng dữ liệu nhận lại trạng thái thanh toán hiện tại; request dùng lại key với payload khác bị từ chối.

* Xây dựng state machine và cơ chế claim an toàn:
  * Thanh toán chỉ chuyển từ PENDING sang PROCESSING bằng cập nhật có điều kiện.
  * Chỉ request claim thành công mới gọi Account Service, giúp loại bỏ nguy cơ nhiều request cùng debit một tài khoản.
  * Việc hoàn tất chỉ cho phép chuyển từ PROCESSING sang SUCCESS hoặc FAILED, tránh ghi đè trạng thái cuối không hợp lệ.

* Tích hợp cơ chế chịu lỗi khi giao tiếp giữa các dịch vụ:
  * Payment Service gọi Account Service bằng OpenFeign với connect timeout và read timeout rõ ràng.
  * Retry chỉ áp dụng cho lỗi kết nối tạm thời; Circuit Breaker ngăn việc tiếp tục gọi khi tỷ lệ lỗi vượt ngưỡng.
  * Lỗi tạm thời giữ thanh toán ở PROCESSING để có thể kiểm tra hoặc xử lý tiếp, thay vì kết luận FAILED trong khi tài khoản có thể đã bị ghi nợ.

* Hoàn thiện API Gateway và rate limiting:
  * Toàn bộ API được truy cập qua một gateway thống nhất.
  * Lua Script thực hiện kiểm tra và cập nhật Token Bucket nguyên tử trên Redis.
  * Giới hạn lưu lượng được tách theo userId, trả mã HTTP 429 cùng các header về giới hạn, số token còn lại và thời gian thử lại.
