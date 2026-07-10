---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:

* Study maximum permission boundary controls and solutions for preventing privilege escalation risks in AWS IAM.
* Study storage encryption with AWS KMS and automated data monitoring and audit-query solutions.
* Study the architecture, operating mechanisms, and optimization methodologies of database services on AWS.
* Study the SQL language system on W3Schools for relational database administration.
* Study the operation, multi-layer secure connectivity architecture, and data backup solutions of Amazon RDS.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Study permission boundaries in cloud identity management systems<br>&emsp; + Analyze the technical nature of Permission Boundaries and the permission intersection algorithm used during policy evaluation<br>&emsp; + Learn how to apply boundaries to IAM User entities to tightly control broad delegated policies<br>- Explore solutions for preventing privilege escalation vulnerabilities and managing geographic restrictions<br>&emsp; + Study methods for identifying Privilege Escalation risks associated with foundational identity accounts<br>&emsp; + Analyze methodologies for defining Region-based condition blocks to limit the geographic scope of resource administration | 25/05/2026   | 25/05/2026      | <https://000030.awsstudygroup.com/>       |
| 3   | - Study data encryption security for cloud storage at rest<br>&emsp; + Analyze the technical nature of automatic encryption on Amazon S3 using customer-managed encryption keys (SSE-KMS)<br>&emsp; + Learn access privilege control, public data blocking, and time-limited information sharing through Presigned URLs<br>- Explore event log collection architecture and advanced system audit query methodologies<br>&emsp; + Study the automatic real-time recording of Data Events through AWS CloudTrail<br>&emsp; + Analyze methodologies for integrating unstructured text logs into the serverless Amazon Athena query engine using standard SQL | 26/05/2026   | 26/05/2026      | <https://000033.awsstudygroup.com/>       |
| 4   | - Study database classification methodologies and advanced relational database solutions<br>&emsp; + Analyze the nature of data models and develop an approach for selecting storage structures for application infrastructure requirements<br>&emsp; + Learn the automated management model of Amazon RDS and analyze the cloud-native architecture of Amazon Aurora<br>- Explore large-scale data analytics and performance-optimized caching solutions<br>&emsp; + Distinguish the technical characteristics of Online Transaction Processing (OLTP) and Online Analytical Processing (OLAP) through Amazon Redshift data warehousing<br>&emsp; + Study In-memory Caching during the query lifecycle through Amazon ElastiCache using Redis and Memcached | 27/05/2026   | 27/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 5   | - Explore and systematize standard structured data language syntax through W3Schools<br>&emsp; + Analyze the technical characteristics and data extraction methodologies of advanced query commands<br>&emsp; + Study the logical model and effects of Data Manipulation Language (DML) and Data Definition Language (DDL) command groups<br>- Study complex data processing solutions in an online academic environment<br>&emsp; + Explore multi-table join algorithms, grouping mechanisms, and specialized group constraint conditions on W3Schools<br>&emsp; + Standardize SQL script structures as a technical foundation for optimizing query performance on Amazon RDS | 28/05/2026   | 28/05/2026      | <https://www.w3schools.com/sql/>          |
| 6   | - Study Amazon RDS infrastructure architecture and secure connectivity mechanisms<br>&emsp; + Analyze solutions for configuring internal network segments, inter-layer routing, and Security Group traffic filtering for servers and databases<br>&emsp; + Learn integration models, encrypted Endpoint communication, and secure identity information management between applications and cloud data entities<br>- Explore operational management methodologies and information protection strategies<br>&emsp; + Study Automated Backups and the creation of fixed system-state copies through Manual Snapshots<br>&emsp; + Analyze Point-In-Time Recovery to ensure resource integrity against system risks | 29/05/2026   | 29/05/2026      | <https://000005.awsstudygroup.com/>       |

### Week 6 Achievements:

* Understood permission boundary architecture and privilege escalation prevention mechanisms (IAM Permission Boundary):
  * Mastered methodologies for building Maximum Permissions policies and understood how permission intersection filters override and effectively isolate broad Full Access policies.
  * Conducted an in-depth analysis of AWS IAM logic when combining Identity-based Policies and Permission Boundaries to precisely determine the permitted action boundary of an account and eliminate privilege abuse or Privilege Escalation risks.
  * Explored context-based permission restrictions by geographic Region to prevent administrative actions outside the enterprise's authorized scope.

* Understood advanced storage encryption architecture and audit log analysis solutions (CloudTrail & Athena):
  * Mastered Amazon S3 server-side security through SSE-KMS and temporary identity distribution through cryptographically signed Presigned URLs with strict expiration constraints.
  * Understood the comprehensive tracing architecture of AWS CloudTrail and distinguished configuration flows through Management Events from data-operation flows through Data Events across real-time storage areas.
  * Analyzed the serverless query model of Amazon Athena and mastered methodologies for structuring raw text log repositories into logical relational tables with standard SQL for security incident investigations.

* Systematized database service classification and architecture concepts (Database Services):
  * Mastered methodologies for analyzing data characteristics to support flexible selection among relational databases (RDBMS), non-relational databases (NoSQL), In-memory caching, and centralized analytical data warehouses (OLAP).
  * Understood Amazon Aurora's separation of the Compute and Storage layers, including automatic recovery and cross-Availability-Zone data replication for improved system performance.
  * Clearly distinguished row-based storage for OLTP from column-based storage for OLAP in petabyte-scale Amazon Redshift, and understood Amazon ElastiCache In-memory Caching using Redis and Memcached to minimize application-layer latency.

* Standardized data extraction methodologies through the W3Schools learning platform:
  * Completed the study of logical design concepts and the operation of Data Definition Language (DDL) and Data Manipulation Language (DML) command groups based on W3Schools technical documentation.
  * Conducted an in-depth analysis of complex query clauses such as JOIN, GROUP BY, and HAVING, and understood processing algorithms and hardware resource optimization when joining multi-layer data at scale.

* Understood operational architecture, secure connectivity, and backup strategies on Amazon RDS:
  * Mastered methodologies for establishing separate security boundaries between the application layer (EC2) and data layer through least-privilege Security Group rules.
  * Conducted an in-depth analysis of internal network communication flows, Endpoint identification, and secure environment-variable linkage between application servers and cloud data entities.
  * Understood the technical differences between daily Automated Backups and fixed Manual Snapshots, and gained an in-depth understanding of Point-In-Time Recovery (PITR) based on Transaction Logs for responding to system risks.
