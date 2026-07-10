---
title : "Launch ECS Services"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.7.3. </b> "
---

We will create the ECS Cluster and spin up our frontend and backend container services inside our secure Private Subnets.

---

### Step 1: Create the ECS Cluster
1. In the ECS Console, click **Clusters** -> Click **Create cluster**.
2. **Cluster name**: `pg-cluster`.
3. **Infrastructure**: Select **AWS Fargate (serverless)**. Click **Create**.

![Create the ECS cluster](/images/h41.png)
![ECS cluster created successfully](/images/h42.png)

---

### Step 2: Launch the Backend Service (`pg-backend-service`)
1. Open cluster `pg-cluster` -> Go to the **Services** tab -> Click **Create**.
2. Configure the service:
   - **Compute configuration**: Select **Launch type** -> **FARGATE**.
   - **Family**: Select **`pg-backend`** (revision 1).
   - **Service name**: `pg-backend-service`.
   - **Desired tasks**: `1`.

![Configure the backend ECS service](/images/h43.png)

   - **Networking**:
     - VPC: Choose **`pg-vpc`**.
     - Subnets: Check **only the two Private Subnets** (`pg-subnet-private1...` and `pg-subnet-private2...`). *Uncheck public subnets*.
     - Security group: Select **Use existing** -> Choose **`pg-ecs-sg`** (and remove the default group).
     - Public IP: Select **Disabled** (Turned off).

![Configure private networking for the backend service](/images/h44.png)

   - **Load balancing**:
     - Load balancer type: Select **Application Load Balancer**.
     - Load balancer: Select **`pg-alb`**.
     - Container to load balance: Select `backend:8080:8080`.

![Configure the backend container for load balancing](/images/h45.png)

     - Listener: Select **Use an existing listener** -> Choose **`HTTP:80`**.
     - Target group: **Use an existing target group** -> Select **`tg-backend`**.

![Select the backend listener and target group](/images/h46.png)

3. Click **Create**.

---

### Step 3: Launch the Frontend Service (`pg-frontend-service`)
1. Navigate back to the Cluster Services tab -> Click **Create**.
2. Configure the service:
   - Compute: **FARGATE** | Family: **`pg-frontend`** | Service name: `pg-frontend-service` | Desired tasks: `1`.
   - **Networking**: VPC `pg-vpc`, select the 2 Private Subnets, Security group `pg-ecs-sg`, Public IP: **Disabled**.
   - **Load balancing**:
     - Load balancer: Select `pg-alb`.
     - Container: Select `frontend:80:80`.
     - Target group: **Use an existing target group** -> Select **`tg-frontend`**.
3. Click **Create**.

*Wait 1-2 minutes. The status of both services will turn to ACTIVE. You can now access your website via the ALB DNS link!*

![Backend target health](/images/h48.png)
![Frontend target health](/images/h49.png)
![ECS Fargate services deployed successfully](/images/h47.png)
