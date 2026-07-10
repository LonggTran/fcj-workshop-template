---
title : "RDS S3 Backup & Recovery Integration"
date : 2024-01-01 
weight : 9
chapter : false
pre : " <b> 5.9. </b> "
---

In this section, we will establish a production-grade database backup and recovery solution: Creating a manual Snapshot of our RDS PostgreSQL database and exporting it to an **Amazon S3 Bucket**, encrypted with a custom **AWS KMS Key**.

#### Contents:

1. [Create S3 Bucket & KMS Key](5.9.1-S3-KMS-Setup/)
2. [Create IAM Policy & Role for RDS](5.9.2-IAM-Policy-Role/)
3. [Create DB Snapshot & Export to S3](5.9.3-Export-Snapshot/)
