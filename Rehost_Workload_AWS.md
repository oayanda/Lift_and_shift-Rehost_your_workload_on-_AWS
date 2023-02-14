# Lift and shift: Rehost your workload on AWS

Workloads running on physical/virtual machines in a datacenter usually require multiple teams to manage services and the workloads with is complex especially when you would like to scale up or scale down.

Below is the rehostig archictural diagram

1. Login into AWS Account

![aws console](./images/1.png)

2. Create key Pairs

To login securely into EC2 instance we need create private/public keys.

Type ***Key pair*** in the search bar, enter a ***name*** and click on ***create key pair***.

![aws console](./images/2.png)

3. Create Security groups
Load Balancer - Allow inboud rules for HTTP and HTTPS for IPv4 and IPv6

Tomcat Instance - 8080 of the application mapped to the LB

Backend Services

- Mysql mapped to the application security group
- 1121 for memcacher mapped to the application SG
- 5672 for RabbitMQ mapped to the application SG
- All traffic mapped to it's self 

4. Lunch Instances with user data (BASH Script)
5. Update IP to name mapping in route 53
6. Build Apllication from source code
7. Upload to S3 bucket
8. Download artifact to Tomcat EC2 Instance
9. Setup ELB with HTTPS (Cert from Amazon Certificate Manager)
10. Map ELB Endpoint to website name in host Zone.
11. Verify 