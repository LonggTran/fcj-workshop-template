---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:

* Nghiên cứu chuyên sâu về kiến trúc hạ tầng và cơ chế điều hướng dữ liệu của mạng ảo Amazon VPC.
* Thấu hiểu giải pháp quản trị hệ thống nâng cao và mô hình bảo mật Zero-Trust qua AWS Session Manager.
* Khảo sát các giải pháp kết nối liên mạng nâng cao bao gồm kết nối ngang hàng VPC Peering và trục định tuyến tập trung AWS Transit Gateway.
* Nghiên cứu cơ chế vận hành đường hầm bảo mật mã hóa thông qua giải pháp kết nối AWS Site-to-Site VPN.
* Tìm hiểu giải pháp phân giải tên miền hỗn hợp Hybrid DNS và cơ chế tích hợp định tuyến phân giải giữa AWS Route 53 với hệ thống On-premises.

### Các công việc cần triển khai trong tuần này:
| Ngày | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1   | - Tìm hiểu sâu hơn về các dịch vụ mạng trên AWS:<br>&emsp; + Amazon Virtual Private Cloud (VPC)<br>&emsp; + VPC Peering & Transit Gateway<br>&emsp; + VPN & Direct Connect<br>&emsp; + Elastic Load Balancing | 24/04/2026   | 24/04/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 2   | - Nghiên cứu kiến trúc hạ tầng và cơ chế định tuyến mạng ảo (Amazon VPC):<br>&emsp; + Phân biệt rõ vai trò của các phân vùng Subnet (Public/Private), bảng định tuyến (Route Table), cổng kết nối Internet Gateway (IGW) và NAT Gateway<br>&emsp; + Phân tích cơ chế cấp phát địa chỉ Elastic IP và giải pháp thiết lập kết nối Internet an toàn một chiều cho máy chủ nội bộ<br>&emsp; + Làm chủ phương pháp phân tích, trực quan hóa và theo dõi toàn bộ sơ đồ tài nguyên thông qua công cụ VPC Resource Map<br>- Nghiên cứu cơ chế bảo mật đa tầng và giải pháp giám sát hệ thống mạng:<br>&emsp; + Đánh giá nguyên lý hoạt động của rào chắn bảo mật hai lớp: Tường lửa máy chủ (Security Group) và bộ lọc tầng mạng (Network ACL)<br>&emsp; + Tìm hiểu mô hình truy cập máy chủ nâng cao thông qua EIC Endpoint nhằm tối ưu hóa tính an toàn và hạn chế phơi nhiễm cổng kết nối<br>&emsp; + Khảo sát cách thức ứng dụng Reachability Analyzer để kiểm tra tính hợp lệ của đường truyền và sử dụng Amazon CloudWatch để thiết lập cảnh báo | 25/04/2026   | 25/04/2026      | <https://000003.awsstudygroup.com/> |
| 3   | - Khảo sát giải pháp kết nối liên mạng và điều phối lưu lượng (Hybrid & Advanced Networking):<br>&emsp; + Thấu hiểu kiến trúc đường hầm bảo mật IPsec Tunnel cùng các thành phần đầu nối Virtual Private Gateway và Customer Gateway trong cấu hình AWS Site-to-Site VPN<br>&emsp; + Nắm bắt nguyên lý định tuyến và quy trình phân tích, khắc phục sự cố (Troubleshooting) lỗi kết nối mạng cơ bản<br>&emsp; + Tìm hiểu tư duy tự động hóa hạ tầng (IaC) thông qua công cụ AWS CloudFormation | 26/04/2026   | 26/04/2026      | <https://000003.awsstudygroup.com/> |
| 4   | - Nghiên cứu kiến trúc tổng quan và cơ chế vận hành của AWS Systems Manager Session Manager:<br>&emsp; + Phân tích mô hình quản lý và phân quyền truy cập máy chủ thông qua AWS IAM Role<br>&emsp; + Tìm hiểu giải pháp kết nối mạng nội bộ an toàn bằng cách kích hoạt các tính năng phân giải DNS ảo<br>&emsp; + Khảo sát cơ chế giao tiếp an toàn thông qua các điểm cuối dịch vụ ssm, ssmmessages và ec2messages<br>&emsp; + Nghiên cứu phương thức đồng bộ, lưu vết và bảo mật lịch sử thao tác hệ thống (Session Logs) trên Amazon S3<br>&emsp; + Tìm hiểu mô hình tối ưu hóa định tuyến đường truyền nội bộ bằng việc ứng dụng S3 Gateway Endpoint<br>&emsp; + Khảo sát nguyên lý chuyển tiếp cổng (Port Forwarding) phục vụ kết nối điều khiển giao diện đồ họa từ xa | 27/04/2026   | 27/04/2026      | <https://000058.awsstudygroup.com/> |
| 5   | - Nghiên cứu cơ chế liên kết mạng ngang hàng thông qua giải pháp AWS VPC Peering:<br>&emsp; + Phân tích mô hình cập nhật bảng định tuyến và cơ chế điều hướng dữ liệu qua kết nối ngang hàng<br>&emsp; + Tìm hiểu tính năng Cross-Peer DNS phục vụ phân giải tên miền hệ thống trong mạng liên thông<br>- Khảo sát giải pháp quản trị mạng tập trung quy mô lớn với AWS Transit Gateway:<br>&emsp; + Nghiên cứu cơ chế vận hành của trục kết nối trung tâm và các điểm liên kết tài nguyên mạng<br>&emsp; + Phân tích nguyên lý cấu hình bảng định tuyến hợp nhất để điều phối lưu lượng giữa nhiều phân vùng độc lập | 28/04/2026   | 28/04/2026      | <https://000019.awsstudygroup.com/><br><https://000020.awsstudygroup.com/> |
| 6   | - Nghiên cứu cơ chế vận hành hệ thống phân giải tên miền hỗn hợp Hybrid DNS:<br>&emsp; + Phân tích kiến trúc giả lập môi trường DNS On-premises thông qua dịch vụ AWS Managed Microsoft AD tích hợp trong vùng mạng Private<br>&emsp; + Thấu hiểu nguyên lý chuyển tiếp và định tuyến truy vấn tên miền hai chiều thông qua cấu phần Route 53 Inbound và Outbound Endpoints<br>&emsp; + Nghiên cứu phương thức cấu hình bộ quy tắc phân giải Resolver Rules phục vụ mục tiêu đồng bộ định danh liên vùng | 29/04/2026   | 29/04/2026      | <https://000010.awsstudygroup.com/> |

### Kết quả đạt được tuần 2:

* Thấu hiểu kiến trúc hạ tầng và cơ chế định tuyến mạng ảo (Amazon VPC):
  * Phân biệt rõ vai trò của các phân vùng Subnet (Public/Private), bảng định tuyến (Route Table), cổng kết nối Internet Gateway (IGW) và NAT Gateway.
  * Phân tích cơ chế cấp phát địa chỉ Elastic IP và giải pháp thiết lập kết nối Internet an toàn một chiều cho máy chủ nội bộ.
  * Làm chủ phương pháp phân tích, trực quan hóa và theo dõi toàn bộ sơ đồ tài nguyên thông qua công cụ VPC Resource Map.

* Nghiên cứu cơ chế bảo mật đa tầng và giải pháp giám sát hệ thống mạng:
  * Đánh giá nguyên lý hoạt động của rào chắn bảo mật hai lớp: Tường lửa máy chủ (Security Group) và bộ lọc tầng mạng (Network ACL) theo nguyên lý đặc quyền tối thiểu.
  * Tìm hiểu mô hình truy cập máy chủ EC2 nâng cao thông qua EIC Endpoint nhằm tối ưu hóa tính an toàn và hạn chế phơi nhiễm cổng kết nối.
  * Khảo sát cách thức ứng dụng Reachability Analyzer để kiểm tra tính hợp lệ của đường truyền và sử dụng Amazon CloudWatch (Dashboard, Metric Filters, Alarms) để theo dõi trạng thái hệ thống.

* Khảo sát giải pháp kết nối liên mạng và điều phối lưu lượng (Hybrid & Advanced Networking):
  * Thấu hiểu kiến trúc đường hầm bảo mật IPsec Tunnel cùng các thành phần đầu nối Virtual Private Gateway và Customer Gateway trong cấu hình AWS Site-to-Site VPN.
  * Nắm bắt nguyên lý định tuyến mạng, quy trình phân tích và phương pháp luận khắc phục sự cố (Troubleshooting) tương thích hệ điều hành đối với lỗi kết nối bảo mật.
  * Tìm hiểu tư duy phân phối lưu lượng thông qua bộ điều phối tải Elastic Load Balancing (ELB) nhằm tối ưu khả năng chịu lỗi và tăng tính sẵn sàng cao cho hệ thống đám mây doanh nghiệp.

* Thấu hiểu giải pháp quản trị hệ thống nâng cao qua AWS Session Manager:
  * Nắm vững nguyên lý phân quyền bảo mật qua IAM Role nhằm cho phép máy chủ ảo kết nối và tương tác an toàn với hệ thống quản lý tập trung.
  * Phân tích luồng dữ liệu khép kín trong mạng nội bộ thông qua các điểm cuối dịch vụ kết nối (VPC Endpoints ssm, ssmmessages, ec2messages) mà không cần mở public cổng kết nối truyền thống.
  * Khảo sát mô hình truy cập Zero-Trust, quy trình lưu vết nhật ký phiên làm việc (Session Logs) tích hợp đồng bộ cùng bộ lưu trữ đám mây S3 và nguyên lý chuyển tiếp cổng (Port Forwarding) điều khiển từ xa.

* Thấu hiểu kiến trúc liên kết mạng và tối ưu hóa hạ tầng (VPC Peering & Transit Gateway):
  * Khảo sát nguyên lý cập nhật bảng định tuyến để điều hướng luồng dữ liệu nội bộ trực tiếp giữa các vùng mạng độc lập qua kết nối ngang hàng và cơ chế phân giải của tính năng Cross-Peer DNS.
  * Thấu hiểu mô hình vận hành của trục kết nối trung tâm AWS Transit Gateway (Associations, Propagations, Attachments) nhằm quản lý, điều phối và phân luồng traffic quy mô lớn theo dạng hình sao (Hub-and-Spoke).

* Nghiên cứu cơ chế phân giải tên miền hỗn hợp (Hybrid DNS):
  * Khảo sát bản chất kỹ thuật của việc giả lập môi trường On-premises bằng cách triển khai dịch vụ AWS Managed Microsoft AD cô lập trong phân vùng mạng kín.
  * Nắm vững nguyên lý cấu hình luồng phân giải hai chiều, sử dụng Outbound Endpoint kết hợp Resolver Rules để đẩy truy vấn ra ngoài và ứng dụng Inbound Endpoint để tiếp nhận yêu cầu phân giải ngược lại từ On-premises vào các vùng dữ liệu Private Hosted Zone.