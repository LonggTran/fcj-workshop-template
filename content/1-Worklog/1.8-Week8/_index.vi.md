---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:

* Bắt đầu giai đoạn phát triển dự án High-Concurrency Payment Gateway theo kiến trúc microservices.
* Khởi tạo cấu trúc Java 21, Spring Boot và Gradle multi-module cho API Gateway, Account Service, Payment Service và Transaction Service.
* Thiết lập môi trường phát triển cục bộ với PostgreSQL, Redis và Docker Compose.
* Xây dựng bộ khung Account Service, thư viện dùng chung, cơ chế validation và xử lý ngoại lệ thống nhất.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Phân tích yêu cầu hệ thống thanh toán chịu tải cao<br>&emsp; + Xác định các luồng tạo tài khoản, ghi nợ, ghi có, tạo thanh toán và tra cứu giao dịch<br>&emsp; + Xác định yêu cầu về tính nhất quán dữ liệu, idempotency, rate limiting và khả năng chịu lỗi<br>&emsp; + Phân chia trách nhiệm giữa API Gateway, Account Service, Payment Service và Transaction Service | 08/06/2026 | 08/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Khởi tạo cấu trúc Gradle multi-module<br>&emsp; + Tạo bốn module dịch vụ và hai thư viện `common-dto`, `common-exception`<br>&emsp; + Cấu hình Java 21, Spring Boot, Spring Web, Validation, JPA và Actuator<br>&emsp; + Chuẩn hóa package controller, service, repository, entity, DTO, mapper và exception | 09/06/2026 | 09/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Thiết lập môi trường dữ liệu cục bộ<br>&emsp; + Cấu hình Docker Compose cho PostgreSQL và Redis<br>&emsp; + Tạo các database `accountservice`, `paymentservice` và `transactionservice` bằng script khởi tạo<br>&emsp; + Chuẩn hóa biến môi trường kết nối database và Redis cho từng service | 10/06/2026 | 10/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Xây dựng bộ khung Account Service<br>&emsp; + Tạo Account entity, trạng thái tài khoản, repository và mapper<br>&emsp; + Xây dựng API tạo tài khoản, lấy thông tin tài khoản và truy vấn số dư<br>&emsp; + Tạo bộ sinh số tài khoản và kiểm tra dữ liệu đầu vào | 11/06/2026 | 11/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Chuẩn hóa phản hồi và kiểm thử chức năng ban đầu<br>&emsp; + Xây dựng API Response, Error Response và Global Exception Handler dùng chung<br>&emsp; + Cấu hình health, info, metrics và Prometheus endpoint qua Spring Boot Actuator<br>&emsp; + Chạy thử các service, kiểm tra kết nối PostgreSQL/Redis và kiểm thử API cơ bản | 12/06/2026 | 12/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 8:

* Hoàn thành phân tích phạm vi và kiến trúc mã nguồn cho hệ thống thanh toán chịu tải cao.
* Khởi tạo thành công dự án Gradle multi-module gồm bốn microservice và hai thư viện dùng chung.
* Thiết lập được PostgreSQL, Redis và các database nghiệp vụ bằng Docker Compose.
* Hoàn thành bộ khung Account Service với API tạo tài khoản, truy vấn thông tin và kiểm tra số dư.
* Chuẩn hóa cấu trúc phản hồi, mã lỗi, xử lý ngoại lệ và endpoint giám sát cơ bản cho các service.
