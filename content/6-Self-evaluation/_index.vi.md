---
title: "Tự đánh giá"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

Trong 12 tuần tham gia chương trình **First Cloud AI Journey**, từ ngày **17/04/2026 đến ngày 11/07/2026**, tôi đã củng cố kiến thức về điện toán đám mây, lập trình backend và quy trình triển khai ứng dụng trên AWS. Quá trình thực tập giúp tôi hiểu rõ hơn cách kết hợp kiến thức lý thuyết với việc xây dựng, kiểm thử và theo dõi một hệ thống thực tế.

Dự án chính được thực hiện là **High-Concurrency Payment Gateway – hệ thống kiểm thử khả năng chịu tải thanh toán cao**. Phần backend được xây dựng bằng Spring Boot theo kiến trúc microservices, gồm API Gateway Service, Account Service, Payment Service và Transaction Service. PostgreSQL được sử dụng để lưu dữ liệu; Redis hỗ trợ cache và rate limiting; Docker được dùng để đóng gói các thành phần của hệ thống.

Để hạn chế lỗi khi nhiều request cùng xử lý một tài khoản, dự án áp dụng idempotency key, cập nhật số dư nguyên tử có điều kiện, processing token và lease, Recovery Worker, Retry và Circuit Breaker. Ứng dụng được đóng gói và triển khai thử nghiệm với Amazon ECR, ECS Fargate, Application Load Balancer, RDS PostgreSQL, VPC và CloudWatch. k6 được sử dụng để tạo tải và kiểm tra tính nhất quán của số dư sau khi xử lý giao dịch.

Kết quả demo cho thấy hệ thống duy trì đúng số dư và hạn chế giao dịch bị xử lý lặp khi chịu tải đồng thời. Tuy nhiên, kết quả kiểm thử cũng phản ánh một số giới hạn: ở lần chạy 10.000 request vẫn còn 22 request không thành công và độ trễ P95 cao hơn ngưỡng kỳ vọng. Vì vậy, dự án hiện phù hợp ở mức **mô hình thử nghiệm và minh họa kỹ thuật**, chưa nên xem là hệ thống thanh toán sẵn sàng vận hành trong môi trường production.

Để phản ánh khách quan quá trình học tập và thực hiện dự án, tôi tự đánh giá bản thân theo các tiêu chí sau:

| STT | Tiêu chí                            | Mô tả                                                                                                           | Tốt | Khá | Trung bình |
| --- | ----------------------------------- | --------------------------------------------------------------------------------------------------------------- | --- | --- | ---------- |
| 1   | **Kiến thức và kỹ năng chuyên môn** | Vận dụng được Spring Boot, PostgreSQL, Redis, Docker và các dịch vụ AWS; vẫn cần nâng cao tối ưu hiệu năng       | ☐   | ✅   | ☐          |
| 2   | **Khả năng học hỏi**                | Chủ động tiếp cận tài liệu mới, thử nghiệm các dịch vụ AWS và kỹ thuật xử lý giao dịch đồng thời                | ✅   | ☐   | ☐          |
| 3   | **Chủ động**                        | Có khả năng tự tìm nguyên nhân lỗi và đề xuất hướng sửa, nhưng cần lập kế hoạch công việc chặt chẽ hơn           | ☐   | ✅   | ☐          |
| 4   | **Tinh thần trách nhiệm**           | Hoàn thành các nội dung chính của worklog, workshop, báo cáo, mã nguồn và video demo                            | ✅   | ☐   | ☐          |
| 5   | **Kỷ luật**                         | Tuân thủ yêu cầu bảo mật và quản lý tài nguyên AWS; cần duy trì việc kiểm tra tiến độ và tài nguyên thường xuyên | ☐   | ✅   | ☐          |
| 6   | **Tính cầu tiến**                   | Tiếp nhận góp ý về source code, kiến trúc, báo cáo và liên tục điều chỉnh sản phẩm                              | ✅   | ☐   | ☐          |
| 7   | **Giao tiếp**                       | Trình bày được luồng hệ thống và kết quả kiểm thử, nhưng cần diễn đạt ngắn gọn và tự tin hơn                     | ☐   | ✅   | ☐          |
| 8   | **Hợp tác nhóm**                    | Có trao đổi, tiếp nhận góp ý và phối hợp với thành viên; kinh nghiệm về review code và quy trình Agile còn hạn chế | ☐ | ✅ | ☐          |
| 9   | **Ứng xử chuyên nghiệp**            | Giữ thái độ nghiêm túc, tôn trọng người hướng dẫn và có trách nhiệm với tài khoản, dữ liệu và tài nguyên AWS     | ✅   | ☐   | ☐          |
| 10  | **Tư duy giải quyết vấn đề**        | Phân tích được lỗi dữ liệu, xử lý đồng thời và lỗi triển khai; chưa xử lý triệt để vấn đề latency                | ☐   | ✅   | ☐          |
| 11  | **Đóng góp vào dự án/tổ chức**      | Hoàn thiện được mã nguồn, tài liệu, sơ đồ kiến trúc và demo; chất lượng vẫn cần được chuẩn hóa thêm              | ☐   | ✅   | ☐          |
| 12  | **Tổng thể**                        | Hoàn thành mục tiêu chính và xây dựng được sản phẩm có thể trình bày, triển khai thử nghiệm và kiểm thử tải      | ☐   | ✅   | ☐          |

### Kết quả đạt được

* Xây dựng được các service chính và tích hợp thành luồng tạo tài khoản, thanh toán và ghi nhận lịch sử giao dịch.
* Áp dụng được idempotency, atomic update, processing token và lease để giảm rủi ro xử lý trùng và sai lệch số dư.
* Đóng gói ứng dụng bằng Docker, đẩy image lên Amazon ECR và triển khai thử nghiệm trên Amazon ECS Fargate.
* Kết nối backend với Amazon RDS PostgreSQL, phân phối request qua Application Load Balancer và theo dõi hệ thống bằng CloudWatch.
* Thực hiện kiểm thử tải bằng k6, đối chiếu số dư kỳ vọng với số dư thực tế và nhận diện được giới hạn về độ trễ, tỷ lệ lỗi.
* Hoàn thiện worklog, tài liệu workshop, báo cáo song ngữ, sơ đồ kiến trúc và video demo dự án.

### Cần cải thiện

* Tối ưu độ trễ P95, connection pool, truy vấn cơ sở dữ liệu và cấu hình ECS để hệ thống đáp ứng tốt hơn khi tải tăng.
* Bổ sung test tự động cho các tình huống xử lý đồng thời, timeout, retry, service gián đoạn và kiểm tra invariant sau kiểm thử.
* Chuẩn hóa quy trình triển khai bằng Infrastructure as Code và CI/CD thay vì phụ thuộc nhiều vào thao tác thủ công trên AWS Console.
* Nâng cao kiến thức về bảo mật production như quản lý secret, TLS, IAM theo nguyên tắc quyền tối thiểu và kết nối private giữa các dịch vụ.
* Cải thiện kỹ năng giao tiếp kỹ thuật, trình bày bằng tiếng Anh, quản lý thời gian và phối hợp theo quy trình Git/Agile.

### Định hướng phát triển

Sau chương trình, tôi sẽ tiếp tục tối ưu hiệu năng của dự án, hoàn thiện bộ kiểm thử tự động và chuẩn hóa quá trình triển khai. Đồng thời, tôi sẽ học sâu hơn về AWS, DevOps, hệ thống phân tán, observability và Infrastructure as Code để có thể phát triển dự án từ mô hình thử nghiệm thành một hệ thống có khả năng vận hành ổn định hơn.
