---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Week 2 Objectives:

* Conduct an in-depth study of the infrastructure architecture and data-routing mechanisms of Amazon VPC virtual networks.
* Understand advanced system management solutions and the Zero-Trust security model through AWS Session Manager.
* Explore advanced inter-network connectivity solutions, including VPC Peering and the centralized routing hub AWS Transit Gateway.
* Study the operation of encrypted secure tunnels through AWS Site-to-Site VPN.
* Learn about Hybrid DNS resolution and the integration of DNS routing between AWS Route 53 and On-premises systems.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 1   | - Learn more about networking services on AWS:<br>&emsp; + Amazon Virtual Private Cloud (VPC)<br>&emsp; + VPC Peering & Transit Gateway<br>&emsp; + VPN & Direct Connect<br>&emsp; + Elastic Load Balancing | 24/04/2026   | 24/04/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 2   | - Study virtual network infrastructure architecture and routing mechanisms (Amazon VPC):<br>&emsp; + Clearly distinguish the roles of Public/Private Subnets, Route Tables, Internet Gateway (IGW), and NAT Gateway<br>&emsp; + Analyze Elastic IP allocation mechanisms and solutions for establishing secure one-way Internet connectivity for internal servers<br>&emsp; + Master methods for analyzing, visualizing, and monitoring the entire resource topology through VPC Resource Map<br>- Study multi-layer security mechanisms and network monitoring solutions:<br>&emsp; + Evaluate the operating principles of the two-layer security barrier: host firewall (Security Group) and network-layer filter (Network ACL)<br>&emsp; + Learn about advanced server access through an EIC Endpoint to improve security and reduce exposed connection ports<br>&emsp; + Explore how to use Reachability Analyzer to validate network paths and Amazon CloudWatch to configure alerts | 25/04/2026   | 25/04/2026      | <https://000003.awsstudygroup.com/> |
| 3   | - Explore inter-network connectivity and traffic orchestration solutions (Hybrid & Advanced Networking):<br>&emsp; + Understand the architecture of IPsec secure tunnels and the Virtual Private Gateway and Customer Gateway components used in AWS Site-to-Site VPN configurations<br>&emsp; + Understand routing principles and the process of analyzing and troubleshooting basic network connectivity issues<br>&emsp; + Learn Infrastructure as Code (IaC) concepts through AWS CloudFormation | 26/04/2026   | 26/04/2026      | <https://000003.awsstudygroup.com/> |
| 4   | - Study the overall architecture and operation of AWS Systems Manager Session Manager:<br>&emsp; + Analyze the model for managing and authorizing server access through AWS IAM Roles<br>&emsp; + Learn how to establish secure internal network connectivity by enabling virtual DNS resolution features<br>&emsp; + Explore secure communication through the ssm, ssmmessages, and ec2messages service endpoints<br>&emsp; + Study how to synchronize, record, and secure system operation history (Session Logs) on Amazon S3<br>&emsp; + Learn an internal routing optimization model using an S3 Gateway Endpoint<br>&emsp; + Explore port forwarding principles for remote graphical interface control | 27/04/2026   | 27/04/2026      | <https://000058.awsstudygroup.com/> |
| 5   | - Study network peering mechanisms through AWS VPC Peering:<br>&emsp; + Analyze the route table update model and data-routing mechanism across peering connections<br>&emsp; + Learn about Cross-Peer DNS for system domain-name resolution across connected networks<br>- Explore centralized large-scale network management with AWS Transit Gateway:<br>&emsp; + Study the operation of the central connectivity hub and network resource attachments<br>&emsp; + Analyze the principles of configuring unified route tables to orchestrate traffic among multiple independent network segments | 28/04/2026   | 28/04/2026      | <https://000019.awsstudygroup.com/><br><https://000020.awsstudygroup.com/> |
| 6   | - Study the operation of Hybrid DNS resolution systems:<br>&emsp; + Analyze an On-premises DNS simulation architecture using AWS Managed Microsoft AD integrated within a Private network<br>&emsp; + Understand bidirectional domain-query forwarding and routing through Route 53 Inbound and Outbound Endpoints<br>&emsp; + Study how to configure Resolver Rules for cross-environment identity resolution synchronization | 29/04/2026   | 29/04/2026      | <https://000010.awsstudygroup.com/> |

### Week 2 Achievements:

* Understood virtual network infrastructure architecture and routing mechanisms (Amazon VPC):
  * Clearly distinguished the roles of Public/Private Subnets, Route Tables, Internet Gateway (IGW), and NAT Gateway.
  * Analyzed Elastic IP allocation mechanisms and solutions for establishing secure one-way Internet connectivity for internal servers.
  * Mastered methods for analyzing, visualizing, and monitoring the entire resource topology through VPC Resource Map.

* Studied multi-layer security mechanisms and network monitoring solutions:
  * Evaluated the operating principles of the two-layer security barrier consisting of host firewalls (Security Groups) and network-layer filters (Network ACLs) according to the principle of least privilege.
  * Learned the advanced EC2 access model through an EIC Endpoint to improve security and reduce exposed connection ports.
  * Explored how to use Reachability Analyzer to validate network paths and Amazon CloudWatch (Dashboards, Metric Filters, and Alarms) to monitor system status.

* Explored inter-network connectivity and traffic orchestration solutions (Hybrid & Advanced Networking):
  * Understood the architecture of IPsec secure tunnels and the Virtual Private Gateway and Customer Gateway components used in AWS Site-to-Site VPN configurations.
  * Understood network routing principles, analysis processes, and operating-system-compatible troubleshooting methodologies for secure connectivity issues.
  * Learned traffic distribution concepts through Elastic Load Balancing (ELB) to improve fault tolerance and high availability for enterprise cloud systems.

* Understood advanced system management through AWS Session Manager:
  * Mastered secure authorization through IAM Roles, allowing virtual servers to connect and interact safely with the centralized management system.
  * Analyzed closed internal-network data flows through VPC Endpoints for ssm, ssmmessages, and ec2messages without exposing traditional public connection ports.
  * Explored the Zero-Trust access model, the process of recording Session Logs integrated with S3 cloud storage, and port forwarding principles for remote control.

* Understood network interconnection architecture and infrastructure optimization (VPC Peering & Transit Gateway):
  * Explored route table update principles for directly routing internal data flows between independent networks through peering connections and the resolution mechanism of Cross-Peer DNS.
  * Understood the operating model of AWS Transit Gateway as a central hub, including Associations, Propagations, and Attachments, for managing, orchestrating, and segmenting large-scale traffic in a Hub-and-Spoke topology.

* Studied Hybrid DNS resolution mechanisms:
  * Explored the technical nature of simulating an On-premises environment by deploying AWS Managed Microsoft AD in an isolated private network segment.
  * Mastered bidirectional resolution flow configuration by using an Outbound Endpoint with Resolver Rules to forward queries outward and an Inbound Endpoint to receive reverse resolution requests from On-premises systems into Private Hosted Zones.
