---
title: "Week 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---
### Week 8 Objectives:

* Begin developing the High-Concurrency Payment Gateway using a microservices architecture.
* Set up the development environment with JDK 21, Gradle multi-module, Docker, PostgreSQL, and Redis.
* Build the Account Service and its account and balance management APIs.
* Apply Flyway Migration, validation, centralized exception handling, Redis Cache, and idempotency for debit and credit operations.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Initialize the High-Concurrency Payment Gateway project structure<br>&emsp; + Configure JDK 21 and Gradle Wrapper<br>&emsp; + Set up Gradle multi-module for Account Service, Payment Service, Transaction Service, and API Gateway<br>&emsp; + Create shared libraries for common DTOs and exceptions | 08/06/2026 | 08/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Tuesday | - Set up the local runtime environment<br>&emsp; + Configure PostgreSQL and Redis with Docker Compose<br>&emsp; + Create the accountservice, paymentservice, and transactionservice databases<br>&emsp; + Configure Spring Boot connections to PostgreSQL and Redis<br>&emsp; + Initialize Flyway Migration scripts | 09/06/2026 | 09/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Wednesday | - Develop the Account Service<br>&emsp; + Design Account Entity, DTO, Repository, Service, Mapper, and Controller layers<br>&emsp; + Build APIs for account creation, account lookup, and balance retrieval<br>&emsp; + Add validation and standardized API responses | 10/06/2026 | 10/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thursday | - Implement safe balance updates<br>&emsp; + Develop debit and credit APIs<br>&emsp; + Use atomic updates to reduce race conditions under concurrent requests<br>&emsp; + Store Transaction History by transactionId<br>&emsp; + Detect duplicate idempotency requests and payload conflicts | 11/06/2026 | 11/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Friday | - Complete and test the Account Service<br>&emsp; + Integrate Redis Cache for account and balance data<br>&emsp; + Implement Global Exception Handler and business error codes<br>&emsp; + Test APIs with Postman<br>&emsp; + Fix database, Redis, and Flyway Migration issues | 12/06/2026 | 12/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Week 8 Achievements:

* Completed the Gradle multi-module structure and shared project libraries.
* Started PostgreSQL and Redis through Docker Compose and connected them successfully to Spring Boot.
* Completed the Account Service APIs for account creation, account lookup, balance retrieval, debit, and credit operations.
* Applied atomic updates, transaction history, and idempotency to reduce duplicate transactions under concurrent requests.
* Integrated Redis Cache, Flyway Migration, validation, and centralized exception handling.
