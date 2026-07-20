---
title: "Week 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---
### Week 10 Objectives:

* Complete the API Gateway and integrate all microservices.
* Build Redis-based rate limiting to control traffic by userId.
* Finalize payment-processing ownership using a processing token and lease.
* Add a recovery worker, load-test profiles, and Docker packaging for all services.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| Monday | - Build the API Gateway with Spring Cloud Gateway<br>&emsp; + Configure routing to Account Service, Payment Service, and Transaction Service<br>&emsp; + Standardize health checks and dev/loadtest profiles<br>&emsp; + Verify the unified request-entry flow | 22/06/2026 | 22/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Tuesday | - Build Redis-based rate limiting<br>&emsp; + Use a Token Bucket and Lua Script for atomic execution<br>&emsp; + Limit requests by userId from a header or query parameter<br>&emsp; + Use the client IP as a fallback key<br>&emsp; + Return HTTP 429, Retry-After, and remaining-quota information | 23/06/2026 | 23/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Wednesday | - Complete concurrent payment processing<br>&emsp; + Move payments from PENDING to PROCESSING through an atomic claim<br>&emsp; + Attach processingToken and leaseExpiresAt to define processing ownership<br>&emsp; + Allow only the token owner to call the Account Service and update the result<br>&emsp; + Prevent duplicate debits from concurrent requests | 24/06/2026 | 24/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Thursday | - Build payment recovery processing<br>&emsp; + Create a Payment Recovery Worker to scan stalled PENDING or PROCESSING records<br>&emsp; + Configure time-based retries and processing-attempt limits<br>&emsp; + Add database indexes for recovery queries<br>&emsp; + Test timeout and ownership-loss cases | 25/06/2026 | 25/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |
| Friday | - Complete the project before AWS deployment<br>&emsp; + Configure application-loadtest profiles for all services<br>&emsp; + Optimize logging, timeout, and connection-pool settings<br>&emsp; + Create Dockerfiles for API Gateway, Account, Payment, and Transaction Services<br>&emsp; + Build the complete project and run local Docker integration tests | 26/06/2026 | 26/06/2026 | <https://github.com/LonggTran/high-concurrency-payment-gateway> |

### Week 10 Achievements:

* Completed the API Gateway and service-routing configuration.
* Implemented userId-based Redis rate limiting with a Lua Script and HTTP 429 responses.
* Finalized the payment state machine with atomic claim, processing token, and processing lease.
* Added a Payment Recovery Worker for stalled transactions and retry processing.
* Packaged the services with Docker and completed local integration testing.
