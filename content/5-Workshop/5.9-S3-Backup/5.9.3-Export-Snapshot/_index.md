---
title : "Create DB Snapshot & Export to S3"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.9.3. </b> "
---

We will take a manual snapshot of our database and export its contents to S3.

---

### Steps:

1. **Create DB Snapshot:**
   - In the **RDS Console**, select Databases -> Select `pg-db`.
   - Click **Actions** -> Select **Take snapshot** -> Name it `pg-db-snapshot-manual` -> Click **Take snapshot**.
   - Wait until the snapshot status turns **Available**.
2. **Export Snapshot to S3:**
   - Go to RDS -> Select **Snapshots** -> Go to the **Manual** tab -> Check `pg-db-snapshot-manual`.
   - Click **Actions** -> Select **Export to Amazon S3**.
3. **Configure the Export Parameters:**
   - **Export identifier**: `pg-db-export-to-s3`.
   - **S3 bucket**: Select your S3 bucket: `pg-db-backups-795938553282-ap-southeast-1-an`.
   - **IAM role**: Select **Choose an existing role** -> Select **`rds-s3-export-role`**.
   - **Encryption (KMS key)**: Select **`pg-s3-export-key`**.
4. Click **Export to Amazon S3** to begin the process.

![Export Snapshot to S3](/images/5-Workshop/5.9-S3-Backup/5.9.3-s3_export.png)
