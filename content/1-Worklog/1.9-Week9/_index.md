---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:

* Complete the Account Service and continue developing the Payment Service and Transaction Service.
* Implement communication between the Payment Service and Account Service using OpenFeign.
* Apply idempotency, payment states, Circuit Breaker, and Retry to the transaction-processing flow.
* Run integration tests across services and evaluate data consistency.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Complete the Account Service<br>&emsp; + Review idempotent debit and credit handling<br>&emsp; + Standardize Transaction History, currency handling, and business error codes<br>&emsp; + Verify cache invalidation after balance updates | 15/06/2026 | 15/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Tuesday | - Develop the Payment Service<br>&emsp; + Design Payment Entity, DTO, Repository, Service, Mapper, and Controller layers<br>&emsp; + Build APIs for payment creation and payment-history lookup<br>&emsp; + Use idempotencyKey to prevent duplicate payment creation | 16/06/2026 | 16/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Wednesday | - Integrate the Payment Service with the Account Service<br>&emsp; + Configure the OpenFeign Client<br>&emsp; + Build debit requests using paymentId/transactionId<br>&emsp; + Configure connect timeout, read timeout, and inter-service error handling<br>&emsp; + Integrate Resilience4j Circuit Breaker and Retry | 17/06/2026 | 17/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thursday | - Develop the Transaction Service<br>&emsp; + Design Transaction Entity, status, and transaction type<br>&emsp; + Build APIs for transaction creation and lookup by ID or account<br>&emsp; + Apply idempotency by transactionId and validate payload conflicts | 18/06/2026 | 18/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Friday | - Run microservice integration tests<br>&emsp; + Test account creation, payment creation, balance debit, and transaction storage<br>&emsp; + Test duplicate requests, insufficient balance, currency mismatch, and timeout cases<br>&emsp; + Track PENDING, PROCESSING, SUCCESS, and FAILED states<br>&emsp; + Record and fix data-consistency issues | 19/06/2026 | 19/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Week 9 Achievements:

* Completed the Account Service and its balance-operation idempotency mechanism.
* Completed the main components of the Payment Service and Transaction Service.
* Established Payment Service to Account Service communication through OpenFeign.
* Integrated Circuit Breaker, Retry, timeout, and inter-service error handling.
* Tested the main payment flows and business-error cases with Postman.
