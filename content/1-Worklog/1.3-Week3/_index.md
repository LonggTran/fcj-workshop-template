---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---
### Week 3 Objectives:

* Study cloud computing solutions and data storage architectures on Amazon EC2 virtual servers.
* Study cross-platform server operation and network-layer privilege control through AWS IAM.
* Study resource identification methodologies and centralized infrastructure grouping solutions on AWS.
* Study centralized monitoring models, system log data analysis, and automated alerting mechanisms on AWS.
* Study load-balancing solutions and automatic server infrastructure scaling mechanisms on AWS.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Study Amazon EC2 virtual server architecture and its related resource management components<br>&emsp; + Analyze the characteristics of Instance Types, AMI image structures, secure encryption mechanisms with Key Pairs, and User Data automation scripts<br>&emsp; + Learn the operating and distribution model of structured system Metadata<br>&emsp; + Explore automatic infrastructure scaling principles through Auto Scaling Groups<br>- Study storage solutions and cloud migration services<br>&emsp; + Distinguish the technical characteristics of EBS block volumes, temporary Instance Store storage, and shared file systems such as EFS/FSx<br>&emsp; + Explore simplified computing with AWS Lightsail and large-scale server migration through AWS Application Migration Service (MGN) | 04/05/2026   | 04/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Study multi-operating-system EC2 architecture and resource lifecycle management solutions<br>&emsp; + Analyze network-flow orchestration for Linux/Windows environments and secure SSH/RDP connection methods<br>&emsp; + Learn performance optimization processes through instance type conversion and system image management using AMIs/Snapshots<br>&emsp; + Explore methodologies for recovering from lost security keys using User Data scripts and Systems Manager<br>&emsp; + Study models for setting up Node.js, LAMP Stack, and XAMPP application environments across multiple operating systems<br>- Explore privilege control and security policy management through AWS IAM<br>&emsp; + Analyze mechanisms for restricting resource creation by geographic Region and specialized instance families<br>&emsp; + Learn how to restrict data deletion permissions based on corporate IP addresses and specific time conditions | 05/05/2026   | 05/05/2026      | <https://000004.awsstudygroup.com/> |
| 4   | - Study resource identification through the AWS Tags classification system<br>&emsp; + Analyze tag hierarchy, naming conventions, and tag lifecycles<br>&emsp; + Learn methodologies for filtering, querying, and automatically classifying servers based on tag metadata<br>&emsp; + Explore automated synchronized tagging of related resources at creation time<br>- Explore centralized infrastructure management through AWS Resource Groups<br>&emsp; + Study automatic resource grouping based on filtering conditions and tag rules<br>&emsp; + Analyze the transition from managing individual servers to managing systems by project and environment | 06/05/2026   | 06/05/2026      | <https://000027.awsstudygroup.com/> |
| 5   | - Study performance measurement and log management through Amazon CloudWatch<br>&emsp; + Analyze the technical nature of Metrics, methodologies for applying mathematical expressions, and dynamic label structures for data visualization<br>&emsp; + Learn the centralized collection and storage model of CloudWatch Logs and query optimization through Logs Insights<br>&emsp; + Explore how CloudWatch Metric Filters convert text data into quantitative metrics<br>- Explore automated risk alerting and centralized management architecture<br>&emsp; + Study safe threshold configuration and the automated action-triggering principles of CloudWatch Alarms<br>&emsp; + Learn the integration model for notification services and methodologies for designing centralized CloudWatch Dashboards | 07/05/2026   | 07/05/2026      | <https://000008.awsstudygroup.com/> |
| 6   | - Study traffic distribution solutions and infrastructure template standardization<br>&emsp; + Analyze the technical nature of packaging AMI system images and the structure of Launch Templates<br>&emsp; + Learn the operating model and health-check mechanisms of Application Load Balancers and Target Groups<br>- Explore the operating principles of Auto Scaling Groups<br>&emsp; + Study manual resource adjustment and fixed recurring scheduled scaling<br>&emsp; + Analyze dynamic scaling algorithms based on actual system performance metrics<br>&emsp; + Explore historical data analysis and predictive graph interpretation to provision infrastructure resources in advance | 08/05/2026   | 08/05/2026      | <https://000006.awsstudygroup.com/> |

### Week 3 Achievements:

* Understood cross-platform virtual server architecture and storage methods:
  * Mastered the principles of configuring compute infrastructure by optimizing Instance Types, system images (AMIs), and Metadata/User Data configuration structures on both Linux and Windows Server.
  * Clearly distinguished the technical characteristics, speed, and durability of EBS block storage, including cost-optimized EBS Snapshot Archive, local Instance Store storage, and large-scale shared file systems such as EFS/FSx.
  * Explored application deployment architectures for Node.js/LAMP/XAMPP and remote access recovery techniques (Zero-Key Recovery) through advanced configuration features.

* Studied advanced security solutions and privilege control mechanisms (AWS IAM):
  * Understood Zero-Trust access management, advanced security layering, and closed internal communication through Systems Manager without relying on traditional security keys.
  * Conducted an in-depth analysis of IAM policy conditions to restrict resource creation and prevent deletion risks based on geographic Region, storage volume type, corporate IP address, and time frame.

* Understood identification strategies and centralized infrastructure management (Tags & Resource Groups):
  * Mastered methodologies for creating system tagging standards such as Owner and Environment, along with synchronized automated tagging to optimize resource search and management.
  * Explored the Resource Groups operating model for automatically grouping resources and transitioning from granular management to centralized project- or environment-based management across Dev, Staging, and Production.

* Understood measurement architecture and log analysis methodologies (Amazon CloudWatch):
  * Mastered performance data extraction using mathematical expressions and dynamic labels, and developed proficiency in analyzing error-event strings using Logs Insights queries and Metric Filters.
  * Analyzed the automated information flow between metric monitoring systems and CloudWatch Alarms when anomalies are detected, combined with consolidating visual data into a single Dashboard interface.

* Studied load orchestration and system scaling solutions (ELB & Auto Scaling Group):
  * Conducted an in-depth analysis of application-layer load distribution through ALB combined with standardized Launch Templates to ensure consistency and high availability.
  * Gained a comprehensive understanding of infrastructure scaling mechanisms, including manual, scheduled, dynamic, and predictive scaling based on historical data, to balance actual user performance requirements and cloud financial risk.
  * Explored the packaged computing model of AWS Lightsail for small systems and the large-scale migration process from physical infrastructure to the cloud using AWS MGN.
