---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:

* Study the advanced cloud storage ecosystem, hybrid integration models, and disaster recovery strategies on AWS.
* Study static content distribution on Amazon S3 and latency optimization with Amazon CloudFront.
* Study hybrid data synchronization between On-premises systems and Amazon S3 through AWS Storage Gateway.
* Study automated cloud resource backup planning and event monitoring through AWS SNS.
* Study high-performance shared file storage systems and advanced data management solutions on AWS.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Study object storage architecture and advanced data management through Amazon S3<br>&emsp; + Analyze storage tiering, file lifecycles, and security features that protect system data integrity<br>&emsp; + Explore large-scale physical data transfer methods through the AWS Snow Family product line<br>&emsp; + Learn the Hybrid Cloud storage model and data synchronization between On-premises systems and the cloud through AWS Storage Gateway<br>- Study information protection strategies and disaster recovery architecture<br>&emsp; + Analyze the two core metrics: Recovery Time Objective (RTO) and Recovery Point Objective (RPO)<br>&emsp; + Explore Disaster Recovery architecture models ranging from basic backup to active parallel configurations<br>&emsp; + Learn methodologies for centrally managing, defining policies, and automating backups with AWS Backup | 11/05/2026   | 11/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Study static website hosting and data security and management solutions on Amazon S3<br>&emsp; + Analyze access control policies through Block Public Access, Bucket Policies, and object authorization using Bucket ACLs<br>&emsp; + Learn Bucket Versioning for managing multiple data versions and preventing accidental overwrites or destruction<br>&emsp; + Explore automated cross-region data synchronization through Cross-Region Replication (CRR)<br>- Explore global content delivery acceleration and system troubleshooting methodologies<br>&emsp; + Study the wide-area distribution architecture of Amazon CloudFront edge caching to minimize latency<br>&emsp; + Explore performance optimization principles, storage budget management, and common S3 connectivity troubleshooting scenarios | 12/05/2026   | 12/05/2026      | <https://000057.awsstudygroup.com/> |
| 4   | - Study hybrid storage integration architecture through AWS File Storage Gateway<br>&emsp; + Analyze the operation of the dedicated virtual appliance, local Cache Volume, and firewall system protecting service ports<br>&emsp; + Learn the connection model and configuration used to map direct data-transfer flows into Amazon S3 Buckets<br>- Explore the operation and synchronization of internal file-sharing systems<br>&emsp; + Study the technical nature of the SMB file-sharing protocol combined with authorization mechanisms on Windows Server<br>&emsp; + Analyze network drive mapping and automated synchronization of local files to the cloud | 13/05/2026   | 13/05/2026      | <https://000024.awsstudygroup.com/> |
| 5   | - Study methodologies for automating data protection through AWS Backup<br>&emsp; + Analyze the architecture for creating strategic Backup Plans and secure isolation within dedicated Backup Vaults<br>&emsp; + Learn the model for automatically identifying and assigning protected resource targets based on Tags<br>- Explore system status event monitoring and centralized notification distribution<br>&emsp; + Study how storage event flows are connected to the Amazon SNS notification system<br>&emsp; + Analyze real-time automated information delivery when backup or data restoration processes are completed | 14/05/2026   | 14/05/2026      | <https://000013.awsstudygroup.com/> |
| 6   | - Study enterprise-scale shared file distribution architecture through Amazon FSx for Windows File Server<br>&emsp; + Analyze the technical nature of Multi-AZ storage using SSD/HDD configurations and continuously available SMB file sharing<br>&emsp; + Learn how to control, evaluate, and monitor throughput performance through CloudWatch Metrics<br>- Explore advanced management, disk-space optimization, and resource allocation solutions<br>&emsp; + Study Data Deduplication algorithms for reducing actual storage consumption<br>&emsp; + Analyze Shadow Copies for restoring historical file versions from end users<br>&emsp; + Explore methodologies for managing User Sessions, configuring User Quotas, and expanding storage capacity or throughput without system interruption | 15/05/2026   | 15/05/2026      | <https://000025.awsstudygroup.com/> |

### Week 4 Achievements:

* Understood the object storage ecosystem and wide-area network optimization solutions (Amazon S3 & CloudFront):
  * Mastered Amazon S3 operating principles, cost optimization through Lifecycle Policies, multi-layer access control using Block Public Access, Bucket Policies, and ACLs, and Versioning to reduce data-loss risks.
  * Analyzed automated Cross-Region Replication (CRR) for redundancy and improved system high availability.
  * Conducted an in-depth analysis of Amazon CloudFront content acceleration through Edge Locations to minimize latency and explored methodologies for diagnosing common S3 connectivity and authorization issues.

* Studied hybrid infrastructure risk management strategies and recovery methodologies (Hybrid Storage & Disaster Recovery):
  * Developed a system design approach based on comparing the core metrics RTO and RPO, and gained a complete understanding of the technical characteristics and trade-offs of four Disaster Recovery models ranging from basic recovery to Multi-Site Active-Active.
  * Analyzed hybrid storage through AWS Storage Gateway, including File, Volume, and Tape gateways, combined with the AWS Snow Family to address large-scale data migration in bandwidth-constrained locations.
  * Gained an in-depth understanding of AWS File Storage Gateway through the SMB protocol, local EBS Cache Volumes, and virtual network drive mapping to automatically synchronize files from On-premises systems to Amazon S3.

* Studied automated security and backup event monitoring (AWS Backup & SNS):
  * Mastered methodologies for configuring recurring system backup rules through Backup Plans and securely isolating backups in Backup Vaults, while using Tags to automatically group and scan large-scale protection targets.
  * Understood data integration and storage operation status extraction to establish event triggers integrated with Amazon SNS for automated real-time backup and restoration notifications.

* Understood high-performance shared file architecture and advanced management solutions (Amazon FSx):
  * Mastered enterprise storage infrastructure supporting Multi-AZ deployment, balancing cost between SSD/HDD storage, and providing Continuously Available Shares.
  * Conducted an in-depth analysis of throughput monitoring for Read/Write Performance through CloudWatch Metrics and the operation of Data Deduplication algorithms for optimizing physical storage space.
  * Understood Shadow Copies for restoring previous data versions, user connection orchestration through User Sessions/Open Files, User Quotas, and online storage or throughput upgrades without system downtime.
