---
title : "Pilot Light"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Pilot Light
In this module, you will go through the Pilot Light disaster recovery strategy. Pilot Light disaster recovery strategy has **Recovery Point Objective(RPO) / Recovery Time Objective (RTO)**  within tens of minutes. For the pilot light strategy secondary region, the data is live and core infrastructure is provisioned, but the services are either idle or absent.

Your application is currently deployed in the primary region N. Virginia (us-east-1). N. California (us-west-1) will be your secondary.

Your test application is **Unishop**. It is a Spring Boot Java application deployed on a single Amazon Elastic Compute Cloud (EC2)  instance using a public subnet. Your datastore is an Amazon Aurora MySQL database with a frontend written using bootstrap and hosted in Amazon Simple Storage Service (S3).

This module takes advantage of Amazon Machine Images (AMI) which you will use to launch your Amazon EC2 instance and Amazon Aurora Global Database to replicate your Amazon Aurora MySQL data to your secondary region.

CloudFormation will be used to configure the infrastructure and deploy the application. Provisioning your infrastructure with infrastructure as code (IaC) methodologies is a best practice. CloudFormation is an easy way to speed up cloud provisioning with infrastructure as code.

{{%notice info%}}
Because this workload has only one EC2 instance that is deployed in only one Availability Zone, this architecture does not meet the AWS Well Architected Framework best practices for running highly available production applications but suffices for this workshop.
{{%/notice%}}


![PilotLight](images/ws1.png)