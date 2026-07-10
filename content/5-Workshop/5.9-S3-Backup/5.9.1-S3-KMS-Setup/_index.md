---
title : "Create S3 Bucket & KMS Key"
date : 2024-01-01 
weight : 1
chapter : false
pre : " <b> 5.9.1. </b> "
---

We will set up the S3 Bucket to hold our backups and provision a customer-managed KMS key for encryption.

---

### Step 1: Create an S3 Bucket for Backup Storage
1. Navigate to the **S3** service on the AWS Console -> Click **Create bucket**.
2. Configure the settings:
   - **Bucket name**: Enter a globally unique name (e.g., **`pg-db-backups-795938553282-ap-southeast-1-an`**).
   - **AWS Region**: Select **ap-southeast-1** (Singapore).
   - Leave other settings as default. Click **Create bucket**.

![Create the S3 backup bucket](/images/h61.png)

---

### Step 2: Create a Custom KMS Key (Customer Managed Key)
AWS does not allow using default system-managed KMS keys (like `aws/s3` or `aws/rds`) for S3 exports because their policies cannot be edited. We need to create a symmetric customer-managed key:
1. Search for and open the **Key Management Service (KMS)** service on the AWS Console.
2. In the left menu, select **Customer managed keys** -> Click **Create key**.
3. Configure the key:
   - **Key type**: Select **Symmetric**. Click **Next**.
   - **Alias**: Enter `pg-s3-export-key`. Click **Next**.
   - **Key administrators**: Check your current IAM User. Click **Next**.
   - **Key users**: Check your current IAM User. Click **Next** -> Click **Finish**.

![Create the customer-managed KMS key](/images/h62.png)
