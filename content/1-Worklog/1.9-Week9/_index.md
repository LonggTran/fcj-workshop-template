---
title: "Week 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---
### Week 9 Objectives:

* Complete Account Service with safe balance updates under concurrent requests.
* Build debit/credit idempotency using `transactionId` and a transaction-history table.
* Integrate Redis Cache for account and balance data.
* Build Transaction Service and initialize the core Payment Service features.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Complete Account Service debit and credit operations<br>&emsp; + Use direct PostgreSQL balance-update statements to preserve atomicity<br>&emsp; + Validate account status, currency, and available balance<br>&emsp; + Normalize monetary amounts to two decimal places | 15/06/2026 | 15/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Tuesday | - Build Account Service idempotency<br>&emsp; + Use `transactionId` as the unique key in `transaction_histories`<br>&emsp; + Insert history with `ON CONFLICT DO NOTHING` to detect duplicate requests<br>&emsp; + Return the current result for matching duplicates and a conflict when the payload differs from the original request | 16/06/2026 | 16/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Wednesday | - Integrate Redis Cache for account data<br>&emsp; + Cache account details and balances with `@Cacheable`<br>&emsp; + Evict cache entries after debit/credit with `@CacheEvict`<br>&emsp; + Configure serialization and suitable cache retention | 17/06/2026 | 17/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thursday | - Build Transaction Service<br>&emsp; + Create transaction entity, repository, service, controller, and mapper components<br>&emsp; + Implement transaction creation, lookup by ID, and listing by account<br>&emsp; + Validate idempotency when the client provides a `transactionId` | 18/06/2026 | 18/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Friday | - Initialize Payment Service and test service APIs<br>&emsp; + Create the Payment entity, payment statuses, and a unique constraint for `idempotencyKey`<br>&emsp; + Implement payment creation, payment lookup, and user payment-history APIs<br>&emsp; + Test Account, Transaction, and Payment APIs with valid, duplicate, and invalid data | 19/06/2026 | 19/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Week 9 Achievements:

* Completed Account Service with account creation, balance lookup, debit, and credit APIs.
* Applied atomic PostgreSQL balance updates to reduce race conditions when multiple requests access the same account.
* Completed debit/credit idempotency; matching duplicate requests do not change the balance again, while a reused `transactionId` with different data is rejected.
* Integrated Redis Cache and cache invalidation after balance changes.
* Completed Transaction Service and built the Payment Service foundation with a unique `idempotencyKey`.
