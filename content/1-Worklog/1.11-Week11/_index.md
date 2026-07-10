---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 11 Objectives:

* Integrate all microservices locally and standardize configuration for AWS deployment.
* Finalize the AWS architecture for a high-throughput payment system using managed services and automatic scaling.
* Create and configure the required AWS networking, compute, database, cache, security, and monitoring services.
* Package the applications as Docker images and deploy the services with Amazon ECS Fargate.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Integrate and verify the local system flow<br>&emsp; + Start PostgreSQL, Redis, and all microservices with consistent environment configuration<br>&emsp; + Verify API Gateway routing, health endpoints, and the Payment Service → Account Service connection<br>&emsp; + Fix database configuration, environment-variable, and schema issues found during concurrent startup | 06/29/2026 | 06/29/2026 | Project source code and Docker Compose |
| 3 | - Finalize the AWS deployment architecture<br>&emsp; + Design one VPC across two Availability Zones with subnets for application and data tiers<br>&emsp; + Define the Amazon API Gateway → VPC Link → Internal ALB → ECS Fargate request flow<br>&emsp; + Design Security Groups and IAM Roles according to least privilege | 06/30/2026 | 06/30/2026 | <https://docs.aws.amazon.com/vpc/> |
| 4 | - Create the image-storage and compute layers<br>&emsp; + Create Amazon ECR repositories, then build and push the service Docker images<br>&emsp; + Create the ECS Cluster, Task Definitions, and Fargate ECS Services<br>&emsp; + Configure health checks and ECS Service Auto Scaling for each service | 07/01/2026 | 07/01/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/> |
| 5 | - Create the data layer and security configuration<br>&emsp; + Create Amazon RDS for PostgreSQL for account, payment, and transaction data<br>&emsp; + Create Amazon ElastiCache for Redis for cache, lock, and rate limiting<br>&emsp; + Store connection details in AWS Secrets Manager and grant access through ECS Task Roles | 07/02/2026 | 07/02/2026 | <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/> |
| 6 | - Complete the access and monitoring layers<br>&emsp; + Create an Internal Application Load Balancer, target groups, and listener rules for the services<br>&emsp; + Connect API Gateway to the ALB through VPC Link<br>&emsp; + Configure CloudWatch Logs, metrics, alarms, and health monitoring for ECS, RDS, and Redis | 07/03/2026 | 07/03/2026 | <https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-vpc-links.html> |

### Week 11 Achievements:

* Completed system-component integration:
  * API Gateway routes requests correctly to Account Service, Payment Service, and Transaction Service.
  * Payment Service communicates with Account Service, and the services use the correct PostgreSQL and Redis connections.
  * Actuator endpoints provide a fast way to verify each service before and after deployment.

* Finalized an AWS architecture suitable for a high-concurrency system:
  * Amazon API Gateway remains outside the VPC and connects to the private network through VPC Link.
  * An Internal ALB distributes requests to ECS Services running on AWS Fargate.
  * RDS PostgreSQL and ElastiCache Redis are isolated in the data tier and accept traffic only from required Security Groups.

* Packaged and deployed the application with containers:
  * Docker images are stored centrally in Amazon ECR.
  * ECS Task Definitions manage the image, port, CPU, memory, environment variables, and secrets for each service.
  * ECS Service Auto Scaling provides a foundation for increasing or decreasing task counts according to resource usage.

* Established the basic operations and security components:
  * IAM Roles and Security Groups are restricted according to the responsibility of each layer.
  * Sensitive information is removed from source code and managed through AWS Secrets Manager.
  * Application logs and infrastructure metrics are centralized in Amazon CloudWatch for the load-testing phase.
