---
title: "Worklog Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:

* Bắt đầu xây dựng dự án High-Concurrency Payment Gateway theo kiến trúc microservices.
* Thiết lập môi trường phát triển với JDK 21, Gradle multi-module, Docker, PostgreSQL và Redis.
* Xây dựng Account Service cùng các API quản lý tài khoản và số dư.
* Áp dụng Flyway Migration, validation, xử lý ngoại lệ tập trung, Redis Cache và cơ chế idempotency cho thao tác cộng/trừ tiền.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Khởi tạo cấu trúc dự án High-Concurrency Payment Gateway<br>&emsp; + Cấu hình JDK 21 và Gradle Wrapper<br>&emsp; + Thiết lập Gradle multi-module cho Account Service, Payment Service, Transaction Service và API Gateway<br>&emsp; + Tạo shared libraries dùng chung cho DTO và exception | 08/06/2026 | 08/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Thiết lập môi trường chạy cục bộ<br>&emsp; + Cấu hình PostgreSQL và Redis bằng Docker Compose<br>&emsp; + Tạo các database accountservice, paymentservice và transactionservice<br>&emsp; + Cấu hình Spring Boot kết nối PostgreSQL và Redis<br>&emsp; + Khởi tạo các script Flyway Migration | 09/06/2026 | 09/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Xây dựng Account Service<br>&emsp; + Thiết kế Account Entity, DTO, Repository, Service, Mapper và Controller<br>&emsp; + Xây dựng API tạo tài khoản, tra cứu tài khoản và kiểm tra số dư<br>&emsp; + Bổ sung validation và chuẩn hóa API Response | 10/06/2026 | 10/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Xây dựng chức năng cập nhật số dư an toàn<br>&emsp; + Triển khai API debit và credit<br>&emsp; + Sử dụng atomic update để hạn chế race condition khi có nhiều request đồng thời<br>&emsp; + Lưu Transaction History theo transactionId<br>&emsp; + Kiểm tra dữ liệu trùng theo idempotency key và phát hiện xung đột payload | 11/06/2026 | 11/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Hoàn thiện và kiểm thử Account Service<br>&emsp; + Tích hợp Redis Cache cho dữ liệu tài khoản và số dư<br>&emsp; + Xây dựng Global Exception Handler và mã lỗi nghiệp vụ<br>&emsp; + Kiểm thử các API bằng Postman<br>&emsp; + Sửa lỗi kết nối database, Redis và Flyway Migration | 12/06/2026 | 12/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 8:

* Hoàn thành cấu trúc Gradle multi-module và các thư viện dùng chung của dự án.
* Khởi chạy được PostgreSQL và Redis bằng Docker Compose, đồng thời kết nối thành công với Spring Boot.
* Hoàn thành Account Service với các API tạo tài khoản, tra cứu thông tin, kiểm tra số dư, cộng tiền và trừ tiền.
* Áp dụng atomic update, transaction history và idempotency để hạn chế giao dịch trùng lặp trong điều kiện nhiều request đồng thời.
* Tích hợp Redis Cache, Flyway Migration, validation và xử lý ngoại lệ tập trung.
