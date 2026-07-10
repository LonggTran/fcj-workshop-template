---
title : "Create SNS Topic & Subscribe Email"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.8.1. </b> "
---

We will set up an AWS SNS Topic to send out email alerts when our threshold is breached.

---

### Steps:

1. Search for and open the **Simple Notification Service (SNS)** service on the AWS Console.
2. Select **Topics** in the left menu -> Click **Create topic**.
3. Configure the Topic:
   - **Type**: Select **Standard**.
   - **Name**: `pg-alerts`.
   - Click **Create topic** at the bottom.
4. **Subscribe your Email:**
   - In the detail view of `pg-alerts`, click **Create subscription** in the pane below.
   - **Protocol**: Select **Email**.
   - **Endpoint**: Enter your **real personal email address**.
   - Click **Create subscription**.
5. **Confirm Email Subscription:**
   - Open your email inbox, look for a mail sent by AWS Notifications with the subject *"AWS Notification - Subscription Confirmation"*.
   - Open the email and click the **Confirm Subscription** link.

![Confirm Email SNS](/images/5-Workshop/5.8-CloudWatch-Alarm/5.8.1-sns_confirm.png)
