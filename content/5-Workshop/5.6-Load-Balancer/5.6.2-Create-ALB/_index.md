---
title : "Create Application Load Balancer"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.6.2. </b> "
---

We will deploy a public-facing Application Load Balancer (ALB) across 2 public subnets to receive and route requests from the public internet.

---

### Steps:

1. In the left menu of the EC2 Console, select **Load Balancers** -> Click **Create load balancer**.
2. Under the **Application Load Balancer** type, click **Create**.
3. Configure the load balancer parameters:
   - **Load balancer name**: `pg-alb`.
   - **Scheme**: Select **Internet-facing** (Routes public requests from the Internet).
   - **Network mapping**:
     - **VPC**: Select **`pg-vpc`**.
     - **Mappings**: Check **both public subnets** (`pg-subnet-public1...` in AZ 1a and `pg-subnet-public2...` in AZ 1b).
   - **Security groups**: Select **`pg-alb-sg`** (and remove the default group).
   - **Listeners and routing**:
     - Default Listener: **HTTP:80** -> Forward to target group: Select **`tg-frontend`**.
4. Click **Create load balancer** at the bottom. Wait until its status becomes **Active**.

![ALB Created](/images/5-Workshop/5.6-Load-Balancer/5.6.2-alb_creation.png)
