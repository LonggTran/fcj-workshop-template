---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}


### Week 7 Objectives:

* Systematize, review, and consolidate all theoretical knowledge and practical hands-on skills of AWS cloud service groups learned from Week 1 to Week 6.
* Systematize secure virtual network design, storage management, database optimization, and resource monitoring automation.
* Consolidate Zero-Trust security mindsets, least privilege permissions via IAM, advanced access controls (ABAC, Switch Role, Permission Boundary), and cloud infrastructure security standards.
* Address outstanding questions, summarize review materials, and complete hands-on lab exercises to prepare for the next phase.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Review Compute & Networking groups (EC2, VPC):<br>&emsp; + Systematize EC2 configurations, AMIs, Key Pairs, User Data & Metadata<br>&emsp; + Review VPC network structure: Subnets, Route Tables, IGW/NAT Gateway, Elastic IP<br>&emsp; + Review advanced networking connectivity: VPC Peering, Transit Gateway, SSM Session Manager & Endpoints | 06/01/2026 | 06/01/2026      | [Week 1](file:///d:/fcj-workshop-template/content/1-Worklog/1.1-Week1/_index.md), [Week 2](file:///d:/fcj-workshop-template/content/1-Worklog/1.2-Week2/_index.md) |
| 3   | - Review Storage & Content Delivery groups (S3, CloudFront, FSx):<br>&emsp; + Review S3 security features, storage lifecycle, Versioning, and CRR<br>&emsp; + Systematize CDN content distribution via CloudFront Edge Locations<br>&emsp; + Review Hybrid Storage Gateway and FSx for Windows File Server (Multi-AZ, Deduplication, Shadow Copies) | 06/02/2026 | 06/02/2026      | [Week 4](file:///d:/fcj-workshop-template/content/1-Worklog/1.4-Week4/_index.md) |
| 4   | - Review Security & Identity groups (IAM, KMS, AWS Organizations):<br>&emsp; + Consolidate IAM Policy, IAM Conditions, dynamic credentials (STS) & IAM Roles<br>&emsp; + Review Switch Role, Tag-based ABAC permission models, and Permission Boundaries<br>&emsp; + Systematize SCP enforcement via AWS Organizations and KMS encryption key management | 06/03/2026 | 06/03/2026      | [Week 5](file:///d:/fcj-workshop-template/content/1-Worklog/1.5-Week5/_index.md), [Week 6](file:///d:/fcj-workshop-template/content/1-Worklog/1.6-Week6/_index.md) |
| 5   | - Review Databases & Monitoring groups (RDS, CloudWatch, Security):<br>&emsp; + Systematize database options: RDS, Aurora, Redshift, ElastiCache (Redis/Memcached)<br>&emsp; + Review Automated Backups, Manual Snapshots, and PITR on RDS<br>&emsp; + Review CloudWatch Alarms, Logs Insights, and security monitoring via AWS Config & Security Hub (CIS, PCI DSS)<br>&emsp; + Practice advanced SQL queries on W3Schools | 06/04/2026 | 06/04/2026      | [Week 3](file:///d:/fcj-workshop-template/content/1-Worklog/1.3-Week3/_index.md), [Week 6](file:///d:/fcj-workshop-template/content/1-Worklog/1.6-Week6/_index.md) |
| 6   | - Consolidate and practice:<br>&emsp; + Redo challenging scenarios: Zero-Key Recovery via SSM, querying CloudTrail logs with Athena, configuring Switch Role & Permission Boundaries<br>&emsp; + Build a Mindmap to systematize the AWS services studied<br>&emsp; + Complete review documentation and address knowledge gaps | 06/05/2026 | 06/05/2026      | Internal consolidation document |


### Week 7 Achievements:

* **Comprehensive Systematization of Infrastructure & Secure Networking (Compute & Networking):**
  * Mastered configuration steps, EC2 instance sizing optimization, and leveraging metadata/user data to automate server initialization.
  * Understood VPC flow controls, setting up route tables, and ensuring Private Subnet instances connect securely to the Internet via NAT Gateway.
  * Consolidated VPN, VPC Peering, and Transit Gateway routing mechanics to link independent networks, and master Zero-Trust remote access via Systems Manager Session Manager.

* **Consolidation of Storage & Content Delivery Management:**
  * Mastered S3 multi-layered data protection (BPA, Bucket Policy, KMS, Versioning) and cost optimization using Lifecycle Policies.
  * Understood how to accelerate page load times and minimize latency globally using CloudFront CDN via Edge Locations.
  * Mastered FSx for Windows File Server shared directories configuration with advanced features like Data Deduplication and Shadow Copies.

* **Enhanced Security & Least Privilege Authorization (Security & Governance):**
  * Consolidated IAM Policies authoring, incorporating strict conditional constraints (IAM Conditions: aws:SourceIp, aws:CurrentTime).
  * Mastered Switch Role, flexible ABAC based on Resource Tags, and applying Permission Boundaries to mitigate Privilege Escalation risks.
  * Systematized multi-account management using SCPs in AWS Organizations and automated centralized backup scheduling via AWS Backup.

* **Proficiency in Database Optimization & Monitoring Automation:**
  * Distinguished when to deploy RDS/Aurora (OLTP), Redshift (OLAP), and ElastiCache (In-memory Caching) based on software workload requirements.
  * Mastered Point-In-Time Recovery (PITR) mechanisms for RDS and configured secure connectivity between EC2 and databases via Security Groups.
  * Mastered CloudWatch monitoring tools (Log Insights, Alarms, Dashboards) and Security Hub to audit compliance with security benchmarks (CIS, PCI DSS).

* **Improved Hands-on and Log Auditing Skills:**
  * Practiced capturing operational history via CloudTrail and writing SQL queries in Amazon Athena to analyze raw log data quickly.
  * Successfully built a Knowledge Map linking all learned services, completing documentation to prepare for the project's next challenges.
