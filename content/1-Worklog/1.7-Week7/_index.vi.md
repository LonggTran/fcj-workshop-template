---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:

* Hệ thống hóa, đối chiếu và củng cố toàn bộ kiến thức lý thuyết của các nhóm dịch vụ đám mây AWS đã nghiên cứu từ Tuần 1 đến Tuần 6.
* Hệ thống lại các mô hình kiến trúc mạng ảo bảo mật, cơ chế quản lý lưu trữ, phương pháp luận tối ưu hóa cơ sở dữ liệu và tự động hóa giám sát tài nguyên.
* Củng cố tư duy bảo mật Zero-Trust, phân quyền đặc quyền tối thiểu qua IAM, kiểm soát truy cập nâng cao (ABAC, Switch Role, Permission Boundary) và các tiêu chuẩn an ninh hạ tầng đám mây.
* Nghiên cứu giải quyết các điểm còn vướng mắc kỹ thuật, tổng kết tài liệu ôn tập và hoàn thiện hệ thống hóa kiến trúc để chuẩn bị cho giai đoạn tiếp theo.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Hệ thống hóa nhóm Compute & Networking (EC2, VPC):<br>&emsp; + Nghiên cứu tổng hợp cấu hình EC2, AMI, cơ chế User Data và Metadata trong tự động hóa<br>&emsp; + Rà soát cấu trúc phân luồng mạng VPC: Subnets, Route Tables, giải pháp lọc dữ liệu qua IGW/NAT Gateway<br>&emsp; + Review các giải pháp kết nối liên mạng nâng cao: VPC Peering, Transit Gateway và cơ chế truy cập qua SSM Session Manager / Endpoint | 01/06/2026   | 01/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Hệ thống hóa nhóm Storage & Content Delivery (S3, CloudFront, FSx):<br>&emsp; + Review các tính năng bảo mật bảo vệ dữ liệu, vòng đời lưu trữ và cơ chế Versioning, CRR của Amazon S3<br>&emsp; + Khảo sát giải pháp phân phối nội dung toàn cầu CDN qua hệ thống máy chủ đệm CloudFront Edge Locations<br>&emsp; + Rà soát kiến trúc hệ thống lưu trữ lai Storage Gateway và mô hình tệp tin dùng chung FSx for Windows (Multi-AZ, Deduplication, Shadow Copies) | 02/06/2026   | 02/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 4   | - Hệ thống hóa nhóm Security & Identity (IAM, KMS, AWS Organizations):<br>&emsp; + Củng cố phương pháp luận thiết lập IAM Policy, IAM Conditions và cơ chế danh tính động qua STS & IAM Role<br>&emsp; + Rà soát mô hình Switch Role, phân quyền thuộc tính ABAC qua Tags và ranh giới phân quyền Permission Boundary<br>&emsp; + Hệ thống lại cơ chế áp đặt hành lang an toàn SCP qua AWS Organizations và quản trị vòng đời khóa mã hóa KMS | 03/06/2026   | 03/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Hệ thống hóa nhóm Databases & Monitoring (RDS, CloudWatch, Security):<br>&emsp; + Đối chiếu phân loại các dòng CSDL đám mây: RDS, Aurora, Redshift và bộ nhớ đệm ElastiCache (Redis/Memcached)<br>&emsp; + Rà soát cơ chế sao lưu tự động/thủ công, Point-In-Time Recovery (PITR) của RDS<br>&emsp; + Review cơ chế CloudWatch Alarms, phân tích log qua Logs Insights và giải pháp giám sát an ninh AWS Config, Security Hub (CIS, PCI DSS)<br>&emsp; + Hệ thống hóa cú pháp ngôn ngữ cấu trúc dữ liệu tiêu chuẩn trên W3Schools | 04/06/2026   | 04/06/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Tổng kết kiến trúc và đánh giá hệ thống:<br>&emsp; + Phân tích sâu các kịch bản bóc tách sự cố nâng cao: Xử lý lỗi kết nối qua SSM, truy vấn log CloudTrail qua Athena, cấu hình Switch Role & Permission Boundary<br>&emsp; + Xây dựng sơ đồ kiến trúc tổng hợp (Knowledge Map) liên kết các nhóm dịch vụ AWS đã học<br>&emsp; + Hoàn thiện tài liệu lý thuyết, đánh giá và khắc phục các lỗ hổng kiến thức hạ tầng | 05/06/2026   | 05/06/2026      | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được tuần 7:

* Hệ thống hóa toàn diện kiến trúc hạ tầng và mạng bảo mật (Compute & Networking):
  * Nắm vững phương pháp luận tối ưu kích thước máy chủ EC2, tận dụng dữ liệu đặc tả (Metadata) và mã cấu hình (User Data) để tự động hóa quy trình triển khai ứng dụng.
  * Thấu hiểu sâu sắc cách phân luồng lưu lượng mạng ảo VPC, thiết lập chính xác các bảng định tuyến (Route Tables) và cơ chế đảm bảo các thực thể trong Private Subnet kết nối Internet an toàn một chiều thông qua NAT Gateway.
  * Củng cố nguyên lý thiết lập liên kết VPC Peering và Transit Gateway để kết nối các phân vùng mạng độc lập, đồng thời thấu hiểu giải pháp quản lý truy cập không cần khóa tĩnh dựa trên Systems Manager Session Manager.

* Củng cố kiến trúc quản trị lưu trữ nâng cao và tối ưu truyền tải (Storage & Content Delivery):
  * Khái quát hóa kỹ thuật bảo vệ dữ liệu đa tầng trên Amazon S3 (Block Public Access, Bucket Policy, KMS, Versioning) và tối ưu hóa ngân sách lưu trữ dữ liệu dựa trên chính sách vòng đời (Lifecycle Policies).
  * Phân tích giải pháp tăng tốc độ truyền tải nội dung toàn cầu, giảm thiểu độ trễ tối đa cho người dùng cuối bằng cách ứng dụng hệ thống máy chủ đệm đầu cuối (Edge Locations) của Amazon CloudFront.
  * Nắm chắc cơ chế thiết lập hệ thống tệp tin dùng chung FSx for Windows File Server với các tính năng quản trị nâng cao bao gồm chống trùng lặp dữ liệu (Data Deduplication) và lưu vết cấu trúc bóng (Shadow Copies).

* Nâng cao năng lực quản trị an ninh và kiểm soát đặc quyền tối thiểu (Security & Governance):
  * Củng cố kỹ năng thiết kế IAM Policies nâng cao, kết hợp chặt chẽ các mệnh đề ràng buộc ngữ cảnh thực tế (IAM Conditions: aws:SourceIp, aws:CurrentTime).
  * Làm chủ bản chất kỹ thuật của cơ chế Switch Role, phân quyền dựa trên thuộc tính ABAC qua hệ thống thẻ Resource Tags và áp dụng Permission Boundary để hạn chế tối đa nguy cơ leo thang đặc quyền (Privilege Escalation).
  * Hệ thống hóa quy trình quản trị hạ tầng quy mô doanh nghiệp bằng chính sách kiểm soát dịch vụ (SCP) của AWS Organizations và tự động hóa kế hoạch sao lưu tập trung qua AWS Backup kết hợp cảnh báo từ Amazon SNS.

* Thành thạo mô hình cơ sở dữ liệu đám mây và tự động hóa giám sát (Databases & Monitoring):
  * Phân biệt rõ ràng ranh giới ứng dụng giữa các dòng dữ liệu RDS/Aurora (OLTP), kho phân tích dữ liệu Redshift (OLAP) và tầng bộ nhớ đệm ElastiCache (Redis/Memcached) phù hợp với từng bài toán kiến trúc phần mềm.
  * Nắm vững cơ chế khôi phục dữ liệu theo mốc thời gian Point-In-Time Recovery (PITR) cho Amazon RDS và phương pháp thiết lập hệ thống tường lửa Security Group cô lập an toàn giữa tầng EC2 và RDS.
  * Làm chủ các công cụ phân tích CloudWatch (Log Insights, Alarms, Dashboards) và trung tâm an ninh hợp nhất Security Hub để tự động đánh giá mức độ tuân thủ tiêu chuẩn quốc tế (CIS Benchmark, PCI DSS).

* Chuẩn hóa phương pháp luận bóc tách sự cố và đồng bộ tư duy kiến trúc:
  * Thấu hiểu giải pháp kiểm toán thông qua việc cấu trúc hóa nhật ký ghi vết CloudTrail bằng công cụ truy vấn phi máy chủ Amazon Athena, hỗ trợ phân tích nhanh lịch sử hành vi hệ thống; rà soát các kịch bản chuẩn hóa cú pháp SQL từ tài liệu chuyên ngành W3Schools phục vụ quản trị RDBMS.
  * Xây dựng thành công bản đồ kiến thức tổng hợp (Knowledge Map) liên kết chặt chẽ mối quan hệ giữa các dịch vụ, hoàn thiện toàn diện khung tài liệu lý thuyết nền tảng sẵn sàng cho giai đoạn phát triển tiếp theo của dự án.