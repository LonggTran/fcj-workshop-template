---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Week 11 Objectives:

* Begin deploying the High-Concurrency Payment Gateway on AWS.
* Push Docker images to Amazon ECR and build a multi-Availability-Zone network.
* Create Amazon RDS PostgreSQL, an Application Load Balancer, and Amazon ECS Fargate resources.
* Configure Security Groups, IAM Roles, CloudWatch Logs, and ECS Service Auto Scaling.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Package the application and manage images in Amazon ECR<br>&emsp; + Build the services into JAR files<br>&emsp; + Build Docker images for the backend and frontend<br>&emsp; + Create ECR repositories and authenticate Docker with ECR<br>&emsp; + Tag and push images to Amazon ECR | 29/06/2026 | 29/06/2026 | <https://000015.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Tuesday | - Set up AWS networking infrastructure<br>&emsp; + Create a VPC across two Availability Zones<br>&emsp; + Create public and private subnets<br>&emsp; + Configure an Internet Gateway, NAT Gateway, and route tables<br>&emsp; + Create Security Groups for the ALB, ECS, RDS, and Bastion Host | 30/06/2026 | 30/06/2026 | <https://000003.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |
| Wednesday | - Create Amazon RDS PostgreSQL in private subnets<br>&emsp; + Create a DB Subnet Group from two private subnets<br>&emsp; + Disable public access and allow connections only from internal Security Groups<br>&emsp; + Create a Bastion Host to initialize the accountservice, paymentservice, and transactionservice databases<br>&emsp; + Verify connectivity and Flyway Migration | 01/07/2026 | 01/07/2026 | <https://000005.awsstudygroup.com/><br><https://000015.awsstudygroup.com/> |
| Thursday | - Configure the Application Load Balancer<br>&emsp; + Create target groups for the frontend and backend API Gateway<br>&emsp; + Create an internet-facing ALB in the public subnets<br>&emsp; + Configure a listener rule that sends `/api/*` to the backend and default requests to the frontend<br>&emsp; + Configure target-group health checks | 02/07/2026 | 02/07/2026 | <https://000006.awsstudygroup.com/><br><https://000016.awsstudygroup.com/> |
| Friday | - Deploy the application on Amazon ECS Fargate<br>&emsp; + Create an ECS Cluster, Task Definitions, and ECS Services<br>&emsp; + Run tasks in private subnets with public IP disabled<br>&emsp; + Configure a Redis sidecar container for the backend<br>&emsp; + Attach ECS Services to ALB target groups<br>&emsp; + Configure the IAM Task Execution Role, CloudWatch Log Group, and Service Auto Scaling | 03/07/2026 | 03/07/2026 | <https://000016.awsstudygroup.com/><br><https://000008.awsstudygroup.com/><br><https://000044.awsstudygroup.com/> |

### Week 11 Achievements:

* Successfully built and pushed Docker images to Amazon ECR.
* Completed a multi-Availability-Zone VPC with public/private subnets, an Internet Gateway, a NAT Gateway, route tables, and Security Groups.
* Created RDS PostgreSQL in private subnets and prepared the application databases.
* Configured the ALB, target groups, listener rules, and health checks for the frontend and backend.
* Deployed the backend, frontend, and Redis sidecar on ECS Fargate and centralized logs in CloudWatch.
