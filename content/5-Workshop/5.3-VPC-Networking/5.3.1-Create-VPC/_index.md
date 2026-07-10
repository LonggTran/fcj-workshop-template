---
title : "Create VPC with \"VPC and more\""
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.3.1. </b> "
---

We will use the "VPC and more" wizard to spin up our public and private subnets.

---

### Step 1: Create VPC
1. Sign in to your AWS Console -> Search for and select the **VPC** service.
2. Click the **Create VPC** button.
3. Configure the parameters:
   - **Resources to create**: Select **VPC and more**.
   - **Name tag auto-generation**: Enter `pg`.
   - **IPv4 CIDR block**: Keep the default `10.0.0.0/16`.
   - **Number of Availability Zones (AZs)**: Choose **2**.
   - **Number of Public Subnets**: Choose **2** (Ranges: `10.0.1.0/24` and `10.0.2.0/24`).
   - **Number of Private Subnets**: Choose **2** (Ranges: `10.0.128.0/24` and `10.0.129.0/24`).
   - **NAT Gateways**: Choose **1 in 1 AZ**.
   - **VPC Endpoints**: Choose **None**.
   - **DNS options**: Ensure both **Enable DNS resolution** and **Enable DNS hostnames** are checked.
4. Click **Create VPC** at the bottom -> Wait 1 minute and click **View VPC**.

![Create VPC Page](/images/5-Workshop/5.3-VPC-Networking/5.3.1-vpc_create.png)

---

### Step 2: Enable Public IP auto-assignment on Public Subnets
To ensure resources placed in public subnets receive public IPs automatically:
1. Click **Subnets** in the left menu.
2. Select the first public subnet: `pg-subnet-public1-ap-southeast-1a`.
3. Click **Actions** -> **Edit subnet settings**.
4. Check **Enable auto-assign public IPv4 address**. Click **Save**.
5. Repeat for the second public subnet: `pg-subnet-public2-ap-southeast-1b`.

![Enable Auto IP](/images/5-Workshop/5.3-VPC-Networking/5.3.1-enable_ip.png)
