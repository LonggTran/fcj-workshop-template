---
title : "Create RDS PostgreSQL DB Instance"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.5.2. </b> "
---

We will provision an isolated Amazon RDS PostgreSQL instance within our Private Subnets, disabling public access.

---

### Steps:

1. Select **Databases** in the left menu of the RDS console -> Click **Create database**.
2. Configure the database options:
   - **Database creation method**: Select **Standard create**.
   - **Engine options**: Select **PostgreSQL**.
   - **Templates**: Select **Free Tier**.
   - **Settings**:
     - **DB instance identifier**: `pg-db`.
     - **Master username**: `postgres`.
     - **Master password**: `yourpassword` (and confirm).

![Configure the RDS database settings](/images/h19.png)

   - **Instance configuration and storage**:
     - Select a suitable burstable instance class, such as `db.t3.micro`.
     - Use General Purpose SSD storage with an appropriate allocated capacity.

![Configure the RDS instance class and storage](/images/h20.png)

   - **Connectivity**:
     - **Virtual private cloud (VPC)**: Select **`pg-vpc`**.
     - **DB Subnet Group**: Select **`pg-db-subnet-group`** created earlier.
     - **Public access**: Select **No**.
     - **VPC security group**: Select **Choose existing**, select **`pg-ecs-sg`**, and uncheck the default group.

![Configure RDS connectivity and security](/images/h21.png)

3. Click **Create database** at the bottom.
4. Wait 5-10 minutes. Once the status changes to **Available**, copy the database **Endpoint** (looks like `pg-db.xxxx.ap-southeast-1.rds.amazonaws.com`).
