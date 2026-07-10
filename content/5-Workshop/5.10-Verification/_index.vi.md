---
title : "Kiểm tra & Nghiệm thu"
date : 2024-01-01 
weight : 10
chapter : false
pre : " <b> 5.10. </b> "
---

Sau khi đã triển khai toàn bộ các thành phần hạ tầng (VPC, RDS, ALB, ECS Fargate, CloudWatch Alarm, S3 Backup), đây là bước cuối cùng để kiểm thử và nghiệm thu tính đúng đắn của toàn bộ hệ thống.

---

### Bước 10.1: Kiểm tra trạng thái Target Groups của ALB
Trước khi truy cập giao diện web, chúng ta cần đảm bảo Application Load Balancer đã nhận diện và kết nối thành công đến các Fargate Tasks trong mạng Private:
1. Vào dịch vụ **EC2** -> Chọn **Target Groups** ở menu bên trái.
2. Kiểm tra trạng thái sức khỏe của cả 2 Target Groups:
   - **`tg-frontend`**: Ở tab **Targets**, danh sách IP của Task Frontend phải hiển thị trạng thái **`Healthy`** ở cổng 80.
   - **`tg-backend`**: Danh sách IP của Task Backend phải hiển thị trạng thái **`Healthy`** ở cổng 8080.

![Trạng thái Target Health của Backend](/images/h48.png)
![Trạng thái Target Health của Frontend](/images/h49.png)

---

### Bước 10.2: Truy cập và Kiểm thử Giao diện Web
1. Vào dịch vụ **EC2** -> Chọn **Load Balancers** -> Click chọn **`pg-alb`**.
2. Sao chép địa chỉ **DNS name**
3. Dán địa chỉ DNS này vào trình duyệt web để truy cập giao diện **NextGenPay**:

![DNS name](/images/h69.png)
---

### Bước 10.3: Kiểm tra Logs của Container bằng CloudWatch
Để kiểm tra xem các microservices có hoạt động ổn định và kết nối chéo thành công:
1. Vào dịch vụ **CloudWatch** trên AWS Console.
2. Chọn **Log groups** ở menu bên trái -> Click vào Log Group **`/ecs/pg-logs`** mà chúng ta đã cấu hình trong Task Definitions.
3. Kiểm tra các **Log Streams** tương ứng với từng container:
   - **`backend/...`**: Chứa nhật ký khởi chạy của ứng dụng Spring Boot (API Gateway, Account Service, Payment Service, Transaction Service). Bạn sẽ thấy log kết nối thành công tới database PostgreSQL (`pg-db`) và Redis sidecar (`127.0.0.1:6379`).
   - **`redis/...`**: Chứa nhật ký của Redis sidecar chạy cùng Task.
   - **`frontend/...`**: Chứa logs hoạt động của Nginx web server phân phối giao diện tĩnh.

---

### Bước 10.4: Xem Metrics số lượng Requests trên CloudWatch
Chúng ta có thể xem biểu đồ trực quan về lượng requests thực tế đi qua Application Load Balancer:
1. Tại dịch vụ **CloudWatch**, chọn **Metrics** -> chọn **All metrics** ở menu trái.
2. Tìm kiếm và chọn chỉ số **`RequestCount`** tương ứng với Load Balancer **`pg-alb`** (hoặc chọn tab **Graphed metrics** để tùy chỉnh thời gian hiển thị).
3. Chọn **Statistic** là **`Sum`** và **Period** là **`5 minutes`** (hoặc `1 minute`). Biểu đồ trực quan hóa số lượng requests đi qua hệ thống sẽ hiển thị tương tự hình dưới:

![Metrics](/images/h70.png)

- Biểu đồ sẽ hiển thị đường đồ thị tăng vọt lên (ví dụ lên tới hơn 250 requests) tại thời điểm bạn chạy lệnh PowerShell giả lập tải để kiểm thử CloudWatch Alarm.