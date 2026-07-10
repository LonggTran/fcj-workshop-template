---
title : "Simulate Traffic Load & Verify Email Alerts"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.8.3. </b> "
---

We will simulate traffic overload to trigger the alarm and verify that the email is sent.

---

### Step 1: Simulate Load
Choose one of the following methods:

* **Method 1: Web Interface Burst:**
  - Access your website via the ALB DNS.
  - Go to the **Rate Limiter Demo** tab.
  - Set **Burst Requests** = `150`, **Delay** = `10ms`. Click **Trigger Request Burst**.

* **Method 2: Local PowerShell Command:**
  - Run this command in your local PowerShell terminal (replace the DNS URL):
```powershell
$url = 'http://pg-alb-504838152.ap-southeast-1.elb.amazonaws.com/'; Write-Host "Sending 200 requests to $url..."; for ($i = 1; $i -le 200; $i++) { try { $r = Invoke-WebRequest -Uri $url -UseBasicParsing -TimeoutSec 2; Write-Host "Request $i - OK" } catch { Write-Host "Request $i - Fail" } }
```

![Send load-test requests from local PowerShell](/images/h58.png)

---

### Step 2: Verify Alerts
1. Wait 1-2 minutes.
2. Check the CloudWatch Alarms page: the status of **`pg-alb-high-request-alarm`** will become red (**`In alarm`**).

![CloudWatch alarm in the In alarm state](/images/h59.png)

3. Check your email inbox: You should find an alert message from AWS SNS.

![SNS alarm notification received by email](/images/h60.png)
