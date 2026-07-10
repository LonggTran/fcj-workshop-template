---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:

* Nghiên cứu cơ chế kiểm soát ranh giới phân quyền tối đa và giải pháp ngăn chặn rủi ro leo thang đặc quyền trong AWS IAM.
* Nghiên cứu cơ chế mã hóa lưu trữ bằng AWS KMS và giải pháp giám sát, truy vấn kiểm toán dữ liệu tự động.
* Nghiên cứu mô hình kiến trúc, cơ chế vận hành và phương pháp luận tối ưu hóa các dịch vụ cơ sở dữ liệu trên AWS.
* Nghiên cứu hệ thống ngôn ngữ SQL trên nền tảng W3Schools phục vụ công tác quản trị cơ sở dữ liệu quan hệ.
* Nghiên cứu cơ chế vận hành, kiến trúc kết nối bảo mật đa tầng và giải pháp dự phòng dữ liệu trên Amazon RDS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nghiên cứu cơ chế ranh giới phân quyền trong hệ thống quản trị định danh đám mây<br>&emsp; + Phân tích bản chất kỹ thuật của chính sách giới hạn đặc quyền tối đa (Permission Boundary) và thuật toán giao thoa quyền hạn khi đánh giá policy<br>&emsp; + Tìm hiểu mô hình áp đặt ranh giới lên các thực thể IAM User nhằm kiểm soát chặt chẽ các chính sách ủy quyền diện rộng<br>- Khảo sát giải pháp phòng chống lỗ hổng leo thang đặc quyền và quản trị phân vùng địa lý<br>&emsp; + Nghiên cứu nguyên lý bóc tách nguy cơ lạm dụng quyền hạn (Privilege Escalation) của các tài khoản định danh cấp cơ sở<br>&emsp; + Phân tích phương pháp luận thiết lập khối điều kiện ràng buộc khu vực địa lý (Regions) để giới hạn phạm vi quản trị thực thi tài nguyên | 25/05/2026   | 25/05/2026      | <https://000030.awsstudygroup.com/>       |
| 3   | - Nghiên cứu giải pháp bảo mật mã hóa dữ liệu ở trạng thái lưu trữ đám mây<br>&emsp; + Phân tích bản chất kỹ thuật của phương thức mã hóa tự động trên Amazon S3 sử dụng khóa mã hóa do khách hàng tự quản lý (SSE-KMS)<br>&emsp; + Tìm hiểu mô hình kiểm soát đặc quyền truy cập, nguyên lý chặn lọc dữ liệu công khai và giải pháp ủy quyền chia sẻ thông tin giới hạn thời gian qua liên kết ký trước (Presigned URL)<br>- Khảo sát kiến trúc thu thập nhật ký sự kiện và phương pháp luận truy vấn kiểm toán hệ thống nâng cao<br>&emsp; + Nghiên cứu cơ chế ghi nhận tự động các chuỗi thao tác dữ liệu (Data Events) theo thời gian thực của dịch vụ AWS CloudTrail<br>&emsp; + Phân tích phương pháp luận tích hợp cấu trúc log văn bản phi cấu trúc vào công cụ truy vấn phi máy chủ Amazon Athena dựa trên ngôn ngữ SQL chuẩn | 26/05/2026   | 26/05/2026      | <https://000033.awsstudygroup.com/>       |
| 4   | - Nghiên cứu phương pháp luận phân loại và giải pháp cơ sở dữ liệu quan hệ chuyên sâu<br>&emsp; + Phân tích bản chất các mô hình dữ liệu và định hình tư duy lựa chọn cấu trúc lưu trữ phục vụ bài toán hạ tầng ứng dụng<br>&emsp; + Tìm hiểu mô hình quản trị tự động của dịch vụ Amazon RDS và phân tích kiến trúc điện toán đám mây nguyên bản (Cloud-native) của Amazon Aurora<br>- Khảo sát giải pháp phân tích dữ liệu quy mô lớn và cơ chế lưu trữ đệm tối ưu hiệu năng<br>&emsp; + Phân biệt bản chất kỹ thuật giữa hai hệ thống xử lý giao dịch trực tuyến OLTP và phân tích trực tuyến OLAP thông qua kho dữ liệu Amazon Redshift<br>&emsp; + Nghiên cứu nguyên lý hoạt động của bộ nhớ đệm trong một dòng đời truy vấn (In-memory Caching) thông qua dịch vụ Amazon ElastiCache dựa trên hai nền tảng Redis và Memcached | 27/05/2026   | 27/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Khảo sát và hệ thống hóa cú pháp ngôn ngữ cấu trúc dữ liệu tiêu chuẩn trên nền tảng W3Schools<br>&emsp; + Phân tích bản chất kỹ thuật và phương pháp luận bóc tách dữ liệu của nhóm lệnh truy vấn dữ liệu chuyên sâu<br>&emsp; + Nghiên cứu mô hình logic và cơ chế tác động của nhóm lệnh thao tác dữ liệu DML và định nghĩa dữ liệu DDL<br>- Nghiên cứu các giải pháp xử lý dữ liệu phức hợp trên môi trường học thuật trực tuyến<br>&emsp; + Khảo sát thuật toán liên kết bảng đa tầng, cơ chế gom cụm và thiết lập điều kiện ràng buộc nhóm dữ liệu chuyên biệt trên W3Schools<br>&emsp; + Chuẩn hóa các bộ kịch bản cấu trúc SQL làm bước đệm kỹ thuật cho việc tối ưu hóa hiệu năng truy vấn trên môi trường Amazon RDS | 28/05/2026   | 28/05/2026      | <https://www.w3schools.com/sql/>          |
| 6   | - Nghiên cứu kiến trúc hạ tầng và cơ chế liên thông kết nối an toàn cho Amazon RDS<br>&emsp; + Phân tích giải pháp thiết lập phân vùng mạng nội bộ, cấu trúc định tuyến liên tầng và cơ chế lọc traffic của hệ thống tường lửa Security Group dành cho máy chủ và cơ sở dữ liệu<br>&emsp; + Tìm hiểu mô hình tích hợp, cơ chế giao tiếp qua Endpoint mã hóa và phương thức quản lý thông tin định danh bảo mật giữa ứng dụng và thực thể dữ liệu đám mây<br>- Khảo sát phương pháp luận quản trị vận hành và chiến lược bảo vệ an toàn thông tin<br>&emsp; + Nghiên cứu nguyên lý tự động hóa quy trình sao lưu (Automated Backups) và cơ chế khởi tạo bản sao chụp trạng thái hệ thống cố định (Manual Snapshots)<br>&emsp; + Phân tích quy trình phục hồi dữ liệu theo mốc thời gian (Point-In-Time Recovery) nhằm đảm bảo tính toàn vẹn tài nguyên trước các rủi ro hệ thống | 29/05/2026   | 29/05/2026      | <https://000005.awsstudygroup.com/>       |

### Kết quả đạt được tuần 6:

* Thấu hiểu kiến trúc ranh giới phân quyền và cơ chế phòng chống leo thang đặc quyền (IAM Permission Boundary):
  * Nắm vững phương pháp luận xây dựng chính sách giới hạn đặc quyền tối đa (Maximum Permissions), thấu hiểu nguyên lý vận hành của bộ lọc giao thoa giúp ghi đè và cô lập hiệu quả các chính sách cấp quyền mở rộng (Full Access).
  * Phân tích sâu hệ thống logic của AWS IAM khi kết hợp đa tầng chính sách (Identity-based Policies và Permission Boundaries) nhằm xác định chính xác ranh giới thực thi hành động hợp pháp của tài khoản, triệt tiêu nguy cơ lạm dụng hoặc leo thang đặc quyền (Privilege Escalation).
  * Khảo sát giải pháp bóc tách quyền hạn dựa trên ngữ cảnh phân vùng địa lý (Regions), ngăn chặn hiệu quả các tác vụ quản trị nằm ngoài phạm vi quy định doanh nghiệp.

* Thấu hiểu kiến trúc mã hóa lưu trữ nâng cao và giải pháp phân tích nhật ký kiểm toán (CloudTrail & Athena):
  * Nắm vững nguyên lý bảo mật phía máy chủ đám mây (SSE-KMS) của Amazon S3 và cơ chế phân phối danh tính tạm thời bằng phương pháp ký mã hóa URL (Presigned URL) có ràng buộc thời hiệu nghiêm ngặt.
  * Thấu hiểu giải pháp kiến trúc ghi vết toàn diện của AWS CloudTrail, bóc tách luồng sự kiện cấu hình (Management Events) và sự kiện thao tác dữ liệu (Data Events) trên các phân vùng lưu trữ theo thời gian thực.
  * Phân tích mô hình truy vấn phi máy chủ trong Amazon Athena, làm chủ phương pháp luận cấu trúc hóa kho dữ liệu nhật ký văn bản thô thành bảng quan hệ logic bằng câu lệnh SQL tiêu chuẩn phục vụ công tác điều tra sự cố bảo mật.

* Hệ thống hóa toàn diện tư duy phân loại và kiến trúc dịch vụ cơ sở dữ liệu (Database Services):
  * Nắm vững phương pháp luận bóc tách đặc tính dữ liệu để định hình tư duy chuyển đổi linh hoạt giữa các nhóm giải pháp dữ liệu quan hệ (RDBMS), phi quan hệ (NoSQL), bộ nhớ đệm (In-memory) và kho dữ liệu tập trung (OLAP).
  * Thấu hiểu bản chất kiến trúc tách biệt giữa tầng tính toán (Compute) và tầng lưu trữ (Storage) của Amazon Aurora, nắm trọn nguyên lý tự động phục hồi và nhân bản dữ liệu đa vùng sẵn sàng nhằm tối ưu hóa hiệu năng hệ thống.
  * Phân biệt rõ ràng cấu trúc lưu trữ dạng dòng phục vụ OLTP và dạng cột phục vụ OLAP trong Amazon Redshift quy mô Petabyte; thấu hiểu cơ chế In-memory Caching của Amazon ElastiCache (đối chiếu hai công cụ Redis và Memcached) để tối ưu hóa triệt để độ trễ (Latency) cho tầng ứng dụng.

* Chuẩn hóa phương pháp luận bóc tách dữ liệu thông qua nền tảng học thuật W3Schools:
  * Hoàn thành quy trình khảo sát, nghiên cứu tư duy thiết kế logic và bản chất vận hành của nhóm lệnh định nghĩa dữ liệu (DDL) cùng nhóm lệnh thao tác dữ liệu (DML) được định chuẩn theo tài liệu chuyên ngành của W3Schools.
  * Phân tích sâu cơ chế thực thi của các mệnh đề truy vấn phức hợp (JOIN, GROUP BY, HAVING), thấu hiểu thuật toán xử lý và tối ưu hóa tài nguyên phần cứng khi liên kết dữ liệu đa tầng trên quy mô lớn.

* Thấu hiểu kiến trúc vận hành, bảo mật kết nối và chiến lược dự phòng trên Amazon RDS:
  * Nắm vững phương pháp luận thiết lập hàng rào bảo mật tách biệt giữa tầng ứng dụng (EC2) và tầng dữ liệu thông qua quy tắc cấu hình hệ thống tường lửa (Security Groups) theo nguyên tắc đặc quyền tối thiểu.
  * Phân tích sâu luồng giao tiếp mạng nội bộ, cơ chế định danh điểm cuối (Endpoint) và phương thức liên kết biến môi trường bảo mật giữa máy chủ ứng dụng và thực thể dữ liệu đám mây.
  * Thấu hiểu bản chất kỹ thuật và sự khác biệt giữa hai cơ chế sao lưu tự động (Automated Backups) lưu vết hàng ngày với sao lưu thủ công (Manual Snapshots) cố định; thấu hiểu sâu giải pháp khôi phục dữ liệu theo mốc thời gian (Point-In-Time Recovery - PITR) dựa trên hệ thống nhật ký giao dịch (Transaction Logs) để ứng phó rủi ro hệ thống.