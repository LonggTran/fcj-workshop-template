---
title : "Create Target Groups"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.6.1. </b> "
---

We must define target groups indicating where the ALB should route incoming traffic:

---

### Steps:

1. **Create Target Group for Frontend (`tg-frontend`):**
   - Open the **EC2** service -> Select **Target Groups** under the Load Balancing section in the left menu.
   - Click **Create target group**.
   - **Choose a target type**: Select **IP addresses** (Required for AWS Fargate ECS tasks).
   - **Target group name**: `tg-frontend`.
   - **Protocol & Port**: Select **HTTP** and port **`80`** (Do not select *TCP*).
   - **VPC**: Select **`pg-vpc`**.
   - **Health check path**: `/`.
   - Click **Next** -> Click **Create target group** (Omit target registration; ECS will handle this automatically).

2. **Create Target Group for Backend (`tg-backend`):**
   - Navigate back to the Target Groups page -> Click **Create target group**.
   - **Choose a target type**: Select **IP addresses**.
   - **Target group name**: `tg-backend`.
   - **Protocol & Port**: Select **HTTP** and port **`8080`**.

![Configure the backend target group](/images/h28.png)

   - **VPC**: Select **`pg-vpc`**.
   - **Health check path**: `/actuator/health`.

![Configure the backend target group health check](/images/h29.png)

   - Click **Next** -> Click **Create target group**.

![Target groups created successfully](/images/h30.png)
