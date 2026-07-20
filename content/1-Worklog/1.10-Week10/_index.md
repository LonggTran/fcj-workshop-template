---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Week 10 Objectives:

* Complete Payment Service with idempotency and the `PENDING → PROCESSING → SUCCESS/FAILED` state machine.
* Build processing ownership with a `processingToken`, lease, and conditional PostgreSQL updates.
* Integrate OpenFeign, Retry, Circuit Breaker, and a recovery worker for interrupted payments.
* Complete API Gateway with a Redis Token Bucket rate limiter by `userId` and integrate all microservices.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Complete Payment Service idempotency and state handling<br>&emsp; + Validate request data when an `idempotencyKey` already exists<br>&emsp; + Create payments in PENDING status and allow only valid state transitions<br>&emsp; + Return the existing payment for matching duplicates and reject key reuse with different data | 22/06/2026 | 22/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Tuesday | - Build payment-processing ownership<br>&emsp; + Claim a payment through `UPDATE ... WHERE status = 'PENDING'`<br>&emsp; + Assign a `processingToken`, processing start time, and `leaseExpiresAt` to the owner<br>&emsp; + Allow only the process holding the matching token to finalize the payment | 23/06/2026 | 23/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Wednesday | - Build payment recovery and reconciliation<br>&emsp; + Create a scheduled worker to find PROCESSING payments with expired leases or stale PENDING payments<br>&emsp; + Schedule retries through `nextRetryAt` and exponential backoff for temporary failures<br>&emsp; + Keep a payment in PROCESSING when the debit result is still uncertain | 24/06/2026 | 24/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thursday | - Integrate Payment Service with Account Service<br>&emsp; + Call the debit API through OpenFeign and use the payment ID as `transactionId`<br>&emsp; + Configure connect timeout, read timeout, Retry, and Circuit Breaker with Resilience4j<br>&emsp; + Distinguish business failures, rate limiting, and temporary connectivity failures | 25/06/2026 | 25/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Friday | - Complete API Gateway and system integration<br>&emsp; + Route `/api/accounts/**`, `/api/payments/**`, and `/api/transactions/**` to the correct services<br>&emsp; + Build a Redis Lua Token Bucket that performs atomic limit checks and updates<br>&emsp; + Limit by `X-User-Id` or `userId`, fall back to IP, and return HTTP 429 when the limit is exceeded<br>&emsp; + Verify account creation, payment, debit, and transaction lookup through the gateway | 26/06/2026 | 26/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Week 10 Achievements:

* Completed Payment Service with a unique `idempotencyKey` and a controlled payment-state machine.
* Built PostgreSQL-based processing ownership with a `processingToken` and lease, preventing concurrent requests from debiting the same payment more than once.
* Added a recovery worker, retry scheduling, and exponential backoff for interrupted or temporarily failed payments.
* Integrated OpenFeign, Resilience4j Retry, and Circuit Breaker for Payment Service calls to Account Service.
* Completed API Gateway with a Redis Lua Token Bucket rate limiter by `userId`; JWT is not used in the current project scope.
* Integrated the services locally and prepared the configuration for the AWS deployment phase.
