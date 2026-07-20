---
title: "Worklog Tuần 12"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
### Mục tiêu tuần 12:

* Hoàn thiện triển khai và kiểm tra end-to-end hệ thống High-Concurrency Payment Gateway trên AWS.
* Theo dõi trạng thái ALB Target Groups, ECS Tasks, RDS, Redis sidecar và CloudWatch Logs.
* Thực hiện kiểm thử tải bằng k6, quan sát RequestCount, độ trễ, tỷ lệ lỗi và phản ứng của ECS Service Auto Scaling.
* Cấu hình CloudWatch Alarm, Amazon SNS và sao lưu RDS Snapshot sang Amazon S3 với AWS KMS.
* Khắc phục lỗi, hoàn thiện tài liệu triển khai và dọn dẹp tài nguyên AWS không còn sử dụng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Kiểm tra và nghiệm thu các thành phần sau triển khai<br>&emsp; + Kiểm tra trạng thái Healthy của target group frontend và backend<br>&emsp; + Truy cập ứng dụng qua DNS của ALB và kiểm thử các luồng tài khoản, thanh toán, số dư và giao dịch<br>&emsp; + Kiểm tra CloudWatch Log Streams của backend, Redis và frontend | 06/07/2026 | 06/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.10-verification/> |
| Thứ 3 | - Thực hiện kiểm thử tải và theo dõi hiệu năng<br>&emsp; + Chạy k6 với nhiều Virtual Users và số lượng request tăng dần<br>&emsp; + Theo dõi latency, throughput, error rate và HTTP 429 từ rate limiter<br>&emsp; + Quan sát ALB RequestCount, CPU/Memory của ECS và số lượng task trong quá trình tăng tải | 07/07/2026 | 07/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.8-cloudwatch-alarm/><br><https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.10-verification/> |
| Thứ 4 | - Cấu hình cảnh báo và điều chỉnh hệ thống<br>&emsp; + Tạo Amazon SNS Topic và đăng ký email nhận cảnh báo<br>&emsp; + Tạo CloudWatch Alarm theo ALB RequestCount hoặc mức sử dụng CPU<br>&emsp; + Điều chỉnh timeout, rate-limit threshold, CPU/Memory và scaling policy dựa trên kết quả kiểm thử<br>&emsp; + Sửa các lỗi cấu hình ứng dụng hoặc kết nối phát sinh khi chạy trên AWS | 08/07/2026 | 08/07/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.8-cloudwatch-alarm/> |
| Thứ 5 | - Thực hiện sao lưu dữ liệu trên AWS<br>&emsp; + Tạo S3 Bucket dùng lưu trữ dữ liệu backup<br>&emsp; + Tạo AWS KMS Key và IAM Role phục vụ xuất snapshot<br>&emsp; + Tạo RDS Snapshot và export dữ liệu sang Amazon S3 với mã hóa | 09/07/2026 | 09/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.9-s3-backup/> |
| Thứ 6 | - Hoàn thiện báo cáo và dọn dẹp tài nguyên<br>&emsp; + Kiểm thử hồi quy các luồng chính sau khi sửa lỗi<br>&emsp; + Hoàn thiện sơ đồ kiến trúc, tài liệu Workshop, worklog song ngữ và báo cáo kết quả<br>&emsp; + Rà soát, tắt hoặc xóa ECS Services, ALB, NAT Gateway, RDS, S3 và các tài nguyên không còn sử dụng để tránh phát sinh chi phí | 10/07/2026 | 10/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.10-verification/><br><https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.11-cleanup/> |

### Kết quả đạt được tuần 12:

* Kiểm tra được luồng truy cập từ Internet qua ALB đến frontend và API Gateway backend chạy trên ECS Fargate.
* Xác nhận các ECS Task kết nối được với RDS PostgreSQL, Redis sidecar và ghi log tập trung lên CloudWatch.
* Thực hiện kiểm thử tải bằng k6 và theo dõi được các chỉ số RequestCount, latency, throughput, error rate, CPU/Memory và phản hồi HTTP 429.
* Thiết lập CloudWatch Alarm và Amazon SNS để gửi cảnh báo khi hệ thống vượt ngưỡng theo dõi.
* Thực hiện quy trình tạo RDS Snapshot và chuẩn bị xuất dữ liệu backup sang S3 với mã hóa KMS.
* Hoàn thiện tài liệu triển khai, worklog tiếng Việt/tiếng Anh, sơ đồ kiến trúc và quy trình dọn dẹp tài nguyên AWS sau kiểm thử.
