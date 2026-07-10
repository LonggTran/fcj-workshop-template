---
title : "Prepare Log Group & IAM Role"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.7.1. </b> "
---

We need to prepare a CloudWatch Log Group and an IAM Execution Role before defining the ECS Fargate tasks.

---

### Step 1: Create a CloudWatch Log Group
Fargate uses the `awslogs` driver to stream output logs, requiring the Log Group to be created beforehand:
1. Search for and select the **CloudWatch** service on the AWS Console.
2. Select **Log groups** in the left menu -> Click **Create log group**.
3. **Log group name**: Enter **`/ecs/pg-logs`**.
4. **Retention setting**: Select **1 day** (or 1 week). Click **Create**.

![Create the CloudWatch log group](/images/h36.png)

---

### Step 2: Create the Task Execution Role (`ecsTaskExecutionRole`)
This role allows the ECS agent to pull images from ECR and publish log streams to CloudWatch:
1. Go to the **IAM** service -> Click **Roles** -> Click **Create role**.
2. **Trusted entity type**: Select **AWS service**.
3. **Service or use case**: Select **Elastic Container Service** -> Select **Elastic Container Service Task**. Click **Next**.
4. **Permissions policies**: Search for and check **`AmazonECSTaskExecutionRolePolicy`**. Click **Next**.

![Select the ECS task execution role policy](/images/h37.png)

5. **Role name**: Enter **`ecsTaskExecutionRole`**.
6. Click **Create role**.

![Create the ECS task execution role](/images/h38.png)
