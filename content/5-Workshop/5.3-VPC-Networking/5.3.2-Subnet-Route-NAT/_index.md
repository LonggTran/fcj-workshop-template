---
title : "Configure NAT Gateway Routing"
date : 2024-01-01 
weight : 2
chapter : false
pre : " <b> 5.3.2. </b> "
---

To ensure that Fargate container tasks running in Private Subnets can make outbound connections to retrieve Docker images and send logs to CloudWatch, verify the Private Route Table.

---

### Step-by-step Private Route Table Configuration:

1. In the **VPC** service, click **Route tables** in the left menu.
2. Select the Private Route Table (the one associated with your 2 private subnets).
3. Select the **Routes** tab at the bottom -> Click **Edit routes**.
4. Check if the following route is present:
   - **Destination**: `0.0.0.0/0`
   - **Target**: **NAT Gateway** -> Choose your NAT Gateway (`pg-nat...`).
5. If it is missing, click **Add route**:
   - Enter `0.0.0.0/0` in the destination box.
   - Choose `NAT Gateway` as target.
   - Select your NAT Gateway ID from the dropdown.
6. Click **Save changes**.

![Confirm the private subnet route through the NAT gateway](/images/h15.png)
