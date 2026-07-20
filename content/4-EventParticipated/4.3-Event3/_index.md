---
title: "Event 3"
date: 2026-06-06
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---
# Summary Report “FCJ Community Day - From Zero to Cloud Hero”

### Event Overview

The event provided practical perspectives on several technologies used in modern systems: real-time communication with WebSocket, application packaging with Docker, GraphRAG on AWS, machine-learning-based cyberattack detection, and the career path from IT Helpdesk to Modern DevOps.

### Technical Highlights

#### 1. Building real-time connections with Serverless WebSocket

**Nguyen Quoc Bao** presented **“Multiplayer in the Cloud: Connecting Godot Clients with AWS WebSockets.”** The architecture used **Amazon API Gateway WebSocket, AWS Lambda**, and **Amazon DynamoDB** to manage connections, waiting states, and player matching.

Routes such as `$connect`, `$disconnect`, and `$default` separated connection lifecycle management from game-message handling. This model is suitable for bidirectional applications that do not require a continuously running server. For games with high-frequency synchronization and complex physics, **AWS GameLift** was introduced as a more appropriate future direction.

#### 2. Improving deployment consistency with Docker

**Bao Huynh** explained the difference between virtual machines and containers. Docker packages an application together with its dependencies while sharing the host operating system, which reduces resource consumption and startup time compared with a full VM.

Important concepts included:

- Images composed of multiple read-only layers;
- A writable container layer created at runtime;
- Build cache reuse to shorten image creation time;
- Image, container, network, and volume management;
- Docker Compose for running multiple application components.

#### 3. Adding contextual relationships with GraphRAG

**Viet Phat** explained how GraphRAG addresses the limitations of traditional RAG. Instead of retrieving only vector-similar text chunks, GraphRAG organizes knowledge into **nodes** and **edges**, allowing the model to understand relationships between entities distributed across different sources.

Two implementation approaches were introduced:

- A managed route using **Amazon Bedrock Knowledge Bases** with **Amazon Neptune Analytics**;
- A customizable route using **LlamaIndex**, Python, and Cypher queries when deeper control is required.

#### 4. Detecting attacks with AWS WAF and Machine Learning

**Le Hoang Gia Dai** presented a **Network Intrusion Detection System** that combined rule-based protection from **AWS WAF** with machine-learning anomaly detection. Network data was collected, cleaned, balanced, and used to compare several algorithms.

**LightGBM** was selected because of its strong evaluation results. In the AWS design, traffic data could flow through **Amazon Kinesis Data Firehose**, be stored in **Amazon S3**, processed by **AWS Lambda**, and generate notifications through **Amazon SNS**. This layered approach supports both known attack patterns and previously unseen abnormal behavior.

#### 5. Moving from IT Helpdesk to Modern DevOps

**Tran Trung Vinh** described a career journey from IT Helpdesk to system administration and DevOps. User support, troubleshooting, and root-cause analysis were presented as valuable foundations before progressing to on-premises infrastructure, Linux, VMware, Cloud, and automation.

The learning roadmap covered:

- Linux and Networking;
- Git and source control;
- Cloud fundamentals;
- Docker and containers;
- CI/CD;
- Infrastructure as Code with Terraform;
- System orchestration;
- Monitoring and Observability.

### Knowledge and Skills Gained

- Understood how API Gateway WebSocket, Lambda, and DynamoDB work together in a real-time application.
- Learned the principles of image layers, container layers, and Docker build cache.
- Distinguished vector-based RAG from GraphRAG, which represents relationships between data entities.
- Gained insight into layered security that combines WAF, data pipelines, and machine learning.
- Identified the main skills required for a Cloud and DevOps career path.
- Recognized the long-term value of practical troubleshooting experience.

### Practical Application

- Use Docker to package services and maintain consistent deployment environments.
- Optimize Dockerfiles through better layer ordering and build-cache reuse.
- Explore WebSocket for features that need real-time state updates.
- Study AWS WAF, CloudWatch, and SNS for stronger monitoring and alerting.
- Continue developing Linux, Networking, CI/CD, and Infrastructure as Code skills.

### Event Reflection

The event covered a wide range of topics while maintaining a clear connection between development, AI, security, and operations. Each session showed that a reliable system requires more than correct source code; it also needs suitable architecture, consistent deployment, observability, and protection. The final career story reinforced that professional growth is built by mastering fundamentals and solving practical problems step by step.

### Some event photos
![Event 3](/images/b8.jpg)
![Event 3](/images/b9.jpg)
![Event 3](/images/b10.jpg)

> **FCJ Community Day - From Zero to Cloud Hero** connected WebSocket, Docker, GraphRAG, cybersecurity, and DevOps into a practical learning direction for modern cloud projects.
