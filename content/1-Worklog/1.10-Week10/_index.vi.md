---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Mục tiêu tuần 10:

* Hoàn thiện API Gateway và tích hợp toàn bộ các microservices.
* Xây dựng rate limiting bằng Redis để kiểm soát lưu lượng theo userId.
* Hoàn thiện cơ chế sở hữu tiến trình thanh toán bằng processing token và lease.
* Bổ sung recovery worker, cấu hình load-test và đóng gói các service bằng Docker.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Xây dựng API Gateway bằng Spring Cloud Gateway<br>&emsp; + Cấu hình routing đến Account Service, Payment Service và Transaction Service<br>&emsp; + Chuẩn hóa health check và cấu hình theo profile dev/loadtest<br>&emsp; + Kiểm tra luồng request qua một cổng truy cập thống nhất | 22/06/2026 | 22/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Xây dựng cơ chế rate limiting bằng Redis<br>&emsp; + Sử dụng Token Bucket và Lua Script để xử lý nguyên tử<br>&emsp; + Giới hạn request theo userId từ header hoặc query parameter<br>&emsp; + Sử dụng IP làm khóa dự phòng<br>&emsp; + Trả về HTTP 429, Retry-After và thông tin quota còn lại | 23/06/2026 | 23/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Hoàn thiện cơ chế xử lý thanh toán đồng thời<br>&emsp; + Chuyển trạng thái PENDING sang PROCESSING bằng atomic claim<br>&emsp; + Gắn processingToken và leaseExpiresAt để xác định quyền xử lý<br>&emsp; + Chỉ tiến trình sở hữu token mới được gọi Account Service và cập nhật kết quả<br>&emsp; + Ngăn nhiều request đồng thời trừ tiền lặp | 24/06/2026 | 24/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Xây dựng cơ chế phục hồi thanh toán<br>&emsp; + Tạo Payment Recovery Worker quét các bản ghi PENDING hoặc PROCESSING bị treo<br>&emsp; + Cấu hình retry theo thời gian và giới hạn số lần xử lý<br>&emsp; + Bổ sung index phục vụ truy vấn recovery<br>&emsp; + Kiểm tra các trường hợp timeout và tiến trình mất quyền sở hữu | 25/06/2026 | 25/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Hoàn thiện dự án trước khi triển khai AWS<br>&emsp; + Cấu hình application-loadtest cho các service<br>&emsp; + Tối ưu logging, timeout và connection pool<br>&emsp; + Viết Dockerfile cho API Gateway, Account, Payment và Transaction Service<br>&emsp; + Build toàn bộ project và kiểm thử tích hợp trên môi trường Docker cục bộ | 26/06/2026 | 26/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 10:

* Hoàn thành API Gateway và định tuyến đến các service trong hệ thống.
* Triển khai Redis rate limiting theo userId bằng Lua Script và phản hồi HTTP 429 khi vượt ngưỡng.
* Hoàn thiện payment state machine với atomic claim, processing token và processing lease.
* Bổ sung Payment Recovery Worker để xử lý các giao dịch bị treo hoặc cần retry.
* Đóng gói các service bằng Docker và hoàn tất kiểm thử tích hợp trên môi trường cục bộ.
