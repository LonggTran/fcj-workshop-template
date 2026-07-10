---
title : "Initialize Databases via Bastion Host"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.5.3. </b> "
---

Because the RDS database is locked inside a Private Subnet, your personal computer cannot connect directly to initialize it. We will deploy a temporary public EC2 instance (Bastion Host) to serve as a bridge.

---

### Step 1: Launch the Bastion Host (EC2)
1. Open the **EC2** service -> Go to **Instances** -> Click **Launch instances**.
2. Configure the instance:
   - **Name**: `pg-bastion`.
   - **OS**: **Amazon Linux 2023** (Free Tier eligible).
   - **Instance type**: `t2.micro` (or `t3.micro`).
   - **Key pair**: Select **Proceed without a key pair** (we will connect directly via the web browser).

![Configure the EC2 bastion host](/images/h22.png)

   - **Network settings**: Click **Edit**:
     - **VPC**: Select **`pg-vpc`**.
     - **Subnet**: Select the first public subnet (e.g., `pg-subnet-public1-ap-southeast-1a`).
     - **Auto-assign public IP**: Select **Enable**.
     - **Security group**: Select **Create security group** -> Name: `pg-bastion-sg` -> Inbound rules: **Remove** all rules.

![Configure networking for the bastion host](/images/h23.png)

3. Click **Launch instance**.

---

### Step 2: Allow Bastion Host to access RDS
1. Open your container Security Group **`pg-ecs-sg`** -> Click **Edit inbound rules** -> Click **Add rule**:
   - **Type**: **PostgreSQL** (port 5432).
   - **Source**: **Custom** -> Select the **`pg-bastion-sg`** security group. Click **Save rules**.

---

### Step 3: Connect and Execute SQL via Browser

![Allow the bastion security group to access RDS](/images/h24.png)

1. In the EC2 Instances page, select `pg-bastion` -> Click **Connect**.

![Connect to the EC2 bastion host](/images/h25.png)
2. Select the **EC2 Instance Connect** tab -> Click **Connect**. A web-based Linux shell will appear in your browser.
3. Run the following commands to install the PostgreSQL client and initialize the database schema:
   ```bash
   # 1. Install PostgreSQL client
   sudo dnf install postgresql15 -y
   
   # 2. Create the SQL initialization file
   cat << 'EOF' > init.sql
   CREATE DATABASE paymentservice;
   CREATE DATABASE accountservice;
   CREATE DATABASE transactionservice;
   EOF
   
   # 3. Execute database creation (Replace <rds-endpoint> with your actual RDS Endpoint)
   # When prompted for password, enter: yourpassword
   psql -h <rds-endpoint> -U postgres -d postgres -f init.sql
   ```

![Install the PostgreSQL client](/images/h26.png)
![Create and initialize the databases on RDS](/images/h27.png)

   *Successful execution will print `CREATE DATABASE` for all three databases.*
4. **Terminate the Bastion Host:**
   - Go back to the EC2 Instances page -> Select `pg-bastion` -> Click **Instance state** -> Click **Terminate instance** to delete the server and prevent additional costs.
