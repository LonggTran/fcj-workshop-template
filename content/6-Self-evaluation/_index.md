---
title: "Self-Assessment"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

During the 12-week **First Cloud AI Journey** program, from **April 17, 2026 to July 11, 2026**, I strengthened my knowledge of cloud computing, backend development, and application deployment on AWS. The internship helped me better understand how to combine theoretical knowledge with building, testing, and monitoring a practical system.

My main project was the **High-Concurrency Payment Gateway**, a system designed to test payment processing under high load. The backend was developed with Spring Boot using a microservices architecture consisting of API Gateway Service, Account Service, Payment Service, and Transaction Service. PostgreSQL was used for data storage, Redis supported caching and rate limiting, and Docker was used to package the system components.

To reduce errors when multiple requests process the same account, the project applied idempotency keys, conditional atomic balance updates, processing tokens and leases, a Recovery Worker, Retry, and Circuit Breaker. The application was packaged and deployed experimentally using Amazon ECR, ECS Fargate, Application Load Balancer, RDS PostgreSQL, VPC, and CloudWatch. k6 was used to generate load and verify balance consistency after transaction processing.

The demo results showed that the system maintained the correct balance and reduced duplicate transaction processing under concurrent load. However, the tests also revealed limitations: during the 10,000-request run, 22 requests were unsuccessful, and P95 latency exceeded the expected threshold. Therefore, the current project should be considered a **technical prototype and demonstration system**, rather than a production-ready payment platform.

To objectively reflect on my learning process and project implementation, I evaluate myself according to the following criteria:

| No. | Criteria                            | Description                                                                                                             | Good | Fair | Average |
| --- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---- | ---- | ------- |
| 1   | **Professional knowledge & skills** | Applied Spring Boot, PostgreSQL, Redis, Docker, and AWS services; performance optimization still requires improvement   | ☐    | ✅    | ☐       |
| 2   | **Ability to learn**                | Proactively studied new documentation, AWS services, and concurrent transaction-handling techniques                    | ✅    | ☐    | ☐       |
| 3   | **Proactiveness**                   | Independently investigated errors and proposed fixes, but needs more structured work planning                           | ☐    | ✅    | ☐       |
| 4   | **Sense of responsibility**         | Completed the main worklog, workshop, report, source code, and project demonstration deliverables                       | ✅    | ☐    | ☐       |
| 5   | **Discipline**                      | Followed security and AWS resource-management requirements; progress and resource checks should be more consistent      | ☐    | ✅    | ☐       |
| 6   | **Drive for improvement**           | Accepted feedback on source code, architecture, and reporting, then continuously revised the deliverables               | ✅    | ☐    | ☐       |
| 7   | **Communication**                   | Explained the system flow and test results, but needs to communicate more concisely and confidently                     | ☐    | ✅    | ☐       |
| 8   | **Teamwork**                        | Communicated and coordinated with team members; experience with code review and Agile workflows remains limited         | ☐    | ✅    | ☐       |
| 9   | **Professional conduct**            | Maintained a serious attitude, respected mentors, and handled AWS accounts, data, and resources responsibly             | ✅    | ☐    | ☐       |
| 10  | **Problem-solving skills**          | Analyzed data, concurrency, and deployment issues; the latency problem has not yet been fully resolved                  | ☐    | ✅    | ☐       |
| 11  | **Contribution to project/team**    | Completed the source code, documentation, architecture diagram, and demo, although further standardization is needed    | ☐    | ☐    | ✅       |
| 12  | **Overall assessment**              | Achieved the main objectives and produced a system that can be demonstrated, experimentally deployed, and load tested   | ☐    | ✅    | ☐       |

### Achievements

* Built the main services and integrated the account creation, payment processing, and transaction history flows.
* Applied idempotency, atomic updates, processing tokens, and leases to reduce duplicate processing and balance inconsistencies.
* Packaged the application with Docker, pushed images to Amazon ECR, and experimentally deployed it on Amazon ECS Fargate.
* Connected the backend to Amazon RDS PostgreSQL, distributed requests through an Application Load Balancer, and monitored the system with CloudWatch.
* Performed load testing with k6, compared expected and actual balances, and identified latency and error-rate limitations.
* Completed worklogs, workshop documentation, bilingual reports, the architecture diagram, and the project demonstration video.

### Areas for Improvement

* Optimize P95 latency, database connection pools, queries, and ECS configuration so the system performs better as load increases.
* Add automated tests for concurrency, timeouts, retries, service interruptions, and invariant verification after load tests.
* Standardize deployment with Infrastructure as Code and CI/CD instead of relying heavily on manual AWS Console operations.
* Improve production security knowledge, including secret management, TLS, least-privilege IAM, and private service connectivity.
* Improve technical communication, English presentation, time management, and collaboration through Git and Agile workflows.

### Development Direction

After the program, I will continue optimizing the project, completing its automated test suite, and standardizing the deployment process. I will also deepen my knowledge of AWS, DevOps, distributed systems, observability, and Infrastructure as Code so that the project can evolve from a technical prototype into a more stable and maintainable system.
