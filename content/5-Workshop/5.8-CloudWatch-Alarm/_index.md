---
title : "CloudWatch Alarm & SNS Email Notification"
date : 2024-01-01 
weight : 8
chapter : false
pre : " <b> 5.8. </b> "
---

In this section, we will implement an automated real-time Email alert system using **Amazon SNS** combined with a **Amazon CloudWatch Alarm** to detect when the HTTP request traffic arriving at our Application Load Balancer exceeds a safe threshold.

#### Contents:

1. [Create SNS Topic & Subscribe Email](5.8.1-Create-SNS/)
2. [Create CloudWatch Alarm on ALB RequestCount](5.8.2-Create-Alarm/)
3. [Simulate Traffic Load & Verify Email Alerts](5.8.3-Load-Testing/)
