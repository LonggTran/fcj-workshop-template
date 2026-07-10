---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 8:

* Phân tích yêu cầu và xác định phạm vi của dự án High Concurrency Payment Gateway phục vụ kiểm thử hệ thống thanh toán chịu tải cao.
* Thiết kế kiến trúc microservices gồm API Gateway, Payment Service, Account Service và Transaction Service.
* Khởi tạo dự án Java 21, Spring Boot và Gradle theo mô hình multi-module, đồng thời xây dựng các thư viện dùng chung.
* Thiết lập môi trường phát triển cục bộ với PostgreSQL, Redis và Docker Compose để chuẩn bị cho giai đoạn triển khai chức năng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Phân tích bài toán cổng thanh toán chịu tải cao<br>&emsp; + Xác định các yêu cầu về tính nhất quán dữ liệu, chống xử lý trùng lặp và khả năng chịu lỗi<br>&emsp; + Xác định các luồng chính: tạo tài khoản, ghi nợ, ghi có, tạo thanh toán và tra cứu giao dịch | 08/06/2026 | 08/06/2026 | Mô tả dự án và mã nguồn hệ thống |
| 3 | - Thiết kế kiến trúc microservices và cấu trúc mã nguồn<br>&emsp; + Phân tách API Gateway, Account Service, Payment Service và Transaction Service<br>&emsp; + Xác định trách nhiệm, cổng chạy và cơ sở dữ liệu riêng của từng dịch vụ | 09/06/2026 | 09/06/2026 | <https://spring.io/projects/spring-boot> |
| 4 | - Khởi tạo Gradle multi-module với Java 21<br>&emsp; + Tạo các module dịch vụ và hai thư viện dùng chung `common-dto`, `common-exception`<br>&emsp; + Cấu hình các dependency Spring Web, Validation, JPA, Actuator và PostgreSQL | 10/06/2026 | 10/06/2026 | <https://docs.gradle.org/> |
| 5 | - Thiết lập môi trường dữ liệu cục bộ<br>&emsp; + Cấu hình Docker Compose cho PostgreSQL và Redis<br>&emsp; + Tạo riêng các database `paymentservice`, `accountservice`, `transactionservice`<br>&emsp; + Chuẩn hóa biến môi trường kết nối cơ sở dữ liệu | 11/06/2026 | 11/06/2026 | <https://docs.docker.com/compose/> |
| 6 | - Xây dựng bộ khung cho các dịch vụ<br>&emsp; + Tạo entity, repository, service, controller và DTO cơ bản<br>&emsp; + Chuẩn hóa cấu trúc phản hồi API, mã lỗi và xử lý ngoại lệ dùng chung<br>&emsp; + Cấu hình health check qua Spring Boot Actuator | 12/06/2026 | 12/06/2026 | Mã nguồn dự án High Concurrency Payment Gateway |

### Kết quả đạt được tuần 8:

* Hoàn thành phân tích phạm vi và các yêu cầu kỹ thuật quan trọng của hệ thống thanh toán chịu tải cao:
  * Xác định idempotency là cơ chế bắt buộc để ngăn một yêu cầu thanh toán hoặc ghi nợ bị thực thi nhiều lần.
  * Xác định Redis được sử dụng cho rate limiting, cache và distributed lock; PostgreSQL đảm nhiệm lưu trữ dữ liệu giao dịch bền vững.
  * Phân tách rõ trách nhiệm của từng microservice, hạn chế phụ thuộc trực tiếp giữa các cơ sở dữ liệu.

* Khởi tạo thành công cấu trúc Gradle multi-module:
  * Tạo bốn module dịch vụ gồm API Gateway, Account Service, Payment Service và Transaction Service.
  * Tạo thư viện `common-dto` và `common-exception` để tái sử dụng định dạng phản hồi và mã lỗi giữa các dịch vụ.
  * Chuẩn hóa cấu trúc package theo các tầng controller, service, repository, entity, DTO, mapper và exception.

* Hoàn thành môi trường phát triển cục bộ:
  * Khởi chạy PostgreSQL và Redis bằng Docker Compose.
  * Tạo các cơ sở dữ liệu riêng cho từng dịch vụ nghiệp vụ.
  * Cấu hình profile phát triển, biến môi trường, cổng dịch vụ và endpoint kiểm tra trạng thái hệ thống.
