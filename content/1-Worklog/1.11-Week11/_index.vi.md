---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Mục tiêu tuần 11:

* Bắt đầu triển khai High-Concurrency Payment Gateway lên AWS.
* Đẩy Docker image lên Amazon ECR và xây dựng hạ tầng mạng nhiều Availability Zone.
* Khởi tạo Amazon RDS PostgreSQL, Application Load Balancer và Amazon ECS Fargate.
* Thiết lập Security Group, IAM Role, CloudWatch Logs và ECS Service Auto Scaling.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Đóng gói ứng dụng và quản lý image trên Amazon ECR<br>&emsp; + Build các service thành file JAR<br>&emsp; + Build Docker image cho backend và frontend<br>&emsp; + Tạo ECR Repository, đăng nhập Docker vào ECR<br>&emsp; + Tag và push image lên Amazon ECR | 29/06/2026 | 29/06/2026 | <https://000015.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Thứ 3 | - Thiết lập hạ tầng mạng AWS<br>&emsp; + Tạo VPC trên hai Availability Zone<br>&emsp; + Tạo public subnet và private subnet<br>&emsp; + Cấu hình Internet Gateway, NAT Gateway và Route Table<br>&emsp; + Tạo Security Group cho ALB, ECS, RDS và Bastion Host | 30/06/2026 | 30/06/2026 | <https://000003.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |
| Thứ 4 | - Khởi tạo Amazon RDS PostgreSQL trong private subnet<br>&emsp; + Tạo DB Subnet Group từ hai private subnet<br>&emsp; + Cấu hình RDS không public access và chỉ nhận kết nối từ Security Group nội bộ<br>&emsp; + Tạo Bastion Host để khởi tạo accountservice, paymentservice và transactionservice database<br>&emsp; + Kiểm tra kết nối và Flyway Migration | 01/07/2026 | 01/07/2026 | <https://000005.awsstudygroup.com/><br><https://000015.awsstudygroup.com/> |
| Thứ 5 | - Cấu hình Application Load Balancer<br>&emsp; + Tạo Target Group cho frontend và backend API Gateway<br>&emsp; + Tạo internet-facing ALB trên các public subnet<br>&emsp; + Cấu hình Listener Rule chuyển `/api/*` đến backend và request mặc định đến frontend<br>&emsp; + Thiết lập health check cho các target group | 02/07/2026 | 02/07/2026 | <https://000006.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Thứ 6 | - Triển khai ứng dụng trên Amazon ECS Fargate<br>&emsp; + Tạo ECS Cluster, Task Definition và ECS Service<br>&emsp; + Chạy các task trong private subnet, tắt public IP<br>&emsp; + Cấu hình Redis container sidecar cho backend<br>&emsp; + Gắn ECS Service với ALB Target Group<br>&emsp; + Thiết lập IAM Task Execution Role, CloudWatch Log Group và Service Auto Scaling | 03/07/2026 | 03/07/2026 | <https://000016.awsstudygroup.com/><br><https://000008.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |

### Kết quả đạt được tuần 11:

* Build và push thành công Docker image lên Amazon ECR.
* Hoàn thiện VPC nhiều Availability Zone với public/private subnet, Internet Gateway, NAT Gateway, Route Table và Security Group.
* Khởi tạo RDS PostgreSQL trong private subnet và chuẩn bị đầy đủ các database cho hệ thống.
* Cấu hình ALB, Target Group, Listener Rule và health check cho frontend/backend.
* Triển khai backend, frontend và Redis sidecar trên ECS Fargate, đồng thời tập trung log về CloudWatch.
