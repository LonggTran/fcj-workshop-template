---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 11:

* Tích hợp toàn bộ microservices trong môi trường cục bộ và chuẩn hóa cấu hình để triển khai lên AWS.
* Hoàn thiện sơ đồ kiến trúc AWS cho hệ thống thanh toán chịu tải cao theo mô hình dịch vụ quản lý và tự động mở rộng.
* Tạo, cấu hình các dịch vụ mạng, compute, database, cache, bảo mật và giám sát cần thiết trên AWS.
* Đóng gói ứng dụng thành Docker image và triển khai các dịch vụ bằng Amazon ECS Fargate.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tích hợp và kiểm tra luồng cục bộ<br>&emsp; + Khởi chạy PostgreSQL, Redis và các microservice với cấu hình môi trường thống nhất<br>&emsp; + Kiểm tra định tuyến qua API Gateway, health endpoint và kết nối Payment Service → Account Service<br>&emsp; + Sửa lỗi cấu hình database, biến môi trường và schema khi chạy đồng thời | 29/06/2026 | 29/06/2026 | Mã nguồn và Docker Compose của dự án |
| 3 | - Hoàn thiện kiến trúc triển khai AWS<br>&emsp; + Thiết kế một VPC trên hai Availability Zone với các subnet dành cho tầng ứng dụng và dữ liệu<br>&emsp; + Xác định luồng Amazon API Gateway → VPC Link → Internal ALB → ECS Fargate<br>&emsp; + Thiết kế Security Group và IAM Role theo nguyên tắc đặc quyền tối thiểu | 30/06/2026 | 30/06/2026 | <https://docs.aws.amazon.com/vpc/> |
| 4 | - Tạo tầng lưu trữ image và compute<br>&emsp; + Tạo Amazon ECR repository, build và push Docker image của các dịch vụ<br>&emsp; + Tạo ECS Cluster, Task Definition và ECS Service trên Fargate<br>&emsp; + Cấu hình health check và ECS Service Auto Scaling cho từng dịch vụ | 01/07/2026 | 01/07/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/> |
| 5 | - Tạo tầng dữ liệu và cấu hình bảo mật<br>&emsp; + Tạo Amazon RDS for PostgreSQL cho dữ liệu account, payment và transaction<br>&emsp; + Tạo Amazon ElastiCache for Redis cho cache, lock và rate limit<br>&emsp; + Lưu thông tin kết nối trong AWS Secrets Manager và gán quyền truy cập cho ECS Task Role | 02/07/2026 | 02/07/2026 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/> |
| 6 | - Hoàn thiện tầng truy cập và giám sát<br>&emsp; + Tạo Internal Application Load Balancer, target group và listener rule cho các dịch vụ<br>&emsp; + Kết nối API Gateway với ALB thông qua VPC Link<br>&emsp; + Cấu hình CloudWatch Logs, metrics, alarms và theo dõi health của ECS, RDS, Redis | 03/07/2026 | 03/07/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vpc-links.html> |

### Kết quả đạt được tuần 11:

* Hoàn thành tích hợp các thành phần của hệ thống:
  * API Gateway định tuyến đúng đến Account Service, Payment Service và Transaction Service.
  * Payment Service kết nối được với Account Service; các dịch vụ truy cập đúng PostgreSQL và Redis theo cấu hình môi trường.
  * Các endpoint Actuator hỗ trợ kiểm tra nhanh tình trạng của từng dịch vụ trước và sau triển khai.

* Hoàn thiện kiến trúc AWS phù hợp với hệ thống chịu tải cao:
  * Amazon API Gateway được đặt ngoài VPC và kết nối vào mạng riêng qua VPC Link.
  * Internal ALB phân phối request đến các ECS Service chạy trên AWS Fargate.
  * RDS PostgreSQL và ElastiCache Redis được đặt trong tầng dữ liệu riêng, chỉ cho phép truy cập từ các Security Group cần thiết.

* Đóng gói và triển khai được ứng dụng theo mô hình container:
  * Docker image được lưu trữ tập trung trên Amazon ECR.
  * ECS Task Definition quản lý image, port, CPU, memory, biến môi trường và secrets của mỗi dịch vụ.
  * ECS Service Auto Scaling tạo nền tảng tăng hoặc giảm số lượng task theo mức sử dụng tài nguyên.

* Thiết lập được các thành phần vận hành và bảo mật cơ bản:
  * IAM Role và Security Group được giới hạn theo trách nhiệm của từng tầng.
  * Thông tin nhạy cảm được tách khỏi source code và quản lý bằng AWS Secrets Manager.
  * Log ứng dụng và chỉ số hạ tầng được tập trung trên Amazon CloudWatch để phục vụ giai đoạn kiểm thử tải.
