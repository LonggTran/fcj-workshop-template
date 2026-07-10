---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 10 Objectives:

* Implement Payment Service with idempotency and a state machine that prevents duplicate account debits.
* Handle concurrent requests through a Redis distributed lock and conditional PostgreSQL status updates.
* Integrate Payment Service with Account Service using OpenFeign, Retry, and Circuit Breaker.
* Complete API Gateway and user-based rate limiting with a Redis Lua script.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Build Payment Service and the payment data model<br>&emsp; + Create the Payment entity, create/query APIs, and a unique constraint for `idempotencyKey`<br>&emsp; + Standardize amount, currency, userId, and accountId validation | 06/22/2026 | 06/22/2026 | Payment Service source code |
| 3 | - Implement the payment state machine<br>&emsp; + Use the `PENDING → PROCESSING → SUCCESS/FAILED` state flow<br>&emsp; + Claim processing ownership through a conditional update while the status is PENDING<br>&emsp; + Allow only the successful claimant to call Account Service for debit | 06/23/2026 | 06/23/2026 | Spring Data JPA and PostgreSQL |
| 4 | - Build Redis distributed locking and idempotency handling<br>&emsp; + Lock by `idempotencyKey` with a TTL to prevent concurrent processing<br>&emsp; + Release the lock safely with a Lua script that verifies the lock value<br>&emsp; + Validate duplicate-request payloads before returning an existing payment | 06/24/2026 | 06/24/2026 | <https://redis.io/docs/latest/> |
| 5 | - Integrate Payment Service with Account Service<br>&emsp; + Call the debit API through OpenFeign and use the payment ID as `transactionId`<br>&emsp; + Configure timeout, Retry, and Circuit Breaker with Resilience4j<br>&emsp; + Distinguish business errors from temporary failures to avoid incorrectly marking a payment FAILED when Account Service has not responded | 06/25/2026 | 06/25/2026 | <https://resilience4j.readme.io/> |
| 6 | - Complete API Gateway and traffic limiting<br>&emsp; + Route requests to Account, Payment, and Transaction Service<br>&emsp; + Build a Token Bucket rate limiter with a Redis Lua script<br>&emsp; + Limit by `X-User-Id` or the `userId` query parameter, with IP fallback when user information is unavailable | 06/26/2026 | 06/26/2026 | API Gateway source code |

### Week 10 Achievements:

* Completed Payment Service with multi-layer idempotency:
  * `idempotencyKey` is unique in PostgreSQL, preventing multiple payment records for the same logical request.
  * A Redis distributed lock reduces concurrent processing before database operations.
  * A duplicate request with matching data receives the current payment state, while reusing the key with a different payload is rejected.

* Built a safe state machine and processing-claim mechanism:
  * A payment moves from PENDING to PROCESSING only through a conditional update.
  * Only the request that successfully claims the payment calls Account Service, preventing multiple debits for the same payment.
  * Completion is limited to PROCESSING-to-SUCCESS or PROCESSING-to-FAILED transitions, protecting terminal states from invalid overwrites.

* Integrated resilient inter-service communication:
  * Payment Service calls Account Service through OpenFeign with explicit connect and read timeouts.
  * Retry is limited to temporary connectivity failures, while Circuit Breaker stops repeated calls when failures become excessive.
  * Temporary failures keep the payment in PROCESSING instead of marking it FAILED when the account might already have been debited.

* Completed API Gateway and rate limiting:
  * All APIs are exposed through a single gateway.
  * The Lua script atomically checks and updates the Redis Token Bucket.
  * Traffic limits are separated by userId and return HTTP 429 with limit, remaining-token, and retry information.
