---
title : "Configure Listener Routing Rules"
date : 2024-01-01 
weight : 3
chapter : false
pre : " <b> 5.6.3. </b> "
---

To route API traffic from client browsers to the backend gateway instead of Nginx, we configure a custom listener rule.

---

### Steps:

1. Open the Load Balancers list -> Select `pg-alb`.
2. Select the **Listeners and rules** tab in the middle pane.
3. Click the blue link **`HTTP:80`**.
4. Select the **Rules** tab -> Click **Add rules**.
5. Configure the routing rule parameters:
   - **Rule name**: `api-rule`.
   - **Conditions**: Click **Add condition** -> Select **Path** -> Enter **`/api/*`** -> Click **Confirm**.

![Configure the listener rule condition](/images/h34.png)

   - **Actions**: Click **Forward to target groups** -> Select **`tg-backend`** -> Click **Confirm**.
   - **Priority**: Enter **`10`**.
6. Click **Save** to apply.

![Configure the listener rule action and priority](/images/h35.png)
