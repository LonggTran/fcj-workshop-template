---
title : "Introduction"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

#### Microservices Payment Gateway Overview

The Payment Gateway application deployed in this workshop consists of multiple microservices built on **Spring Boot** (Backend) and **React Vite** (Frontend):
- **API Gateway (Port 8080):** Serves as the single entry point, routing client traffic to specific internal microservices.
- **Account Service (Port 8082):** Manages customer profiles, account registration, and account balances.
- **Payment Service (Port 8083):** Handles transaction processing, incorporating idempotency keys with Redis distributed locks.
- **Transaction Service (Port 8084):** Manages ledger histories and double-entry auditing.
- **Redis Cache/Lock:** Manages locking mechanisms for payment request protection.

#### Network Architecture Diagram

The AWS deployment follows a secure multi-tier networking model:

![Architecture Diagram](/images/5-Workshop/5.1-Workshop-overview/diagram1.png)

#### Key Architectural Highlights:
1. **Network Isolation:** The ALB sits in **Public Subnets** to face external web traffic, whereas the ECS container services and the RDS PostgreSQL database are hosted strictly in **Private Subnets** with no public IP access.
2. **NAT Gateway Routing:** Allows tasks in Private Subnets to make outbound connections to retrieve ECR images and upload logs to CloudWatch.
3. **Monolithic Task Packaging:** The 4 Spring Boot microservices are run concurrently within a single unified Docker container alongside a Redis container (sidecar) to minimize Fargate costs.
4. **S3 Backup:** Seamless RDS snapshot export encrypted with custom KMS keys to S3.