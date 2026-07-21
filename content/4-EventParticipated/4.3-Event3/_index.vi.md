---
title: "Event 3"
date: 2026-06-06
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---
# Bài thu hoạch “FCJ Community Day - From Zero to Cloud Hero”

### Tổng Quan Sự Kiện

Sự kiện cung cấp góc nhìn thực tế về nhiều mảng công nghệ đang được sử dụng trong hệ thống hiện đại: giao tiếp thời gian thực bằng WebSocket, đóng gói ứng dụng với Docker, GraphRAG trên AWS, phát hiện tấn công mạng bằng Machine Learning và lộ trình phát triển từ IT Helpdesk đến Modern DevOps.

### Nội Dung Kỹ Thuật Nổi Bật

#### 1. Xây dựng kết nối thời gian thực bằng Serverless WebSocket

**Nguyễn Quốc Bảo** trình bày chủ đề **“Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets”**. Kiến trúc sử dụng **Amazon API Gateway WebSocket, AWS Lambda** và **Amazon DynamoDB** để quản lý kết nối, trạng thái chờ và ghép cặp người chơi.

Các route như `$connect`, `$disconnect` và `$default` được tách riêng để xử lý vòng đời kết nối và dữ liệu trò chơi. Giải pháp phù hợp với các ứng dụng cần giao tiếp hai chiều nhưng không muốn duy trì máy chủ liên tục. Với trò chơi yêu cầu đồng bộ tần suất cao và mô phỏng vật lý phức tạp, **AWS GameLift** được đề cập như một hướng phát triển phù hợp hơn.

#### 2. Tối ưu quy trình triển khai bằng Docker

**Bảo Huỳnh** giải thích sự khác nhau giữa máy ảo và container. Docker đóng gói ứng dụng cùng các thư viện phụ thuộc nhưng dùng chung hệ điều hành của máy chủ, nhờ đó khởi động nhanh và tiêu thụ ít tài nguyên hơn VM.

Nội dung quan trọng gồm:

- Cách image được tạo từ nhiều layer chỉ đọc;
- Container bổ sung một layer có thể ghi khi chạy;
- Tận dụng cache để giảm thời gian build;
- Quản lý image, container, network và volume;
- Dùng Docker Compose để chạy nhiều thành phần của ứng dụng.

#### 3. Bổ sung quan hệ ngữ cảnh bằng GraphRAG

**Việt Phát** trình bày cách GraphRAG khắc phục hạn chế của RAG truyền thống. Thay vì chỉ tìm kiếm đoạn văn có vector tương đồng, GraphRAG tổ chức dữ liệu thành các **node** và **edge**, nhờ đó mô hình có thể nhận biết mối liên hệ giữa nhiều thực thể nằm ở các nguồn khác nhau.

Hai hướng triển khai được giới thiệu:

- Dùng **Amazon Bedrock Knowledge Bases** kết hợp **Amazon Neptune Analytics** cho mô hình được quản lý;
- Xây dựng pipeline tùy chỉnh bằng **LlamaIndex**, Python và truy vấn Cypher khi cần kiểm soát chi tiết hơn.

#### 4. Phát hiện xâm nhập bằng AWS WAF và Machine Learning

**Lê Hoàng Gia Đại** trình bày mô hình **Network Intrusion Detection System** kết hợp lớp bảo vệ theo quy tắc của **AWS WAF** với khả năng phát hiện bất thường của Machine Learning. Dữ liệu mạng được thu thập, làm sạch, cân bằng và sử dụng để so sánh nhiều thuật toán khác nhau.

Mô hình **LightGBM** được lựa chọn nhờ kết quả đánh giá tốt. Trong kiến trúc AWS, dữ liệu có thể được chuyển qua **Amazon Kinesis Data Firehose**, lưu vào **Amazon S3**, xử lý bằng **AWS Lambda** và gửi cảnh báo qua **Amazon SNS**. Cách kết hợp này giúp hệ thống vừa chặn các mẫu tấn công đã biết, vừa có khả năng nhận diện hành vi bất thường mới.

#### 5. Lộ trình từ IT Helpdesk đến Modern DevOps

**Trần Trung Vinh** chia sẻ quá trình phát triển nghề nghiệp từ IT Helpdesk đến quản trị hệ thống và DevOps. Kinh nghiệm hỗ trợ người dùng, xử lý sự cố và phân tích nguyên nhân gốc rễ là nền tảng quan trọng trước khi tiếp cận hạ tầng on-premises, Linux, VMware, Cloud và tự động hóa.

Lộ trình được hệ thống thành các nhóm kỹ năng:

- Linux và Networking;
- Git và quản lý mã nguồn;
- Nền tảng Cloud;
- Docker và container;
- CI/CD;
- Infrastructure as Code với Terraform;
- Điều phối hệ thống;
- Monitoring và Observability.

### Kiến Thức Và Kỹ Năng Tiếp Thu

- Hiểu luồng hoạt động của API Gateway WebSocket, Lambda và DynamoDB trong ứng dụng real-time.
- Nắm được nguyên lý image layer, container layer và build cache của Docker.
- Phân biệt RAG dựa trên vector với GraphRAG có khả năng biểu diễn quan hệ dữ liệu.
- Có thêm góc nhìn về kiến trúc bảo mật nhiều lớp kết hợp WAF, luồng dữ liệu và mô hình học máy.
- Xác định rõ hơn các kỹ năng cần thiết cho lộ trình Cloud và DevOps.
- Nhận thấy kinh nghiệm xử lý sự cố thực tế có giá trị lớn trong quá trình phát triển nghề nghiệp.

### Khả Năng Áp Dụng

- Dùng Docker để đóng gói các service và đảm bảo môi trường triển khai nhất quán.
- Tối ưu Dockerfile bằng cách sắp xếp layer hợp lý và tái sử dụng build cache.
- Nghiên cứu WebSocket cho các chức năng cần cập nhật trạng thái theo thời gian thực.
- Tìm hiểu AWS WAF, CloudWatch và SNS để tăng khả năng giám sát và cảnh báo.
- Tiếp tục rèn luyện Linux, Networking, CI/CD và Infrastructure as Code theo lộ trình DevOps.

### Đánh Giá Sau Sự Kiện

Điểm nổi bật của chương trình là sự đa dạng nhưng vẫn có tính liên kết giữa phát triển ứng dụng, AI, bảo mật và vận hành. Các nội dung đều cho thấy một hệ thống tốt không chỉ cần mã nguồn đúng, mà còn phải có kiến trúc phù hợp, quy trình triển khai nhất quán, khả năng quan sát và cơ chế bảo vệ. Câu chuyện nghề nghiệp cuối chương trình cũng khẳng định rằng lộ trình phát triển được tạo nên từ việc học nền tảng và giải quyết các vấn đề thực tế từng bước một.

### Một số hình ảnh khi tham gia sự kiện
![Event 3](/images/b3-1.jpg)

[//]: # (![Event 3]&#40;/images/b8.jpg&#41;)

[//]: # (![Event 3]&#40;/images/b9.jpg&#41;)

[//]: # (![Event 3]&#40;/images/b10.jpg&#41;)

> **FCJ Community Day - From Zero to Cloud Hero** giúp kết nối kiến thức về WebSocket, Docker, GraphRAG, an ninh mạng và DevOps thành một định hướng học tập thực tế, có thể áp dụng cho các dự án đám mây hiện đại.
