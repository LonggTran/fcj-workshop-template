---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Mục tiêu tuần 9:

* Hoàn thiện Account Service và tiếp tục xây dựng Payment Service, Transaction Service.
* Triển khai giao tiếp giữa Payment Service và Account Service bằng OpenFeign.
* Áp dụng idempotency, trạng thái thanh toán, Circuit Breaker và Retry cho luồng xử lý giao dịch.
* Kiểm thử tích hợp các service và đánh giá tính nhất quán dữ liệu.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Hoàn thiện Account Service<br>&emsp; + Rà soát cơ chế idempotent debit/credit<br>&emsp; + Chuẩn hóa Transaction History, currency và các mã lỗi nghiệp vụ<br>&emsp; + Kiểm tra cache invalidation sau khi số dư thay đổi | 15/06/2026 | 15/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Xây dựng Payment Service<br>&emsp; + Thiết kế Payment Entity, DTO, Repository, Service, Mapper và Controller<br>&emsp; + Xây dựng API tạo thanh toán và tra cứu lịch sử thanh toán<br>&emsp; + Sử dụng idempotencyKey để ngăn tạo giao dịch thanh toán lặp | 16/06/2026 | 16/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Tích hợp Payment Service với Account Service<br>&emsp; + Cấu hình OpenFeign Client<br>&emsp; + Xây dựng request trừ tiền theo paymentId/transactionId<br>&emsp; + Cấu hình connect timeout, read timeout và xử lý lỗi liên dịch vụ<br>&emsp; + Tích hợp Resilience4j Circuit Breaker và Retry | 17/06/2026 | 17/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Xây dựng Transaction Service<br>&emsp; + Thiết kế Transaction Entity, trạng thái và loại giao dịch<br>&emsp; + Xây dựng API tạo giao dịch, tra cứu theo ID và theo tài khoản<br>&emsp; + Áp dụng idempotency theo transactionId và kiểm tra xung đột dữ liệu | 18/06/2026 | 18/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Kiểm thử tích hợp các microservices<br>&emsp; + Kiểm tra luồng tạo tài khoản, tạo thanh toán, trừ số dư và lưu giao dịch<br>&emsp; + Kiểm tra request trùng, số dư không đủ, sai loại tiền và lỗi timeout<br>&emsp; + Theo dõi trạng thái PENDING, PROCESSING, SUCCESS và FAILED<br>&emsp; + Ghi nhận và khắc phục lỗi dữ liệu không nhất quán | 19/06/2026 | 19/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 9:

* Hoàn thiện Account Service và cơ chế idempotency cho thao tác số dư.
* Hoàn thành các thành phần chính của Payment Service và Transaction Service.
* Thiết lập giao tiếp Payment Service đến Account Service bằng OpenFeign.
* Tích hợp Circuit Breaker, Retry, timeout và xử lý lỗi liên dịch vụ.
* Kiểm thử được các luồng thanh toán chính và các trường hợp lỗi nghiệp vụ bằng Postman.
