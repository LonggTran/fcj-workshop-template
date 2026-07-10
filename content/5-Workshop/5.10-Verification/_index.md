---
title : "Verification & Results"
date : 2024-01-01 
weight : 10
chapter : false
pre : " <b> 5.10. </b> "
---

After deploying all infrastructure components (VPC, RDS, ALB, ECS Fargate, CloudWatch Alarm, S3 Backup), this is the final step to test and verify the entire system's correctness and performance.

---

### Step 10.1: Verify Target Group Health Status
Before accessing the web UI, we must ensure that the Application Load Balancer has successfully registered and established connectivity to the Fargate Tasks running in the Private Subnets:
1. Go to the **EC2** service -> select **Target Groups** from the left navigation pane.
2. Verify the health status of both Target Groups:
   - **`tg-frontend`**: Under the **Targets** tab, the IP address list of the Frontend Task must show a **`Healthy`** status on port 80.
   - **`tg-backend`**: The IP address list of the Backend Task must show a **`Healthy`** status on port 8080.

![Backend Target Health](/images/h48.png)
![Frontend Target Health](/images/h49.png)

---

### Step 10.2: Access and Test the Web Interface
1. Go to the **EC2** service -> click **Load Balancers** -> select **`pg-alb`**.
2. Copy the **DNS name** (e.g., `pg-alb-504838152.ap-southeast-1.elb.amazonaws.com`).
3. Paste this DNS address into your web browser to access the **NextGenPay** application:

![DNS name](/images/h69.png)

- **Initial State (Offline):** When the backend containers are starting up or not yet ready to connect to the database, the top right of the dashboard will display `Gateway: OFFLINE` and the service status indicators (Account Service, Payment Service, Transaction Service, API Gateway) will show red `OFFLINE` warnings.
- **Active State (Online):** Wait a few minutes for the Spring Boot services to finish initialization and connect successfully to the RDS PostgreSQL database and the Redis sidecar. These indicators will turn green `ONLINE`, and you can start creating accounts and submitting transactions.

---

### Step 10.3: Inspect Container Logs via CloudWatch
To monitor internal microservice activities and verify container-to-container communication:
1. Go to the **CloudWatch** console.
2. Select **Log groups** from the left pane -> click on the **`/ecs/pg-logs`** log group.
3. Check the **Log Streams** corresponding to each container:
   - **`backend/...`**: Contains logs from the Spring Boot services (API Gateway, Account Service, Payment Service, Transaction Service). Look for connection confirmation messages pointing to the database host and the Redis sidecar (`127.0.0.1:6379`).
   - **`redis/...`**: Contains execution logs of the Redis cache engine running alongside the Java container.
   - **`frontend/...`**: Shows access and error logs for the Nginx proxy serving static assets.

---

### Step 10.4: Check Request Metrics in CloudWatch
We can view real-time traffic statistics arriving at our Load Balancer:
1. In the **CloudWatch** console, go to **Metrics** -> **All metrics** in the left menu.
2. Search and select the **`RequestCount`** metric belonging to your Load Balancer **`pg-alb`** (or go to the **Graphed metrics** tab to adjust the time window).
3. Select **Sum** as the **Statistic** and **5 minutes** (or `1 minute`) as the **Period**. You should see the traffic visualization graph:

![Metrics](/images/h70.png)

- The graph will plot a sharp spike (e.g., reaching over 250 requests) representing the load test script execution you ran via PowerShell.
