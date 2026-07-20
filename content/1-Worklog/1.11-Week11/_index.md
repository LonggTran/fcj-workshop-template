---
title: "Week 11 Worklog"
date: 2026-06-29
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Week 11 Objectives:

* Package the application with Docker and store images in Amazon ECR.
* Build a two-Availability-Zone VPC with public/private subnets, an Internet Gateway, a NAT Gateway, and Security Groups.
* Create Amazon RDS PostgreSQL in private subnets and initialize data through an EC2 Bastion Host.
* Deploy an Application Load Balancer and containers on Amazon ECS Fargate.
* Configure IAM roles, CloudWatch Logs, and ECS Service Auto Scaling for the deployment environment.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Package the application and manage Amazon ECR<br>&emsp; + Compile the Spring Boot services into JAR files<br>&emsp; + Build the backend Docker image and prepare the frontend image for deployment<br>&emsp; + Create ECR repositories, tag the images, and push them to AWS | 29/06/2026 | 29/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway><br><https://xduc695.github.io/fcj-workshop-template/5-workshop/5.2-prerequiste/> |
| Tuesday | - Set up VPC Networking and Security Groups<br>&emsp; + Create a VPC across two Availability Zones with two public and two private subnets<br>&emsp; + Configure the Internet Gateway, NAT Gateway, and route tables<br>&emsp; + Separate Security Groups for ALB, ECS Fargate, RDS, and the Bastion Host | 30/06/2026 | 30/06/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.3-vpc-networking/><br><https://xduc695.github.io/fcj-workshop-template/5-workshop/5.4-security-groups/> |
| Wednesday | - Create Amazon RDS PostgreSQL in the private network<br>&emsp; + Create a DB Subnet Group from the two private subnets<br>&emsp; + Launch RDS PostgreSQL with public access disabled<br>&emsp; + Create an EC2 Bastion Host and run scripts to create the business databases | 01/07/2026 | 01/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.5-rds-database/> |
| Thursday | - Configure the Application Load Balancer<br>&emsp; + Create target groups for the frontend and backend API Gateway<br>&emsp; + Launch an internet-facing ALB in the public subnets<br>&emsp; + Configure listener rules so `/api/*` goes to the backend and default requests go to the frontend | 02/07/2026 | 02/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.6-load-balancer/> |
| Friday | - Deploy Amazon ECS Fargate<br>&emsp; + Create the ECS Cluster, CloudWatch Log Group, Task Execution Role, and Task Role<br>&emsp; + Register Task Definitions for the backend, Redis sidecar, and frontend<br>&emsp; + Create ECS Services in private subnets, attach target groups, and configure Service Auto Scaling | 03/07/2026 | 03/07/2026 | <https://xduc695.github.io/fcj-workshop-template/5-workshop/5.7-ecs-fargate/> |

### Week 11 Achievements:

* Completed Docker image build, tagging, and upload to Amazon ECR.
* Built a multi-Availability-Zone VPC with public/private subnets, an Internet Gateway, a NAT Gateway, route tables, and layered Security Groups.
* Created RDS PostgreSQL in the private network and initialized Account, Payment, and Transaction Service databases through the Bastion Host.
* Configured the ALB, target groups, and listener rules to distribute traffic to the frontend and backend API Gateway.
* Deployed tasks and services on ECS Fargate, centralized logs in CloudWatch, and prepared automatic service scaling based on load.
