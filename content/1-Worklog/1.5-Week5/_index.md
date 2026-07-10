---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
### Week 5 Objectives:

* Study information security architecture, identity management solutions, and centralized data encryption mechanisms on AWS.
* Study secure application authorization and dynamic identity security through AWS IAM Roles.
* Study advanced permission management models and conditional system access control through AWS IAM.
* Study resource-tag-based access control methodologies and decentralized management models through AWS IAM.
* Study unified security monitoring and automated compliance assessment methodologies on AWS.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Study the responsibility model and comprehensive identity management solutions<br>&emsp; + Analyze the security boundary between the provider and the customer under the Shared Responsibility Model<br>&emsp; + Learn authorization mechanisms and least-privilege policy management through AWS IAM<br>&emsp; + Explore authentication, authorization, and end-user identity management architecture for web/mobile applications through Amazon Cognito<br>- Explore multi-account management and data protection encryption systems<br>&emsp; + Study enterprise resource grouping and centralized policy enforcement through AWS Organizations<br>&emsp; + Analyze the technical nature of creating, managing, and auditing encryption key lifecycles with AWS KMS<br>&emsp; + Learn the model for consolidating security data and automating infrastructure security standard assessments through AWS Security Hub | 18/05/2026   | 18/05/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 3   | - Study the cybersecurity risks of static authentication methods in the cloud computing ecosystem<br>&emsp; + Analyze the nature and operation of fixed Access Key and Secret Access Key credentials when granting access to the S3 storage service<br>&emsp; + Identify security threats and serious data-leak vulnerabilities caused by hard-coding credentials in application source code<br>- Explore optimal security methodologies through advanced temporary identities<br>&emsp; + Study the architecture for establishing Trust Policies and dynamically assigning permissions through IAM Roles to EC2 virtual servers<br>&emsp; + Analyze automatic issuance and rotation of temporary security credentials to eliminate the storage of static keys | 19/05/2026   | 19/05/2026      | <https://000048.awsstudygroup.com>        |
| 4   | - Study layered privilege organization and centralized management through IAM entities<br>&emsp; + Analyze IAM Group architecture for synchronizing and enforcing least-privilege policies across core service areas such as EC2 and RDS<br>&emsp; + Learn permission separation and temporary administrative delegation through Switch Role<br>- Explore context-aware security through policy condition logic<br>&emsp; + Study IAM Policy Condition structures for establishing dynamic security boundaries around cloud resources<br>&emsp; + Analyze permission restrictions based on environmental parameters such as corporate source IP addresses and defined execution time windows | 20/05/2026   | 20/05/2026      | <https://000044.awsstudygroup.com/>       |
| 5   | - Study tag-attribute-based authorization in the cloud computing ecosystem<br>&emsp; + Analyze the technical nature of Attribute-Based Access Control (ABAC) and IAM Policy structures associated with Resource Tags<br>&emsp; + Learn how to configure strict conditions that limit permissions to create, modify, or delete EC2 virtual servers<br>- Explore layered administration and decentralized identity delegation<br>&emsp; + Study secure policy distribution by indirectly assigning permissions to functional IAM Role entities<br>&emsp; + Analyze the principles for testing, examining, and validating the correctness of logical statements in security policies when applying role switching | 21/05/2026   | 21/05/2026      | <https://000028.awsstudygroup.com/>       |
| 6   | - Study the operation of the cloud security management center and configuration tracking solutions<br>&emsp; + Analyze the technical nature, data integration flow, and continuous resource collection between AWS Security Hub and AWS Config<br>&emsp; + Learn automated infrastructure scanning, vulnerability detection, and real-time system security score calculation<br>- Explore risk assessment and management methodologies based on international security frameworks<br>&emsp; + Study the structure and core assessment criteria of AWS Foundational Security Best Practices, CIS AWS Foundations Benchmark, and PCI DSS<br>&emsp; + Analyze risk alert severity classification and methodologies for customizing and refining audit controls to suit actual enterprise operating contexts | 22/05/2026   | 22/05/2026      | <https://000018.awsstudygroup.com/>       |

### Week 5 Achievements:

* Understood cloud security concepts and advanced identity management mechanisms (IAM & Amazon Cognito):
  * Mastered the security boundary principles of the Shared Responsibility Model and clearly identified user responsibilities for application- and data-layer security configuration.
  * Conducted an in-depth analysis of Zero-Trust access management through IAM Groups, policy enforcement, and consistent least-privilege authorization across core services such as EC2 and RDS.
  * Explored Amazon Cognito centralized identity management through User Pools and Identity Pools, and understood advanced authentication flows and secure end-user access authorization.

* Studied dynamic identity-based authorization and advanced policy condition control:
  * Identified the serious security vulnerability of using static credentials such as Access Keys in source code and understood the temporary credential rotation mechanism of AWS Security Token Service (STS) through IAM Role trust delegation architecture.
  * Mastered flexible authorization management through Switch Role, combined with context-aware IAM Conditions to block access by source IP range using aws:SourceIp and by time window using aws:CurrentTime.
  * Understood Attribute-Based Access Control (ABAC), using Resource Tags to define privilege boundaries, require identity tags at resource creation time, and prevent unauthorized changes to infrastructure structures.

* Studied multi-account control, encryption, and centralized security monitoring architecture:
  * Understood large-scale infrastructure management through AWS Organizations and the enforcement of Service Control Policies (SCPs) to establish security guardrails for all member accounts.
  * Conducted an in-depth analysis of encryption at rest through Amazon S3 server-side encryption with SSE-KMS and the operation of AWS-managed and Customer Managed KMS keys to optimize information protection.
  * Mastered the integration of security data from AWS Config into AWS Security Hub and understood vulnerability scanning, Security Score calculation, automated assessment against AWS Foundational, CIS Benchmark, and PCI DSS standards, and the customization of excluded controls through Controls Customization.
