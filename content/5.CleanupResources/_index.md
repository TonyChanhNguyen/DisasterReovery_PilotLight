---
title : "Cleanup resources"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

### S3 Cleanup
1. Go to [S3](https://s3.console.aws.amazon.com/s3/home).
2. Select the **pilot-primary-uibucket-xxxx**.
3. Click **Empty**.
![Cleanup Resources](./images/5.cleanup/5.1cleanup.png?width=90pc)

4. Input ```permanently delete```.
5. Then, click on **Empty**.
![Cleanup Resources](./images/5.cleanup/5.2cleanup.png?width=90pc)

6. Repeat those step for bucket name **pilot-secondary-uibucket-xxxx** also.


### Database Cleanup
#### Primary region
1. Go to [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:) in **N. Virginia (us-east-1)** region.
2. Select **unishop** database under **pilot-primary** cluster.
3. Click on **Action**.
4. Then click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.5cleanup.png?width=90pc)
5. Enter ```delete me```.
6. Click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.6cleanup.png?width=90pc)

7. After **unishop** database was deleted, select **pilot-primary** cluster.
8. Click on **Actions**.
9. Click on **Remove from global database**.
![Cleanup Resources](./images/5.cleanup/5.9cleanup.png?width=90pc)

10. Click **Remove and promote**.
![Cleanup Resources](./images/5.cleanup/5.10cleanup.png?width=90pc)

11. After remove from global database, select **pilot-primary** cluster.
12. Click on **Actions**.
13. Click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.11cleanup.png?width=90pc)


14. Uncheck **Create final snapshot** box.
15. Check **I acknowledge that upon instance...** box.
16. Input ```delete me```.
17. Then, click on **Delete DB sluster**.
![Cleanup Resources](./images/5.cleanup/5.8cleanup.png?width=90pc)

#### Secondary region
1. Go to [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-west-1#databases:) in **N. California (us-west-1)** region.
2. Repeat all above steps to delete **unishop-pilot** database first, then delete **pilot-secondary** cluster.

After databases and clusters were deleted, now we will delete **Global database**.

3. Select **pilot-global**.
4. Click on **Actions**.
5. Click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.12cleanup.png?width=90pc)

6. Input ```delete me```.
7. Click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.13cleanup.png?width=90pc)


### EC2 cleanup
1. Go to [EC2](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Instances:instanceState=running) in the **N. California (us-west-1)** region.
2. Select instance name **pilot-secondary**.
3. Click on **Instance state**.
4. Click on **Terminate instance**.
![Cleanup Resources](./images/5.cleanup/5.14cleanup.png?width=90pc)

5. Go to [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me).
6. Select AMI name **pilotAMI**.
7. Click on **Actions**.
8. Click on **Deregister AMI**.
![Cleanup Resources](./images/5.cleanup/5.15cleanup.png?width=90pc)

9. Repeat these steps to delete [AMIs](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Images:visibility=owned-by-me) at the **N. Virginia (us-east-1)** region


### CloudFormation Secondary Region Cleanup
1. Go to [CloudFormation stacks](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/outputs?stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fpilot-secondary%2F03e01970-9f12-11ee-bb5d-0282085eba19&filteringText=&filteringStatus=active&viewNested=true) in the **N. California (us-west-1)** region.
2. Select stack name **pilot-secondary**.
3. Then click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.16cleanup.png?width=90pc)

4. After stack **pilot-secondary** was deleted, select stack name **network-stack**.
5. Then click on **Delete**.
![Cleanup Resources](./images/5.cleanup/5.17cleanup.png?width=90pc)
### CloudFormation Primary Region Cleanup
1. Go to [CloudFormation stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true&stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fnetwork-stack%2F97f9d5d0-9f10-11ee-a02a-06401036bc1b) in the **N. Virginia (us-east-1)** region.

2. Repeat these steps to delete stack name **pilot-primary** first, then delete stack name **network-stack**.

#### Congratulations, you had finished this workshop! 