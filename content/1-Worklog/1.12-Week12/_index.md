---
title: "Week 12 Worklog"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
### Week 12 Objectives:

* Complete deployment and acceptance testing of the High-Concurrency Payment Gateway on AWS.
* Monitor logs, metrics, target groups, ECS tasks, and RDS connectivity during operation.
* Run load tests and observe latency, error rate, HTTP 429 responses, and automatic scaling behavior.
* Configure CloudWatch Alarms, Amazon SNS, RDS backups, and post-test resource cleanup.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Verify the deployed system<br>&emsp; + Check ECS Task Running status and Target Group Healthy status<br>&emsp; + Access the application through the ALB DNS name<br>&emsp; + Verify connectivity among the backend, Redis sidecar, and RDS PostgreSQL<br>&emsp; + Test account, payment, and transaction flows | 06/07/2026 | 06/07/2026 | <https://000016.awsstudygroup.com/><br><https://000005.awsstudygroup.com/> |
| Tuesday | - Configure monitoring with Amazon CloudWatch<br>&emsp; + Collect CloudWatch Logs from ECS Fargate<br>&emsp; + Monitor ALB RequestCount, TargetResponseTime, HTTPCode, and ECS CPU/Memory<br>&emsp; + Create a CloudWatch Dashboard and Logs Insights queries<br>&emsp; + Analyze application and connectivity errors from centralized logs | 07/07/2026 | 07/07/2026 | <https://000008.awsstudygroup.com/> |
| Wednesday | - Configure automated alerts<br>&emsp; + Create CloudWatch Alarms based on RequestCount or CPU Utilization<br>&emsp; + Create an Amazon SNS Topic and subscribe an alert email address<br>&emsp; + Verify OK and ALARM states and email delivery<br>&emsp; + Review IAM Roles and ECS Task permissions | 08/07/2026 | 08/07/2026 | <https://000008.awsstudygroup.com/><br><https://000013.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |
| Thursday | - Run load tests and tune the system<br>&emsp; + Execute k6/JMeter with increasing virtual-user and request levels<br>&emsp; + Monitor latency, throughput, error rate, and HTTP 429 responses<br>&emsp; + Observe ALB RequestCount, ECS CPU/Memory, and task count while Auto Scaling operates<br>&emsp; + Adjust rate limits, timeouts, CPU/Memory, and scaling policies based on test results | 09/07/2026 | 09/07/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://000008.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Friday | - Complete backups, documentation, and resource cleanup<br>&emsp; + Create an RDS Snapshot and verify backup/restore procedures<br>&emsp; + Finalize deployment documentation, the architecture diagram, and bilingual worklogs<br>&emsp; + Run regression tests after configuration changes<br>&emsp; + Stop or delete unused ECS Services, ALB, NAT Gateway, RDS, and related resources to avoid additional charges | 10/07/2026 | 10/07/2026 | <https://000005.awsstudygroup.com/><br><https://000013.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |

### Week 12 Achievements:

* Completed end-to-end verification from the ALB to ECS Fargate, Redis, and RDS PostgreSQL.
* Monitored application, ALB, and ECS logs and operational metrics through CloudWatch.
* Configured CloudWatch Alarms and Amazon SNS email notifications for threshold violations.
* Ran load tests and recorded latency, throughput, error rate, HTTP 429 responses, and ECS Service Auto Scaling behavior.
* Completed the RDS Snapshot, deployment documentation, architecture diagram, bilingual worklogs, and AWS resource-cleanup procedure.
