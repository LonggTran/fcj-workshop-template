---
title : "Application Load Balancer Configuration"
date : 2024-01-01 
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

In this section, we will deploy a public-facing **Application Load Balancer (ALB)** to distribute user traffic: Routing home page requests to the Frontend Nginx service (port 80) and API calls (`/api/*`) to the backend API Gateway (port 8080).

#### Contents:

1. [Create Target Groups](5.6.1-Create-Target-Groups/)
2. [Create Application Load Balancer](5.6.2-Create-ALB/)
3. [Configure Listener Routing Rules](5.6.3-Configure-Listener-Rules/)
