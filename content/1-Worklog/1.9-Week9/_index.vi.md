---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}}
⚠️ **Lưu ý:** Các thông tin dưới đây chỉ nhằm mục đích tham khảo, vui lòng **không sao chép nguyên văn** cho bài báo cáo của bạn kể cả warning này.
{{% /notice %}}

### Mục tiêu tuần 9:

* Triển khai Account Service để quản lý tài khoản, số dư và các thao tác ghi nợ/ghi có an toàn khi có nhiều yêu cầu đồng thời.
* Xây dựng cơ chế idempotency tại Account Service bằng `transactionId` và bảng lịch sử giao dịch.
* Tích hợp Redis Cache nhằm giảm số lần truy vấn tài khoản và số dư từ PostgreSQL.
* Hoàn thiện Transaction Service để lưu trữ và tra cứu giao dịch theo tài khoản.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Xây dựng miền dữ liệu Account Service<br>&emsp; + Tạo entity Account, trạng thái tài khoản và bộ sinh số tài khoản<br>&emsp; + Xây dựng API tạo tài khoản, lấy thông tin tài khoản và truy vấn số dư | 15/06/2026 | 15/06/2026 | Mã nguồn Account Service |
| 3 | - Triển khai thao tác ghi nợ và ghi có an toàn<br>&emsp; + Sử dụng câu lệnh cập nhật số dư trực tiếp tại PostgreSQL để đảm bảo tính nguyên tử<br>&emsp; + Kiểm tra trạng thái tài khoản, loại tiền và số dư khả dụng trước khi ghi nợ | 16/06/2026 | 16/06/2026 | <https://docs.spring.io/spring-data/jpa/reference/> |
| 4 | - Xây dựng idempotency cho Account Service<br>&emsp; + Dùng `transactionId` làm khóa duy nhất trong bảng `transaction_histories`<br>&emsp; + Áp dụng `INSERT ... ON CONFLICT DO NOTHING` để nhận biết yêu cầu trùng lặp<br>&emsp; + Trả kết quả thành công cho yêu cầu trùng khớp và báo conflict khi payload khác yêu cầu ban đầu | 17/06/2026 | 17/06/2026 | PostgreSQL và mã nguồn dự án |
| 5 | - Tích hợp Redis Cache cho dữ liệu tài khoản<br>&emsp; + Cache thông tin tài khoản và số dư bằng `@Cacheable`<br>&emsp; + Xóa cache liên quan sau thao tác debit/credit bằng `@CacheEvict`<br>&emsp; + Chuẩn hóa serialization cho dữ liệu cache | 18/06/2026 | 18/06/2026 | <https://docs.spring.io/spring-data/redis/reference/> |
| 6 | - Hoàn thiện Transaction Service<br>&emsp; + Xây dựng API tạo giao dịch, lấy giao dịch theo ID và danh sách giao dịch theo tài khoản<br>&emsp; + Kiểm tra idempotency khi client cung cấp `transactionId`<br>&emsp; + Chuẩn hóa kiểm tra amount, currency, type và xử lý lỗi nghiệp vụ | 19/06/2026 | 19/06/2026 | Mã nguồn Transaction Service |

### Kết quả đạt được tuần 9:

* Hoàn thiện Account Service với các chức năng cốt lõi:
  * Tạo tài khoản với số tài khoản duy nhất, loại tiền và số dư ban đầu.
  * Cung cấp API truy vấn thông tin tài khoản, số dư, ghi nợ và ghi có.
  * Chuẩn hóa amount về hai chữ số thập phân và kiểm tra trạng thái tài khoản, loại tiền, số dư trước khi cập nhật.

* Xây dựng được cơ chế cập nhật số dư an toàn trong điều kiện đồng thời:
  * Thực hiện debit bằng một câu lệnh SQL có điều kiện `balance >= amount`, tránh tình trạng kiểm tra và cập nhật bị tách rời.
  * Thực hiện credit bằng phép cập nhật nguyên tử trực tiếp trong cơ sở dữ liệu.
  * Phân loại rõ các lỗi không đủ số dư, tài khoản không hoạt động, sai loại tiền và lỗi thao tác.

* Hoàn thiện idempotency cho debit/credit:
  * Mỗi `transactionId` chỉ được ghi nhận một lần trong `transaction_histories`.
  * Yêu cầu lặp lại với cùng account, amount, currency và type trả lại kết quả hiện tại mà không trừ hoặc cộng tiền lần nữa.
  * Yêu cầu sử dụng lại `transactionId` với dữ liệu khác được từ chối bằng lỗi idempotency conflict.

* Tích hợp Redis Cache và hoàn thiện Transaction Service:
  * Giảm truy vấn lặp lại đối với thông tin tài khoản và số dư; cache được làm mới sau khi số dư thay đổi.
  * Lưu trữ giao dịch độc lập, hỗ trợ tra cứu theo ID và theo tài khoản.
  * Áp dụng kiểm tra trùng lặp và chuẩn hóa phản hồi lỗi thống nhất giữa các API.
