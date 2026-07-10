---
title : "Build & Push Images to ECR"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.2.2. </b> "
---

In this step, we will compile our Spring Boot microservices into JAR files, package them into Docker images, and push them to AWS ECR.

---

### Step 1: Compile Backend Source Code
1. Navigate to the Backend directory:
```bash
cd high-concurrency-payment-gateway
```
2. Compile the JAR files using Gradle:
```bash
./gradlew build -x test
```
*Verify that the build is successful and output JARs exist in the build directories.*

![Gradle build succeed](/images/5-Workshop/5.2-Prerequiste/5.2.2-build_success.png)

---

### Step 2: Create Private Repositories on ECR
1. Go to the AWS Console -> Search for **Elastic Container Registry (ECR)**.
2. Click **Create repository**:
   - Visibility: **Private**.
   - Name: `pg-combined-backend`. Click **Create**.
3. Repeat to create another repository named `pg-frontend`.

![ECR created](/images/5-Workshop/5.2-Prerequiste/5.2.2-ecr_creation.png)

---

### Step 3: Login and Push Images to ECR
Run these commands locally to push your images (Replace `<aws-region>` and `<aws-account-id>` with your own):

1. **Authenticate Docker with ECR:**
```bash
aws ecr get-login-password --region <aws-region> | docker login --username AWS --password-stdin <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com
```

2. **Build and Push the Backend image:** (From the `high-concurrency-payment-gateway` directory)
```bash
# Build the backend image
docker build -t pg-combined-backend -f backend.Dockerfile .

# Tag the image
docker tag pg-combined-backend:latest <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/pg-combined-backend:latest

# Push to ECR
docker push <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/pg-combined-backend:latest
```

3. **Build and Push the Frontend image:** (Navigate to `high-concurrency-payment-gateway-fe`)
```bash
cd ../high-concurrency-payment-gateway-fe

# Build the frontend image
docker build -t pg-frontend -f Dockerfile .

# Tag the image
docker tag pg-frontend:latest <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/pg-frontend:latest

# Push to ECR
docker push <aws-account-id>.dkr.ecr.<aws-region>.amazonaws.com/pg-frontend:latest
```

![ECR images pushed](/images/5-Workshop/5.2-Prerequiste/5.2.2-ecr_images.png)
