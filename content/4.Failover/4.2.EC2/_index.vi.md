---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 4.2 </b> "
---

1. Đi đến [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me) trong vùng **N. California (us-west-1)**.
2. Chọn AMI tên **pilotAMI**.
3. Sau đó, nhấn **Launch instance from AMI**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.1ec2.png?width=90pc)

4. Nhập ```pilot-secondary``` tại **Name**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.2ec2.png?width=90pc)

5. Cuộn xuống tại mục **Key pair (login)**, chọn **Proceed without a key pair (Not recommended)** tại **Key pair name - required**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.3ec2.png?width=90pc)

6. Tại trang **Network settings**, nhấn **Edit**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.4ec2.png?width=90pc)

7. Chọn **VPC** mà không phải là VPC mặc định tại mục **VPC**.
8. Tại **Firewall (security groups)**, chọn **Select existing security group**.
9. Sau đó chọn SG tên **network-stack-WebServerSecurityGroup-XXXXXXXXXXXXX**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.5ec2.png?width=90pc)

10. Cuộn xuống và mở rộng **Advanced details**.
11. Tại **IAM instance profile**, chọn **pilot-secondary-S3InstanceProfile-xxx**.
![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.7ec2.png?width=90pc)
12. Tại trang **User data - optional**, nhập đoạn code sau:
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

13. Nhấn **Launch instance**. 

![Failover EC2](../../../images/4.failover/4.2.ec2/4.2.6ec2.png?width=90pc)
