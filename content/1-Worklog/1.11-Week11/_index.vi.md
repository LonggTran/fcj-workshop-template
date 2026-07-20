---
title: "Worklog Tuần 11"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Mục tiêu tuần 11:

* Đóng gói ứng dụng bằng Docker và lưu trữ image trên Amazon ECR.
* Thiết lập hạ tầng mạng VPC trên hai Availability Zone với Public/Private Subnets, Internet Gateway, NAT Gateway và Security Groups.
* Khởi tạo Amazon RDS PostgreSQL trong Private Subnets và chuẩn bị dữ liệu qua EC2 Bastion Host.
* Triển khai Application Load Balancer và các container trên Amazon ECS Fargate.
* Thiết lập IAM Role, CloudWatch Logs và ECS Service Auto Scaling cho môi trường triển khai.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Đóng gói ứng dụng và quản lý Amazon ECR<br>&emsp; + Biên dịch các service Spring Boot thành file JAR<br>&emsp; + Build Docker image backend và chuẩn bị image frontend theo cấu trúc triển khai<br>&emsp; + Tạo ECR Repository, tag và push image lên AWS | 29/06/2026 | 29/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.2-prerequiste/> |
| Thứ 3 | - Thiết lập VPC Networking và Security Groups<br>&emsp; + Tạo VPC trên hai Availability Zone với hai Public Subnets và hai Private Subnets<br>&emsp; + Cấu hình Internet Gateway, NAT Gateway và Route Tables<br>&emsp; + Phân tách Security Group cho ALB, ECS Fargate, RDS và Bastion Host | 30/06/2026 | 30/06/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.3-vpc-networking/><br><https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.4-security-groups/> |
| Thứ 4 | - Khởi tạo Amazon RDS PostgreSQL trong mạng riêng<br>&emsp; + Tạo DB Subnet Group từ hai Private Subnets<br>&emsp; + Khởi tạo RDS PostgreSQL với Public Access tắt<br>&emsp; + Tạo EC2 Bastion Host và chạy script tạo các database nghiệp vụ | 01/07/2026 | 01/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.5-rds-database/> |
| Thứ 5 | - Cấu hình Application Load Balancer<br>&emsp; + Tạo target group cho frontend và backend API Gateway<br>&emsp; + Khởi tạo Internet-facing ALB tại Public Subnets<br>&emsp; + Cấu hình listener rule để `/api/*` chuyển đến backend và request mặc định chuyển đến frontend | 02/07/2026 | 02/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.6-load-balancer/> |
| Thứ 6 | - Triển khai Amazon ECS Fargate<br>&emsp; + Tạo ECS Cluster, CloudWatch Log Group, Task Execution Role và Task Role<br>&emsp; + Đăng ký Task Definitions cho backend, Redis sidecar và frontend<br>&emsp; + Tạo ECS Services trong Private Subnets, gắn target group và cấu hình Service Auto Scaling | 03/07/2026 | 03/07/2026 | <https://xduc695.github.io/fcj-workshop-template/vi/5-workshop/5.7-ecs-fargate/> |

### Kết quả đạt được tuần 11:

* Hoàn thành build, tag và push các Docker image phục vụ triển khai lên Amazon ECR.
* Thiết lập được VPC đa Availability Zone với Public/Private Subnets, Internet Gateway, NAT Gateway, Route Tables và Security Groups phân lớp.
* Khởi tạo RDS PostgreSQL trong mạng riêng và tạo các database cho Account, Payment và Transaction Service qua Bastion Host.
* Cấu hình ALB, target groups và listener rules để phân phối traffic đến frontend và API Gateway backend.
* Triển khai các task và service trên ECS Fargate, tập trung log về CloudWatch và cấu hình nền tảng tự động mở rộng theo tải.
