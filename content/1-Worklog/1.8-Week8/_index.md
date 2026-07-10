---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 8 Objectives:

* Analyze the requirements and define the scope of the High Concurrency Payment Gateway project for load testing a high-throughput payment system.
* Design a microservices architecture consisting of API Gateway, Payment Service, Account Service, and Transaction Service.
* Initialize a Java 21, Spring Boot, and Gradle multi-module project with reusable shared libraries.
* Set up a local development environment with PostgreSQL, Redis, and Docker Compose for the implementation phase.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Analyze the high-concurrency payment gateway problem<br>&emsp; + Identify data consistency, duplicate-processing prevention, and fault-tolerance requirements<br>&emsp; + Define the main flows: account creation, debit, credit, payment creation, and transaction lookup | 06/08/2026 | 06/08/2026 | Project description and system source code |
| 3 | - Design the microservices architecture and source-code structure<br>&emsp; + Separate API Gateway, Account Service, Payment Service, and Transaction Service<br>&emsp; + Define the responsibility, runtime port, and dedicated database of each service | 06/09/2026 | 06/09/2026 | <https://spring.io/projects/spring-boot> |
| 4 | - Initialize the Java 21 Gradle multi-module project<br>&emsp; + Create service modules and the shared `common-dto` and `common-exception` libraries<br>&emsp; + Configure Spring Web, Validation, JPA, Actuator, and PostgreSQL dependencies | 06/10/2026 | 06/10/2026 | <https://docs.gradle.org/> |
| 5 | - Set up the local data environment<br>&emsp; + Configure Docker Compose for PostgreSQL and Redis<br>&emsp; + Create separate `paymentservice`, `accountservice`, and `transactionservice` databases<br>&emsp; + Standardize database connection environment variables | 06/11/2026 | 06/11/2026 | <https://docs.docker.com/compose/> |
| 6 | - Build the initial service skeletons<br>&emsp; + Create basic entities, repositories, services, controllers, and DTOs<br>&emsp; + Standardize API responses, error codes, and shared exception handling<br>&emsp; + Configure health checks through Spring Boot Actuator | 06/12/2026 | 06/12/2026 | High Concurrency Payment Gateway source code |

### Week 8 Achievements:

* Completed the scope analysis and identified the main technical requirements of a high-throughput payment system:
  * Established idempotency as a mandatory mechanism to prevent a payment or debit request from being executed more than once.
  * Selected Redis for rate limiting, caching, and distributed locking, while PostgreSQL provides durable transaction storage.
  * Clearly separated the responsibilities of each microservice and avoided direct cross-service database access.

* Successfully initialized the Gradle multi-module structure:
  * Created four service modules: API Gateway, Account Service, Payment Service, and Transaction Service.
  * Created `common-dto` and `common-exception` libraries to reuse response formats and error definitions.
  * Standardized package organization into controller, service, repository, entity, DTO, mapper, and exception layers.

* Completed the local development environment:
  * Started PostgreSQL and Redis with Docker Compose.
  * Created separate databases for the business services.
  * Configured development profiles, environment variables, service ports, and health-check endpoints.
