---
title : "Create DB Subnet Group"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.5.1. </b> "
---

A DB Subnet Group defines the subnets where RDS instances can be allocated. We will restrict the RDS database to exist only inside our secure Private Subnets.

---

### Steps:

1. Search for and select **RDS** on the AWS Console.
2. In the left menu, select **Subnet groups** -> Click **Create DB subnet group**.
3. Configure the details:
   - **Name**: `pg-db-subnet-group`.
   - **Description**: `DB Subnet Group for payment gateway`.
   - **VPC**: Select **`pg-vpc`**.
   - **Add subnets**:
     - **Availability Zones**: Choose your 2 AZs (e.g., `ap-southeast-1a` and `ap-southeast-1b`).
     - **Subnets**: Check the 2 Private Subnets: **`10.0.128.0/24`** and **`10.0.129.0/24`**.
4. Click **Create**.

![Create the DB subnet group](/images/h18.png)
