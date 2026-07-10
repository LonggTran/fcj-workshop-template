---
title : "RDS PostgreSQL Database Creation"
date : 2024-01-01 
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

In this section, we will deploy an **Amazon RDS PostgreSQL** instance running completely isolated in the Private Subnets. We will use a temporary public EC2 instance (Bastion Host / Jumpbox) as a bridge to initialize the database schema.

#### Contents:

1. [Create DB Subnet Group](5.5.1-Create-Subnet-Group/)
2. [Create RDS PostgreSQL DB Instance](5.5.2-Create-RDS-Instance/)
3. [Initialize Databases via Bastion Host](5.5.3-Initialize-Database/)
