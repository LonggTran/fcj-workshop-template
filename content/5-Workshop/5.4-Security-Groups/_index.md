---
title : "Security Groups Setup"
date : 2024-01-01 
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

In this section, we will create Security Groups (virtual firewalls) to control traffic flow to the Application Load Balancer, the ECS container services, and the RDS database.

---

### Step 4.1: Create Security Group for Application Load Balancer (`pg-alb-sg`)
The ALB will receive public requests from the Internet:
1. Open the **EC2** service on the AWS Console -> Under **Network & Security** in the left menu, select **Security Groups**.
2. Click **Create security group** in the top right.
3. Configure the details:
   - **Security group name**: `pg-alb-sg`.
   - **Description**: `Allow HTTP traffic from internet`.
   - **VPC**: Select **`pg-vpc`** (Do not select the default VPC).
4. **Configure Inbound rules:** Click **Add rule**:
   - **Type**: **HTTP** (port 80).
   - **Source**: **Anywhere-IPv4** (`0.0.0.0/0`).
5. Click **Create security group** at the bottom.

![Create the ALB security group](/images/h16.png)

---

### Step 4.2: Create Security Group for Containers & Database (`pg-ecs-sg`)
This Security Group protects the Fargate tasks (Frontend, unified Backend) and the RDS PostgreSQL instance in the Private Subnets:
1. Navigate back to the Security Groups list -> Click **Create security group**.
2. Configure the details:
   - **Security group name**: `pg-ecs-sg`.
   - **Description**: `Allow traffic from ALB and internal containers`.
   - **VPC**: Select **`pg-vpc`**.
3. **Configure Inbound rules:** Add the following 4 rules for precise access delegation:
   - **Rule 1 (For Frontend):** Type: **HTTP** | Source: Select **Custom** -> Choose the **`pg-alb-sg`** security group created in Step 4.1.
   - **Rule 2 (For API Gateway Backend):** Type: **Custom TCP** | Port range: `8080` | Source: Select **Custom** -> Choose the **`pg-alb-sg`** security group.
   - **Rule 3 (For PostgreSQL Database):** Type: **PostgreSQL** (port 5432) | Source: Select **Custom** -> Choose this same **`pg-ecs-sg`** security group. (Allows the backend tasks using this group to communicate with RDS).
   - **Rule 4 (Cross-container communication):** Type: **All traffic** | Source: Select **Custom** -> Choose this same **`pg-ecs-sg`** security group. (Allows the Java container and Redis sidecar container to communicate on localhost).
4. Click **Create security group** at the bottom.

![Configure the ECS and RDS security group](/images/h17.png)
