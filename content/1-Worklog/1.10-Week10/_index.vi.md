---
title: "Worklog Tuần 10"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Mục tiêu tuần 10:

* Hoàn thiện Payment Service với idempotency và state machine `PENDING → PROCESSING → SUCCESS/FAILED`.
* Xây dựng cơ chế giành quyền xử lý bằng `processingToken`, lease và câu lệnh cập nhật có điều kiện tại PostgreSQL.
* Tích hợp OpenFeign, Retry, Circuit Breaker và worker khôi phục các payment bị gián đoạn.
* Hoàn thiện API Gateway với Redis Token Bucket rate limiter theo `userId` và tích hợp toàn bộ microservices.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Hoàn thiện idempotency và state machine của Payment Service<br>&emsp; + Kiểm tra payload khi `idempotencyKey` đã tồn tại<br>&emsp; + Khởi tạo payment ở trạng thái PENDING và chỉ cho phép chuyển sang các trạng thái hợp lệ<br>&emsp; + Trả lại payment hiện có cho request trùng khớp, từ chối trường hợp dùng lại key với dữ liệu khác | 22/06/2026 | 22/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 3 | - Xây dựng quyền sở hữu xử lý payment<br>&emsp; + Claim payment bằng câu lệnh `UPDATE ... WHERE status = 'PENDING'`<br>&emsp; + Gán `processingToken`, thời điểm bắt đầu và `leaseExpiresAt` cho tiến trình sở hữu<br>&emsp; + Chỉ tiến trình giữ đúng token mới được hoàn tất payment | 23/06/2026 | 23/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 4 | - Xây dựng cơ chế khôi phục và đối soát payment<br>&emsp; + Tạo worker định kỳ tìm payment PROCESSING hết lease hoặc PENDING quá thời gian chờ<br>&emsp; + Lập lịch retry bằng `nextRetryAt` và exponential backoff cho lỗi tạm thời<br>&emsp; + Giữ payment ở PROCESSING khi chưa xác định chắc chắn kết quả debit | 24/06/2026 | 24/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 5 | - Tích hợp Payment Service với Account Service<br>&emsp; + Gọi API debit qua OpenFeign và dùng payment ID làm `transactionId`<br>&emsp; + Cấu hình connect timeout, read timeout, Retry và Circuit Breaker bằng Resilience4j<br>&emsp; + Phân biệt lỗi nghiệp vụ, rate limit và lỗi kết nối tạm thời | 25/06/2026 | 25/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thứ 6 | - Hoàn thiện API Gateway và tích hợp hệ thống<br>&emsp; + Định tuyến `/api/accounts/**`, `/api/payments/**` và `/api/transactions/**` đến đúng service<br>&emsp; + Xây dựng Redis Lua Token Bucket bảo đảm kiểm tra và cập nhật giới hạn nguyên tử<br>&emsp; + Giới hạn theo `X-User-Id` hoặc `userId`, fallback theo IP và trả HTTP 429 khi vượt ngưỡng<br>&emsp; + Kiểm tra luồng tạo tài khoản, thanh toán, trừ tiền và tra cứu giao dịch qua gateway | 26/06/2026 | 26/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Kết quả đạt được tuần 10:

* Hoàn thiện Payment Service với khóa `idempotencyKey` duy nhất và state machine kiểm soát trạng thái thanh toán.
* Xây dựng cơ chế sở hữu xử lý dựa trên PostgreSQL bằng `processingToken` và lease, ngăn nhiều request cùng debit cho một payment.
* Bổ sung worker khôi phục, lịch retry và exponential backoff cho payment bị gián đoạn hoặc gặp lỗi tạm thời.
* Tích hợp OpenFeign, Resilience4j Retry và Circuit Breaker khi Payment Service gọi Account Service.
* Hoàn thiện API Gateway với Redis Lua Token Bucket rate limiter theo `userId`; không sử dụng JWT trong phạm vi hiện tại.
* Tích hợp thành công các service trong môi trường cục bộ và chuẩn bị cấu hình cho giai đoạn triển khai AWS.
