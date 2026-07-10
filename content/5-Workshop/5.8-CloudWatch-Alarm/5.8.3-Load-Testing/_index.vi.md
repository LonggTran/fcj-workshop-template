---
title : "Simulate Load & Kiểm thử Alarm"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.8.3. </b> "
---

Chúng ta sẽ giả lập gửi lượng lớn requests để kích hoạt **CloudWatch Alarm** và nhận **Email notification**.

---

### Bước 1: Kích hoạt giả lập tải
Chạy PowerShell Script từ máy tính cá nhân (thay thế địa chỉ DNS của ALB của bạn):
```powershell
$url = 'http://pg-alb-504838152.ap-southeast-1.elb.amazonaws.com/'; Write-Host "Sending 200 requests to $url..."; for ($i = 1; $i -le 200; $i++) { try { $r = Invoke-WebRequest -Uri $url -UseBasicParsing -TimeoutSec 2; Write-Host "Request $i - OK" } catch { Write-Host "Request $i - Fail" } }
```

---
![gửi request từ PowerShell cục bộ](/images/h58.png)
* Lưu ý: Bạn cũng có thể dùng các công cụ benchmark khác để gửi requests.

### Bước 2: Kiểm thử kết quả
1. Chờ khoảng 1-2 phút.
2. Kiểm tra **CloudWatch Alarm** `pg-alb-high-request-alarm`: Status sẽ chuyển sang màu đỏ báo **`In alarm`**.
![CloudWatch Alarm In Alarm](/images/h59.png)
3. Mở hòm thư email của bạn: Bạn sẽ nhận được email cảnh báo tự động từ AWS SNS.

![CloudWatch Alarm In Alarm](/images/h60.png)
