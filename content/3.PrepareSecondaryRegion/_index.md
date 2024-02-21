---
title : "Prepare secondary region"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

In this step, we will perform create the EC2 AMI at Primary region, then copy it in to Secondary region to launch EC2 instance on it.

### Create the EC2 Amazon Machine Image (AMI)
1. Go to [EC2](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Instances:v=3;$case=tags:true%5C,client:false;$regex=tags:false%5C,client:false) at Primary region **N. Virginia (us-east-1)**.

2. Select the instance name **pilot-primary**.
3. Click on **Action**.
4. Click on **Images and Templates** under **Action**.
5. Then, click on **Create image**.
![Prepare secondary region](./../images/3.preparesecondaryregion/3.1preparesecondaryregion.png?width=90pc)

6. Enter ```pilotAMI``` as the **Image name**.
7. Then, click on **Create image**.
![Prepare secondary region](./../images/3.preparesecondaryregion/3.2preparesecondaryregion.png?width=90pc)

### Copy the EC2 Amazon Machine Image (AMI)
1. Click [AMIs](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Images:visibility=owned-by-me) to navigate to the dashboard.
2. Select image name **pilotAMI**.
3. Click on **Action**.
4. Click on **Copy AMI** under **Action**.
![Prepare secondary region](./../images/3.preparesecondaryregion/3.3preparesecondaryregion.png?width=90pc)

5. At **Copy AMI** interface, select Secondary region **US West (N. California)** as **Destination Region**.
6. Then, click on **Copy AMI**.
![Prepare secondary region](./../images/3.preparesecondaryregion/3.4preparesecondaryregion.png?width=90pc)

7. Go to [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me) at Secondary region **N. California (us-west-1)**, you will see there is a AMI with status is **Pending**.
![Prepare secondary region](./../images/3.preparesecondaryregion/3.5preparesecondaryregion.png?width=90pc)

8. It will take you about 5 minutes for the AMI was copied successfully.
![Prepare secondary region](../images/3.preparesecondaryregion/3.6preparesecondaryregion.png?width=90pc)


