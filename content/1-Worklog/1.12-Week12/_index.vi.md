---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 12:

* Kiểm tra tích hợp end-to-end của hệ thống sau khi triển khai lên AWS.
* Xây dựng và thực thi các kịch bản kiểm thử chức năng, đồng thời, idempotency, rate limiting và khả năng chịu lỗi.
* Thực hiện kiểm thử tải để quan sát độ trễ, tỷ lệ lỗi, mức sử dụng tài nguyên và phản ứng của cơ chế tự động mở rộng.
* Tối ưu cấu hình, khắc phục lỗi, hoàn thiện tài liệu dự án và dọn dẹp tài nguyên AWS không còn sử dụng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Kiểm tra tích hợp sau triển khai<br>&emsp; + Kiểm tra health của API Gateway, ALB target group, ECS task, RDS và ElastiCache<br>&emsp; + Thực hiện luồng tạo tài khoản, truy vấn số dư, tạo thanh toán và tra cứu giao dịch qua endpoint chung<br>&emsp; + Kiểm tra log và traceId giữa các dịch vụ khi xảy ra lỗi | 06/07/2026 | 06/07/2026 | Hệ thống đã triển khai và CloudWatch Logs |
| 3 | - Kiểm thử idempotency và tính nhất quán<br>&emsp; + Gửi lặp lại cùng `idempotencyKey` cho Payment Service<br>&emsp; + Gửi đồng thời cùng `transactionId` đến Account Service<br>&emsp; + Kiểm tra yêu cầu trùng khớp không debit lần hai và payload khác bị trả về conflict | 07/07/2026 | 07/07/2026 | Kịch bản kiểm thử API của dự án |
| 4 | - Kiểm thử đồng thời, rate limiting và khả năng chịu lỗi<br>&emsp; + Gửi nhiều request song song đến API tạo thanh toán<br>&emsp; + Kiểm tra giới hạn theo userId và phản hồi HTTP 429 khi vượt ngưỡng<br>&emsp; + Mô phỏng Account Service chậm hoặc tạm thời không khả dụng để quan sát Retry, Circuit Breaker và trạng thái PROCESSING | 08/07/2026 | 08/07/2026 | Mã nguồn Payment Service và API Gateway |
| 5 | - Thực hiện kiểm thử tải và theo dõi hệ thống<br>&emsp; + Tăng dần số lượng người dùng ảo và request trong từng giai đoạn kiểm thử<br>&emsp; + Theo dõi latency, throughput, error rate, CPU, memory, số ECS task, connection database và Redis<br>&emsp; + Quan sát ECS Service Auto Scaling và xác định các điểm nghẽn của ứng dụng hoặc hạ tầng | 09/07/2026 | 09/07/2026 | Amazon CloudWatch và công cụ kiểm thử tải |
| 6 | - Tối ưu, kiểm thử lại và hoàn thiện dự án<br>&emsp; + Điều chỉnh timeout, Retry, rate-limit threshold, CPU/memory và scaling policy phù hợp<br>&emsp; + Kiểm thử hồi quy các luồng chính sau khi sửa lỗi<br>&emsp; + Hoàn thiện sơ đồ kiến trúc, worklog, báo cáo kết quả và xóa/tắt tài nguyên AWS không còn cần thiết để tránh phát sinh chi phí | 10/07/2026 | 10/07/2026 | Tài liệu và kết quả kiểm thử của dự án |

### Kết quả đạt được tuần 12:

* Hoàn thành kiểm tra tích hợp end-to-end:
  * Xác nhận luồng request đi qua API Gateway, VPC Link, Internal ALB và đến đúng ECS Service.
  * Kiểm tra các dịch vụ kết nối thành công với RDS PostgreSQL và ElastiCache Redis.
  * Sử dụng CloudWatch Logs và traceId để đối chiếu request giữa các microservice và hỗ trợ tìm lỗi.

* Xác nhận các cơ chế bảo vệ dữ liệu hoạt động đúng trong các kịch bản kiểm thử:
  * Nhiều request có cùng `idempotencyKey` không tạo thêm payment và không debit tài khoản nhiều lần.
  * Account Service trả kết quả idempotent cho `transactionId` trùng khớp và từ chối khi dữ liệu giao dịch không giống yêu cầu đầu tiên.
  * State machine và thao tác claim có điều kiện ngăn nhiều tiến trình cùng xử lý một payment.

* Đánh giá được hành vi của hệ thống dưới tải:
  * Theo dõi được throughput, latency, error rate và mức sử dụng CPU/memory trong từng giai đoạn tăng tải.
  * Kiểm tra rate limiter trả HTTP 429 khi một user vượt giới hạn, giúp bảo vệ các dịch vụ phía sau.
  * Quan sát Retry, Circuit Breaker, Redis lock và ECS Service Auto Scaling khi lưu lượng hoặc lỗi kết nối tăng cao.

* Hoàn thiện và tổng kết dự án:
  * Điều chỉnh các tham số timeout, retry, rate limit và tài nguyên container dựa trên kết quả kiểm thử.
  * Hoàn thiện sơ đồ kiến trúc AWS, tài liệu triển khai, worklog song ngữ và nội dung báo cáo dự án.
  * Rà soát, tắt hoặc xóa tài nguyên AWS không cần thiết nhằm hạn chế chi phí sau khi kết thúc kiểm thử.
