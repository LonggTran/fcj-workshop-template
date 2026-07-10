---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
### Mục tiêu tuần 3:

* Nghiên cứu giải pháp điện toán đám mây và kiến trúc lưu trữ dữ liệu trên máy chủ ảo Amazon EC2.
* Nghiên cứu cơ chế vận hành máy chủ đa nền tảng và giải pháp kiểm soát đặc quyền tầng mạng qua AWS IAM.
* Nghiên cứu phương pháp luận định danh tài nguyên và giải pháp gom nhóm hạ tầng tập trung trên AWS.
* Nghiên cứu mô hình giám sát tập trung, phân tích dữ liệu nhật ký hệ thống và cơ chế tự động hóa cảnh báo trên AWS.
* Nghiên cứu giải pháp cân bằng tải dữ liệu và cơ chế tự động co giãn hạ tầng máy chủ trên AWS.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nghiên cứu kiến trúc máy chủ ảo Amazon EC2 và các cấu phần quản trị tài nguyên đi kèm<br>&emsp; + Phân tích đặc tính các dòng Instance Type, cấu trúc tạo ảnh đĩa AMI, cơ chế mã hóa bảo mật với Key Pair và mã kịch bản tự động hóa User Data<br>&emsp; + Tìm hiểu mô hình vận hành và phân phối dữ liệu cấu trúc dạng Metadata hệ thống<br>&emsp; + Khảo sát nguyên lý co giãn hạ tầng tự động thông qua giải pháp Auto Scaling Group<br>- Nghiên cứu các giải pháp lưu trữ và dịch vụ di trú đám mây<br>&emsp; + Phân biệt bản chất kỹ thuật của phân vùng đĩa khối EBS, bộ nhớ tạm thời Instance Store và hệ thống tệp tin dùng chung EFS/FSx<br>&emsp; + Khảo sát mô hình điện toán tối giản với AWS Lightsail và cơ chế dịch chuyển máy chủ diện rộng thông qua AWS Application Migration Service (MGN)                                                                                             | 04/05/2026   | 04/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Nghiên cứu kiến trúc máy chủ ảo EC2 đa hệ điều hành và các giải pháp quản trị vòng đời tài nguyên<br>&emsp; + Phân tích cơ chế điều phối luồng mạng cho các phân vùng Linux/Windows và phương thức kết nối SSH/RDP an toàn<br>&emsp; + Tìm hiểu quy trình tối ưu hiệu năng thông qua kỹ thuật chuyển đổi dòng máy chủ và quản trị ảnh đĩa hệ thống AMI/Snapshot<br>&emsp; + Khảo sát phương pháp luận xử lý sự cố mất khóa bảo mật bằng mã kịch bản User Data và hệ thống Systems Manager<br>&emsp; + Nghiên cứu mô hình thiết lập môi trường chạy ứng dụng Node.js, LAMP Stack và XAMPP trên đa nền tảng hệ điều hành<br>- Khảo sát giải pháp kiểm soát đặc quyền và quản trị chính sách bảo mật thông qua AWS IAM<br>&emsp; + Phân tích cơ chế giới hạn phạm vi khởi tạo tài nguyên theo vùng địa lý (Region) và các dòng máy chủ chuyên biệt<br>&emsp; + Tìm hiểu phương thức ràng buộc quyền hạn xóa dữ liệu dựa trên địa chỉ IP doanh nghiệp và các điều kiện mốc thời gian cụ thể                                            | 05/05/2026   | 05/05/2026      | <https://000004.awsstudygroup.com/> |
| 4   | - Nghiên cứu cơ chế định danh tài nguyên bằng hệ thống phân loại thẻ AWS Tags<br>&emsp; + Phân tích cấu trúc phân cấp, quy chuẩn đặt tên và vòng đời của các thẻ định danh<br>&emsp; + Tìm hiểu phương pháp luận lọc, truy vấn và phân loại máy chủ tự động dựa trên siêu dữ liệu của thẻ<br>&emsp; + Khảo sát mô hình tự động hóa dán nhãn đồng bộ cho các tài nguyên liên đới ngay tại thời điểm khởi tạo<br>- Khảo sát giải pháp quản lý hạ tầng tập trung thông qua AWS Resource Groups<br>&emsp; + Nghiên cứu cơ chế gom cụm tự động tài nguyên dựa trên các điều kiện lọc và quy tắc thẻ định danh<br>&emsp; + Phân tích tư duy chuyển đổi mô hình từ quản trị đơn lẻ từng máy chủ sang quản lý hệ thống theo dự án và môi trường | 06/05/2026   | 06/05/2026      | <https://000027.awsstudygroup.com/> |
| 5   | - Nghiên cứu giải pháp đo lường hiệu năng và quản trị nhật ký thông qua Amazon CloudWatch<br>&emsp; + Phân tích bản chất kỹ thuật của các chỉ số Metrics, phương pháp luận ứng dụng các biểu thức toán học và cấu trúc nhãn động để trực quan hóa dữ liệu<br>&emsp; + Tìm hiểu mô hình thu thập, lưu trữ tập trung dữ liệu nhật ký CloudWatch Logs và cơ chế tối ưu hóa truy vấn thông qua công cụ Logs Insights<br>&emsp; + Khảo sát nguyên lý hoạt động của bộ lọc dữ liệu văn bản thành chỉ số định lượng thông qua CloudWatch Metrics Filters<br>- Khảo sát kiến trúc tự động hóa cảnh báo rủi ro và quản trị tập trung<br>&emsp; + Nghiên cứu cơ chế thiết lập ngưỡng giới hạn an toàn và nguyên lý kích hoạt hành động tự động của CloudWatch Alarms<br>&emsp; + Tìm hiểu mô hình tích hợp dịch vụ thông báo thông tin và phương pháp luận thiết kế bảng điều khiển trung tâm CloudWatch Dashboards                  | 07/05/2026   | 07/05/2026      | <https://000008.awsstudygroup.com/> |
| 6   | - Nghiên cứu giải pháp phân phối lưu lượng và chuẩn hóa khuôn mẫu hạ tầng<br>&emsp; + Phân tích bản chất kỹ thuật của việc đóng gói ảnh đĩa hệ thống AMI và cấu trúc khuôn mẫu khởi tạo Launch Template<br>&emsp; + Tìm hiểu mô hình vận hành, cơ chế kiểm tra sức khỏe của bộ phận điều phối Application Load Balancer và nhóm đích Target Group<br>- Khảo sát nguyên lý vận hành của hệ thống co giãn máy chủ tự động Auto Scaling Group<br>&emsp; + Nghiên cứu cơ chế điều chỉnh tài nguyên thủ công và giải pháp thiết lập lịch trình co giãn cố định định kỳ<br>&emsp; + Phân tích thuật toán co giãn động dựa trên các chỉ số hiệu năng thực tế của hệ thống<br>&emsp; + Khảo sát mô hình phân tích dữ liệu lịch sử và đọc hiểu biểu đồ dự báo xu hướng để chuẩn bị trước tài nguyên hạ tầng                                                                                         | 08/05/2026   | 08/05/2026      | <https://000006.awsstudygroup.com/> |

### Kết quả đạt được tuần 3:

* Thấu hiểu kiến trúc máy chủ ảo đa nền tảng và phương thức lưu trữ:
  * Nắm vững nguyên lý cấu hình hạ tầng tính toán dựa trên việc tối ưu Instance Type, ảnh đĩa hệ thống (AMI) và cấu trúc dữ liệu cấu hình Metadata/User Data trên cả hai hệ điều hành Linux và Windows Server.
  * Phân biệt rõ bản chất kỹ thuật, tốc độ và độ bền vững giữa các giải pháp lưu trữ khối EBS (bao gồm EBS Snapshot Archive tối ưu chi phí), bộ nhớ đệm cục bộ Instance Store và hệ thống chia sẻ tệp tin quy mô lớn EFS/FSx.
  * Khảo sát các mô hình kiến trúc chạy ứng dụng (Node.js/LAMP/XAMPP) cùng kỹ thuật xử lý sự cố cứu hộ quyền truy cập từ xa (Zero-Key Recovery) thông qua tính năng cấu hình nâng cao.

* Nghiên cứu giải pháp bảo mật nâng cao và cơ chế kiểm soát đặc quyền (AWS IAM):
  * Thấu hiểu tư duy quản lý truy cập Zero-Trust, phân tầng bảo mật nâng cao và nguyên lý giao tiếp nội bộ khép kín qua Systems Manager mà không phụ thuộc vào khóa bảo mật truyền thống.
  * Phân tích sâu các điều kiện chính sách của IAM (IAM Conditions) nhằm ràng buộc quyền hạn khởi tạo và ngăn chặn rủi ro xóa tài nguyên theo vùng địa lý, loại đĩa lưu trữ, địa chỉ IP doanh nghiệp và khung thời gian.

* Thấu hiểu chiến lược định danh và quản lý hạ tầng tập trung (Tags & Resource Groups):
  * Nắm vững phương pháp luận xây dựng bộ quy chuẩn thẻ định danh hệ thống (Owner, Environment) và cơ chế tự động hóa dán nhãn đồng bộ để phục vụ mục tiêu tối ưu hóa quy trình tra cứu tài nguyên.
  * Khảo sát mô hình vận hành của Resource Groups giúp gom cụm tự động tài nguyên, chuyển đổi tư duy từ quản trị vi mô sang quản lý vĩ mô tập trung theo dự án hoặc môi trường (Dev/Staging/Production).

* Thấu hiểu kiến trúc đo lường và phương pháp luận phân tích nhật ký (Amazon CloudWatch):
  * Nắm vững nguyên lý bóc tách dữ liệu hiệu năng nhờ việc ứng dụng các biểu thức toán học và cơ chế định danh nhãn động; thành thạo tư duy bóc tách chuỗi sự kiện lỗi bằng ngôn ngữ truy vấn trong Logs Insights và Metric Filters.
  * Phân tích luồng liên kết thông tin tự động giữa hệ thống giám sát chỉ số và cơ chế kích hoạt thông báo tự động (CloudWatch Alarms) khi phát hiện bất thường, kết hợp tích hợp dữ liệu trực quan về một giao diện Dashboard duy nhất.

* Nghiên cứu giải pháp điều phối tải và co giãn quy mô hệ thống (ELB & Auto Scaling Group):
  * Phân tích sâu nguyên lý điều phối tải tầng ứng dụng (ALB) kết hợp chuẩn hóa khuôn mẫu cấu hình khởi tạo (Launch Template) để đảm bảo tính nhất quán và sẵn sàng cao cho hệ thống.
  * Thấu hiểu toàn diện các cơ chế co giãn hạ tầng (thủ công, theo lịch trình cố định, co giãn động và co giãn dự báo dựa trên dữ liệu lịch sử) nhằm cân bằng tối ưu giữa hiệu năng thực tế của người dùng và rủi ro tài chính đám mây.
  * Khảo sát tư duy điện toán trọn gói của AWS Lightsail cho hệ thống nhỏ và quy trình di trú máy chủ diện rộng từ hạ tầng vật lý lên đám mây bằng giải pháp AWS MGN.