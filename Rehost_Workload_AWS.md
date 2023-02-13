# Lift and shift: Rehost your workload on AWS

Workloads running on physical/virtual machines in a datacenter usually require multiple teams to manage services and the workloads with is complex especially when you would like to scale up or scale down.

Below is the rehostig archictural diagram

1. Login to AWS Account

![aws console](./images/1.png)

2. Create key Pairs
3. Create Security groups
4. Lunch Instances with user data (BASH Script)
5. Update IP to name mapping in route 53
6. Build Apllication from source code
7. Upload to S3 bucket
8. Download artifact to Tomcat EC2 Instance
9. Setup ELB with HTTPS (Cert from Amazon Certificate Manager)
10. Map ELB Endpoint to website name in host Zone.
11. Verify 