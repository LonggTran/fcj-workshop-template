---
title : "Configure AWS CLI & Clone Source Code"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.2.1. </b> "
---

In this step, we will configure our local AWS credentials using the AWS CLI and retrieve the microservices source code from Git.

---

### Step 1: Configure AWS CLI Credentials
Open your Terminal or PowerShell window and run the configure command:
```bash
aws configure
```
Input your credentials:
- **AWS Access Key ID**: Enter your Access Key ID
- **AWS Secret Access Key**: Enter your Secret Access Key
- **Default region name**: e.g., `ap-southeast-1`
- **Default output format**: `json`

![AWS CLI Configure](/images/h1.png)

---

### Step 2: Clone Repositories
Run the Git command to clone both projects:

1. **Clone the Backend repository:**
```bash
git clone https://github.com/your-username/high-concurrency-payment-gateway.git
```
2. **Clone the Frontend repository:**
```bash
git clone https://github.com/your-username/high-concurrency-payment-gateway-fe.git
```

![Git Clone Projects](/images/h2.png)
