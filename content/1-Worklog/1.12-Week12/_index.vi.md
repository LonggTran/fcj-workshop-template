---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
### Mục tiêu tuần 12:

* Hoàn thiện triển khai và nghiệm thu hệ thống High-Concurrency Payment Gateway trên AWS.
* Theo dõi log, metrics, Target Group, ECS Task và kết nối RDS trong quá trình vận hành.
* Thực hiện kiểm thử tải, quan sát độ trễ, tỷ lệ lỗi, HTTP 429 và khả năng tự động mở rộng.
* Thiết lập CloudWatch Alarm, Amazon SNS, sao lưu RDS và dọn dẹp tài nguyên sau kiểm thử.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Kiểm tra hệ thống sau triển khai<br>&emsp; + Kiểm tra trạng thái Running của ECS Tasks và Healthy của Target Groups<br>&emsp; + Truy cập ứng dụng qua ALB DNS<br>&emsp; + Kiểm tra kết nối giữa backend, Redis sidecar và RDS PostgreSQL<br>&emsp; + Kiểm thử các luồng tài khoản, thanh toán và giao dịch | 06/07/2026 | 06/07/2026 | <https://000016.awsstudygroup.com/><br><https://000005.awsstudygroup.com/> |
| Thứ 3 | - Thiết lập giám sát bằng Amazon CloudWatch<br>&emsp; + Thu thập CloudWatch Logs từ ECS Fargate<br>&emsp; + Theo dõi ALB RequestCount, TargetResponseTime, HTTPCode và ECS CPU/Memory<br>&emsp; + Tạo CloudWatch Dashboard và Logs Insights query<br>&emsp; + Kiểm tra lỗi ứng dụng và kết nối từ log tập trung | 07/07/2026 | 07/07/2026 | <https://000008.awsstudygroup.com/> |
| Thứ 4 | - Cấu hình cảnh báo tự động<br>&emsp; + Tạo CloudWatch Alarm theo RequestCount hoặc CPU Utilization<br>&emsp; + Tạo Amazon SNS Topic và đăng ký email nhận cảnh báo<br>&emsp; + Kiểm tra trạng thái OK, ALARM và quá trình gửi email<br>&emsp; + Rà soát IAM Role và quyền truy cập của ECS Task | 08/07/2026 | 08/07/2026 | <https://000008.awsstudygroup.com/><br><https://000013.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |
| Thứ 5 | - Thực hiện kiểm thử tải và điều chỉnh hệ thống<br>&emsp; + Chạy k6/JMeter với số lượng virtual user và request tăng dần<br>&emsp; + Theo dõi latency, throughput, error rate và phản hồi HTTP 429<br>&emsp; + Quan sát ALB RequestCount, ECS CPU/Memory và số lượng task khi Auto Scaling hoạt động<br>&emsp; + Điều chỉnh rate limit, timeout, CPU/Memory và scaling policy dựa trên kết quả kiểm thử | 09/07/2026 | 09/07/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://000008.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Thứ 6 | - Hoàn thiện sao lưu, tài liệu và dọn dẹp tài nguyên<br>&emsp; + Tạo RDS Snapshot và kiểm tra khả năng backup/restore<br>&emsp; + Hoàn thiện tài liệu triển khai, sơ đồ kiến trúc và worklog song ngữ<br>&emsp; + Kiểm thử hồi quy sau khi điều chỉnh cấu hình<br>&emsp; + Tắt hoặc xóa ECS Service, ALB, NAT Gateway, RDS và các tài nguyên không còn sử dụng để tránh phát sinh chi phí | 10/07/2026 | 10/07/2026 | <https://000005.awsstudygroup.com/><br><https://000013.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |

### Kết quả đạt được tuần 12:

* Hoàn tất kiểm tra end-to-end từ ALB đến ECS Fargate, Redis và RDS PostgreSQL.
* Theo dõi được log và các chỉ số vận hành của ALB, ECS và ứng dụng bằng CloudWatch.
* Thiết lập CloudWatch Alarm và Amazon SNS để gửi email cảnh báo khi hệ thống vượt ngưỡng.
* Thực hiện kiểm thử tải và ghi nhận latency, throughput, error rate, HTTP 429 và phản ứng của ECS Service Auto Scaling.
* Hoàn thành RDS Snapshot, tài liệu triển khai, sơ đồ kiến trúc, worklog song ngữ và quy trình dọn dẹp tài nguyên AWS.
