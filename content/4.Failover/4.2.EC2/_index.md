---
title : "EC2"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 4.2 </b> "
---

1. Go to [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me) in the **N. California (us-west-1)** region.
2. Select AMI name **pilotAMI**.
3. Then, click on **Launch instance from AMI**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.1ec2.png?width=90pc)

4. Enter ```pilot-secondary``` as **Name**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.2ec2.png?width=90pc)

5. Scroll down and at **Key pair (login)** feature, select **Proceed without a key pair (Not recommended)** as **Key pair name - required**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.3ec2.png?width=90pc)

6. At **Network settings** feature, click on **Edit**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.4ec2.png?width=90pc)

7. Select the **VPC** that is NOT the default VPC as the **VPC**.
8. At **Firewall (security groups)**, select **Select existing security group**.
9. Then select SG name **network-stack-WebServerSecurityGroup-XXXXXXXXXXXXX**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.5ec2.png?width=90pc)

10. Scroll down and expand **Advanced details**.
11. At **IAM instance profile**, select **pilot-secondary-S3InstanceProfile-xxx**.
![Failover EC2](/images/4.failover/4.2.ec2/4.2.7ec2.png?width=90pc)
12. At **User data - optional** feature, input the code below:
```
#!/bin/bash     
sudo su ec2-user                        
export AWS_DEFAULT_REGION=$(curl -s http://169.254.169.254/latest/dynamic/instance-identity/document | python -c "import json,sys; print json.loads(sys.stdin.read())['region']")
export DATABASE=$(aws rds describe-db-clusters --region $AWS_DEFAULT_REGION --db-cluster-identifier pilot-secondary --query 'DBClusters[*].[Endpoint]' --output text)
sudo bash -c "cat >/home/ec2-user/unishopcfg.sh" <<EOF
#!/bin/bash
export DB_ENDPOINT=$DATABASE
EOF
sudo systemctl restart unishop
```

13. Click on **Launch instance**. 

![Failover EC2](/images/4.failover/4.2.ec2/4.2.6ec2.png?width=90pc)