---
title : "Create IAM Policy & Role for RDS"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.9.2. </b> "
---

We will define the security IAM policies and roles allowing RDS to securely write data to our S3 bucket.

---

### Step 1: Create a Custom IAM Policy (`rds-s3-export-policy`)
1. Open the **IAM** service -> Select **Policies** -> Click **Create policy**.
2. Select the **JSON** tab, clear the default template, and paste the JSON block below (ensure the bucket name matches your actual S3 bucket):
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ExportPolicy",
            "Effect": "Allow",
            "Action": [
                "s3:PutObject*",
                "s3:ListBucket",
                "s3:GetObject*",
                "s3:DeleteObject*",
                "s3:GetBucketLocation"
            ],
            "Resource": [
                "arn:aws:s3:::pg-db-backups-795938553282-ap-southeast-1-an",
                "arn:aws:s3:::pg-db-backups-795938553282-ap-southeast-1-an/*"
            ]
        }
    ]
}
```

![Create the custom IAM policy](/images/h63.png)

3. Click **Next** -> Name the policy **`rds-s3-export-policy`** -> Click **Create policy**.

---

### Step 2: Create an IAM Role with Custom Trust Policy (`rds-s3-export-role`)
We must allow the RDS export service (`export.rds.amazonaws.com`) to assume the role:
1. In the **IAM** console, select **Roles** -> Click **Create role**.
2. Select the **Custom trust policy** option at the bottom.
3. Paste the following trust policy JSON:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "export.rds.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
4. Click **Next** -> Search for and select the **`rds-s3-export-policy`** policy created in Step 1. Click **Next**.
5. Name the role **`rds-s3-export-role`** -> Click **Create role**.

![Create the RDS S3 export IAM role](/images/h64.png)
