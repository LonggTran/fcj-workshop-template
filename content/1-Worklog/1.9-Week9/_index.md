---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
{{% notice warning %}} 
⚠️ **Note:** The following information is for reference purposes only. Please **do not copy verbatim** for your own report, including this warning.
{{% /notice %}}

### Week 9 Objectives:

* Implement Account Service to manage accounts, balances, and safe debit/credit operations under concurrent requests.
* Build Account Service idempotency using `transactionId` and a transaction-history table.
* Integrate Redis Cache to reduce repeated PostgreSQL queries for account and balance data.
* Complete Transaction Service for storing and retrieving account transactions.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Build the Account Service domain model<br>&emsp; + Create the Account entity, account status, and account-number generator<br>&emsp; + Implement APIs for account creation, account details, and balance lookup | 06/15/2026 | 06/15/2026 | Account Service source code |
| 3 | - Implement safe debit and credit operations<br>&emsp; + Use direct PostgreSQL balance updates to preserve atomicity<br>&emsp; + Validate account status, currency, and available balance before debit | 06/16/2026 | 06/16/2026 | <https://docs.spring.io/spring-data/jpa/reference/> |
| 4 | - Build Account Service idempotency<br>&emsp; + Use `transactionId` as the unique key in `transaction_histories`<br>&emsp; + Apply `INSERT ... ON CONFLICT DO NOTHING` to detect duplicate requests<br>&emsp; + Return success for matching duplicates and a conflict when the payload differs from the original request | 06/17/2026 | 06/17/2026 | PostgreSQL and project source code |
| 5 | - Integrate Redis Cache for account data<br>&emsp; + Cache account details and balances with `@Cacheable`<br>&emsp; + Evict related entries after debit/credit with `@CacheEvict`<br>&emsp; + Standardize cache-data serialization | 06/18/2026 | 06/18/2026 | <https://docs.spring.io/spring-data/redis/reference/> |
| 6 | - Complete Transaction Service<br>&emsp; + Implement APIs to create a transaction, retrieve it by ID, and list transactions by account<br>&emsp; + Validate idempotency when the client supplies a `transactionId`<br>&emsp; + Standardize amount, currency, type validation, and business error handling | 06/19/2026 | 06/19/2026 | Transaction Service source code |

### Week 9 Achievements:

* Completed the core Account Service features:
  * Created accounts with a unique account number, currency, and initial balance.
  * Exposed APIs for account details, balance lookup, debit, and credit.
  * Normalized monetary amounts to two decimal places and validated account status, currency, and balance before updates.

* Built safe balance updates for concurrent execution:
  * Debit is performed with a conditional SQL statement containing `balance >= amount`, avoiding a separated read-then-write race condition.
  * Credit is executed as an atomic database update.
  * Clearly distinguished insufficient balance, inactive account, currency mismatch, and operation-failure errors.

* Completed debit/credit idempotency:
  * Each `transactionId` is recorded only once in `transaction_histories`.
  * A repeated request with the same account, amount, currency, and type returns the current result without changing the balance again.
  * Reusing a `transactionId` with different request data is rejected as an idempotency conflict.

* Integrated Redis Cache and completed Transaction Service:
  * Reduced repeated database queries for account and balance data, with cache invalidation after balance changes.
  * Stored transactions independently and supported lookup by transaction ID and account ID.
  * Applied duplicate-request validation and consistent API error responses.
