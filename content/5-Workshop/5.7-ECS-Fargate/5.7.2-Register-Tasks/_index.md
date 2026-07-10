---
title : "Register Task Definitions via JSON"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.7.2. </b> "
---

We will define how our containers run using JSON schemas:
1. In the **ECS** console, select **Task definitions** in the left menu -> Click **Create new task definition** -> Select **Create new task definition with JSON**.

2. **Register the Backend Task Definition (`pg-backend`):**
   - Clear the template editor and paste the JSON block below.
   - *Note: Replace `<aws-account-id>` with your AWS Account ID (e.g., `795938553282`) and `<rds-endpoint>` with your RDS PostgreSQL Endpoint*:
```json
{
  "family": "pg-backend",
  "cpu": "512",
  "memory": "1024",
  "networkMode": "awsvpc",
  "requiresCompatibilities": ["FARGATE"],
  "executionRoleArn": "arn:aws:iam::<aws-account-id>:role/ecsTaskExecutionRole",
  "containerDefinitions": [
    {
      "name": "backend",
      "image": "<aws-account-id>.dkr.ecr.ap-southeast-1.amazonaws.com/pg-combined-backend:latest",
      "cpu": 256,
      "memory": 512,
      "portMappings": [
        {"containerPort": 8080},
        {"containerPort": 8082},
        {"containerPort": 8083},
        {"containerPort": 8084}
      ],
      "environment": [
        {"name": "SPRING_PROFILES_ACTIVE", "value": "dev"},
        {"name": "DB_USERNAME", "value": "postgres"},
        {"name": "DB_PASSWORD", "value": "yourpassword"},
        {"name": "DB_ACCOUNT_NAME_URL", "value": "jdbc:postgresql://<rds-endpoint>:5432/accountservice"},
        {"name": "DB_PAYMENT_NAME_URL", "value": "jdbc:postgresql://<rds-endpoint>:5432/paymentservice"},
        {"name": "DB_TRANSACTION_NAME_URL", "value": "jdbc:postgresql://<rds-endpoint>:5432/transactionservice"},
        {"name": "REDIS_HOST", "value": "127.0.0.1"},
        {"name": "REDIS_PORT", "value": "6379"},
        {"name": "ACCOUNT_SERVICE_URL", "value": "http://localhost:8082"},
        {"name": "PAYMENT_SERVICE_URL", "value": "http://localhost:8083"},
        {"name": "TRANSACTION_SERVICE_URL", "value": "http://localhost:8084"}
      ],
      "logConfiguration": {
        "logDriver": "awslogs",
        "options": {
          "awslogs-group": "/ecs/pg-logs",
          "awslogs-region": "ap-southeast-1",
          "awslogs-stream-prefix": "backend"
        }
      }
    },
    {
      "name": "redis",
      "image": "public.ecr.aws/docker/library/redis:alpine",
      "cpu": 256,
      "memory": 512,
      "portMappings": [
        {"containerPort": 6379}
      ],
      "logConfiguration": {
        "logDriver": "awslogs",
        "options": {
          "awslogs-group": "/ecs/pg-logs",
          "awslogs-region": "ap-southeast-1",
          "awslogs-stream-prefix": "redis"
        }
      }
    }
  ]
}
```

![Register the backend task definition](/images/h39.png)

   - Click **Create**.

3. **Register the Frontend Task Definition (`pg-frontend`):**
   - Click **Create new task definition with JSON** again, and paste the following JSON:
```json
{
  "family": "pg-frontend",
  "cpu": "256",
  "memory": "512",
  "networkMode": "awsvpc",
  "requiresCompatibilities": ["FARGATE"],
  "executionRoleArn": "arn:aws:iam::<aws-account-id>:role/ecsTaskExecutionRole",
  "containerDefinitions": [
    {
      "name": "frontend",
      "image": "<aws-account-id>.dkr.ecr.ap-southeast-1.amazonaws.com/pg-frontend:latest",
      "cpu": 256,
      "memory": 512,
      "portMappings": [
        {"containerPort": 80}
      ],
      "logConfiguration": {
        "logDriver": "awslogs",
        "options": {
          "awslogs-group": "/ecs/pg-logs",
          "awslogs-region": "ap-southeast-1",
          "awslogs-stream-prefix": "frontend"
        }
      }
    }
  ]
}
```
   - Click **Create**.

![Register the frontend task definition](/images/h40.png)
