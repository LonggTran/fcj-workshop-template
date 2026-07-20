---
title: "Worklog Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Mục tiêu tuần 9:

* Hoàn thiện Account Service với cơ chế cập nhật số dư an toàn khi có nhiều request đồng thời.
* Xây dựng idempotency cho thao tác debit/credit bằng `transactionId` và bảng lịch sử giao dịch.
* Tích hợp Redis Cache cho dữ liệu tài khoản và số dư.
* Xây dựng Transaction Service và khởi tạo các chức năng cốt lõi của Payment Service.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Hoàn thiện thao tác debit/credit của Account Service<br>&emsp; + Sử dụng câu lệnh cập nhật số dư trực tiếp tại PostgreSQL để bảo đảm tính nguyên tử<br>&emsp; + Kiểm tra trạng thái tài khoản, loại tiền và số dư khả dụng<br>&emsp; + Chuẩn hóa amount về hai chữ số thập phân | 15/06/2026 | 15/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Xây dựng idempotency cho Account Service<br>&emsp; + Dùng `transactionId` làm khóa duy nhất trong bảng `transaction_histories`<br>&emsp; + Chèn lịch sử bằng cơ chế `ON CONFLICT DO NOTHING` để nhận biết request trùng lặp<br>&emsp; + Trả lại kết quả hiện tại khi payload trùng khớp và trả conflict khi dữ liệu khác yêu cầu ban đầu | 16/06/2026 | 16/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Tích hợp Redis Cache cho dữ liệu tài khoản<br>&emsp; + Cache thông tin tài khoản và số dư bằng `@Cacheable`<br>&emsp; + Xóa cache sau thao tác debit/credit bằng `@CacheEvict`<br>&emsp; + Cấu hình serializer và thời gian lưu cache phù hợp | 17/06/2026 | 17/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Xây dựng Transaction Service<br>&emsp; + Tạo entity, repository, service, controller và mapper cho giao dịch<br>&emsp; + Xây dựng API tạo giao dịch, tra cứu theo ID và liệt kê theo tài khoản<br>&emsp; + Kiểm tra idempotency khi client cung cấp `transactionId` | 18/06/2026 | 18/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Khởi tạo Payment Service và kiểm thử liên service<br>&emsp; + Tạo Payment entity, trạng thái thanh toán và unique constraint cho `idempotencyKey`<br>&emsp; + Xây dựng API tạo, tra cứu thanh toán và danh sách thanh toán theo người dùng<br>&emsp; + Kiểm thử các API Account, Transaction và Payment bằng dữ liệu hợp lệ, trùng lặp và không hợp lệ | 19/06/2026 | 19/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 9:

* Hoàn thiện Account Service với các API tạo tài khoản, truy vấn số dư, debit và credit.
* Áp dụng cập nhật số dư nguyên tử tại PostgreSQL, hạn chế race condition khi nhiều request truy cập cùng tài khoản.
* Hoàn thành cơ chế idempotency cho debit/credit; request trùng khớp không thay đổi số dư lần hai, request dùng lại `transactionId` với payload khác bị từ chối.
* Tích hợp Redis Cache và cơ chế làm mới cache sau khi số dư thay đổi.
* Hoàn thiện Transaction Service và xây dựng bộ khung Payment Service với khóa `idempotencyKey` duy nhất.
