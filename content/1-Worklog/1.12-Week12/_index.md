---
title: "Week 12 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 12 Objectives:

* Verify end-to-end integration after deploying the system to AWS.
* Design and execute functional, concurrency, idempotency, rate-limiting, and fault-tolerance test scenarios.
* Perform load testing to observe latency, error rate, resource utilization, and automatic-scaling behavior.
* Optimize configuration, fix defects, complete project documentation, and remove unused AWS resources.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Verify post-deployment integration<br>&emsp; + Check the health of API Gateway, ALB target groups, ECS tasks, RDS, and ElastiCache<br>&emsp; + Execute account creation, balance lookup, payment creation, and transaction lookup through the common endpoint<br>&emsp; + Inspect logs and traceId propagation across services when errors occur | 07/06/2026 | 07/06/2026 | Deployed system and CloudWatch Logs |
| 3 | - Test idempotency and consistency<br>&emsp; + Repeat requests with the same Payment Service `idempotencyKey`<br>&emsp; + Send concurrent requests with the same Account Service `transactionId`<br>&emsp; + Verify that matching duplicates do not debit again and different payloads return a conflict | 07/07/2026 | 07/07/2026 | Project API test scenarios |
| 4 | - Test concurrency, rate limiting, and fault tolerance<br>&emsp; + Send parallel requests to the payment-creation API<br>&emsp; + Verify user-based limits and HTTP 429 responses when the threshold is exceeded<br>&emsp; + Simulate a slow or temporarily unavailable Account Service to observe Retry, Circuit Breaker, and PROCESSING status behavior | 07/08/2026 | 07/08/2026 | Payment Service and API Gateway source code |
| 5 | - Run load tests and monitor the system<br>&emsp; + Gradually increase virtual users and request volume in each test stage<br>&emsp; + Monitor latency, throughput, error rate, CPU, memory, ECS task count, database connections, and Redis<br>&emsp; + Observe ECS Service Auto Scaling and identify application or infrastructure bottlenecks | 07/09/2026 | 07/09/2026 | Amazon CloudWatch and load-testing tool |
| 6 | - Optimize, retest, and finalize the project<br>&emsp; + Adjust timeout, Retry, rate-limit thresholds, CPU/memory, and scaling policies<br>&emsp; + Run regression tests for the main flows after defect fixes<br>&emsp; + Finalize the architecture diagram, worklog, test report, and remove or stop unnecessary AWS resources to avoid additional cost | 07/10/2026 | 07/10/2026 | Project documentation and test results |

### Week 12 Achievements:

* Completed end-to-end integration verification:
  * Confirmed that requests pass through API Gateway, VPC Link, the Internal ALB, and the correct ECS Service.
  * Verified that the services connect successfully to RDS PostgreSQL and ElastiCache Redis.
  * Used CloudWatch Logs and traceId values to correlate requests across microservices and diagnose failures.

* Confirmed that data-protection mechanisms work correctly in the test scenarios:
  * Multiple requests with the same `idempotencyKey` do not create additional payments or debit the account more than once.
  * Account Service returns an idempotent result for a matching `transactionId` and rejects a reused ID when transaction data differs.
  * The state machine and conditional claim prevent multiple workers from processing the same payment.

* Evaluated system behavior under load:
  * Observed throughput, latency, error rate, and CPU/memory utilization across increasing load stages.
  * Verified that the rate limiter returns HTTP 429 when one user exceeds the configured threshold, protecting downstream services.
  * Observed Retry, Circuit Breaker, Redis locking, and ECS Service Auto Scaling behavior as traffic or connection failures increased.

* Completed and summarized the project:
  * Tuned timeout, retry, rate-limit, and container-resource parameters based on test observations.
  * Finalized the AWS architecture diagram, deployment documentation, bilingual worklog, and project report content.
  * Reviewed, stopped, or deleted unnecessary AWS resources to limit costs after testing.
