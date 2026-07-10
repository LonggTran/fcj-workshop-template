---
title : "Create CloudWatch Alarm on ALB RequestCount"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.8.2. </b> "
---

We will set up the CloudWatch Alarm to monitor the total incoming requests on the ALB.

---

### Steps:

1. Search for and select the **CloudWatch** service on the AWS Console.
2. In the left menu, select **Alarms** -> Select **All alarms** -> Click **Create alarm** in the top right.
3. Click **Select metric**:
   - Select **ApplicationELB** -> Select **Per AppELB Metrics**.
   - Find and check the **`RequestCount`** metric for your Load Balancer **`pg-alb`**.

![Select the ALB RequestCount metric](/images/h53.png)

   - Click **Select metric** at the bottom.
4. **Configure Metric & Alarm Conditions (IMPORTANT):**
   - **Statistic**: Select **`Sum`** (Do not choose *Average*).
   - **Period**: Select **`1 minute`** (Allows the system to update and alert quickly).
   - **Threshold type**: **Static**.
   - **Whenever RequestCount is...**: **Greater than threshold** | **than...**: Enter **`100`** (Triggers when the count exceeds 100 requests in a single minute).

![Configure the alarm threshold](/images/h55.png)

   - Click **Next**.
5. **Configure Actions:**
   - **Alarm state trigger**: Select **In alarm**.
   - **Send a notification to the following SNS topic**: Select **Select an existing SNS topic** -> Choose your **`pg-alerts`** topic.
   - *Ensure that Actions enabled is checked/active*. Click **Next**.

![Configure the SNS notification action](/images/h56.png)

6. **Name the Alarm:** Enter `pg-alb-high-request-alarm`. Click **Next** -> Click **Create alarm**.

![CloudWatch alarm created successfully](/images/h57.png)
