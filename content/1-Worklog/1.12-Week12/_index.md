---
title: "Week 12 Worklog"
date: 2026-07-06
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---
### Week 12 Objectives:

* Complete deployment and end-to-end verification of the High-Concurrency Payment Gateway on AWS.
* Monitor ALB target groups, ECS tasks, RDS, the Redis sidecar, and CloudWatch Logs.
* Run k6 load tests and observe RequestCount, latency, error rate, and ECS Service Auto Scaling behavior.
* Configure CloudWatch Alarms, Amazon SNS, and RDS Snapshot export to Amazon S3 with AWS KMS.
* Fix deployment issues, complete documentation, and clean up unused AWS resources.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Verify the deployed components<br>&emsp; + Check the Healthy status of the frontend and backend target groups<br>&emsp; + Access the application through the ALB DNS and test account, payment, balance, and transaction flows<br>&emsp; + Inspect CloudWatch Log Streams for the backend, Redis, and frontend | 06/07/2026 | 06/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.10-verification/> |
| Tuesday | - Run load tests and monitor performance<br>&emsp; + Execute k6 with increasing virtual-user and request levels<br>&emsp; + Monitor latency, throughput, error rate, and HTTP 429 responses from the rate limiter<br>&emsp; + Observe ALB RequestCount, ECS CPU/Memory, and task count during load growth | 07/07/2026 | 07/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.8-cloudwatch-alarm/><br><https://xduc695.github.io/fcj-workshop-template/5-workshop/5.10-verification/> |
| Wednesday | - Configure alerts and tune the system<br>&emsp; + Create an Amazon SNS Topic and subscribe an alert email address<br>&emsp; + Create CloudWatch Alarms based on ALB RequestCount or CPU utilization<br>&emsp; + Adjust timeouts, rate-limit thresholds, CPU/Memory, and scaling policies based on the test results<br>&emsp; + Fix application-configuration or connectivity issues found on AWS | 08/07/2026 | 08/07/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://xduc695.github.io/fcj-workshop-template/5-workshop/5.8-cloudwatch-alarm/> |
| Thursday | - Back up data on AWS<br>&emsp; + Create an S3 bucket for backup data<br>&emsp; + Create an AWS KMS key and IAM role for snapshot export<br>&emsp; + Create an RDS Snapshot and export data to Amazon S3 with encryption | 09/07/2026 | 09/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.9-s3-backup/> |
| Friday | - Complete the report and clean up resources<br>&emsp; + Run regression tests for the main flows after fixes<br>&emsp; + Finalize the architecture diagram, Workshop documentation, bilingual worklog, and result report<br>&emsp; + Review, stop, or delete unused ECS Services, ALB, NAT Gateway, RDS, S3, and related resources to avoid additional cost | 10/07/2026 | 10/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.10-verification/><br><https://xduc695.github.io/fcj-workshop-template/5-workshop/5.11-cleanup/> |

### Week 12 Achievements:

* Verified the request flow from the Internet through the ALB to the frontend and backend API Gateway on ECS Fargate.
* Confirmed that ECS tasks connect to RDS PostgreSQL and the Redis sidecar and send centralized logs to CloudWatch.
* Ran k6 load tests and monitored RequestCount, latency, throughput, error rate, CPU/Memory, and HTTP 429 responses.
* Configured CloudWatch Alarms and Amazon SNS for threshold-based system notifications.
* Performed the RDS Snapshot workflow and prepared encrypted backup export to S3 with KMS.
* Completed deployment documentation, Vietnamese/English worklogs, the architecture diagram, and the AWS resource-cleanup procedure.
