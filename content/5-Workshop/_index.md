---
title: "Workshop"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

# Deploying a High-Performance Payment Gateway on AWS ECS Fargate with Private Networking, RDS PostgreSQL, and S3 Backup

#### Overview

In this workshop, we will build and deploy a secure, highly-available cloud infrastructure on AWS for a **Microservices Payment Gateway**.

The architecture follows production-grade security standards: isolating backend containers and database in **Private Subnets**, utilizing an **Application Load Balancer** in Public Subnets to receive and route traffic, running multi-container ECS tasks (Spring Boot API Gateway + Redis sidecar) on **AWS ECS Fargate**, connecting to a private **Amazon RDS PostgreSQL** instance, and implementing **automated database backup to S3** via RDS Snapshot exports encrypted with a customer-managed KMS key.

#### Workshop Contents

1. [Workshop overview](5.1-Workshop-overview/)
2. [Prerequisites & ECR setup](5.2-Prerequiste/)
3. [VPC Networking Configuration](5.3-VPC-Networking/)
4. [Security Groups Setup](5.4-Security-Groups/)
5. [RDS PostgreSQL Database Creation](5.5-RDS-Database/)
6. [Application Load Balancer Configuration](5.6-Load-Balancer/)
7. [ECS Fargate Container Services Deployment](5.7-ECS-Fargate/)
8. [CloudWatch Alarm & SNS Email Notification](5.8-CloudWatch-Alarm/)
9. [RDS S3 Backup & Recovery Integration](5.9-S3-Backup/)
10. [Verification & Results](5.10-Verification/)
11. [Resource Cleanup](5.11-Cleanup/)