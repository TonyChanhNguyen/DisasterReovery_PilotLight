---
title : "Verify failover"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3 </b> "
---

1. Go to [CloudFormation Stacks](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/?filteringText=&filteringStatus=active&viewNested=true) in the **N. California (us-west-1)** region.
2. Click on stack name **pilot-secondary**.

![Verify Failover](/images/4.failover/4.3.verifyfailover/4.3.1verifyfailover.png?width=90pc)

3. Click on **Outputs** tab.
![Verify Failover](/images/4.failover/4.3.verifyfailover/4.3.2verifyfailover.png?width=90pc)

4. Click on **WebsiteURL** link.
![Verify Failover](/images/4.failover/4.3.verifyfailover/4.3.3verifyfailover.png?width=90pc)

5. Your website should be appeared like this.
![Verify Failover](/images/4.failover/4.3.verifyfailover/4.3.4verifyfailover.png?width=89pc)

6. Now we will login to website to see the result. The needed information to login created at [2.4 Verify website](../../2.preparation/2.4.verifywebsite/).

7. After login successfully, you can see at the cart still saved the quantity of Primary Region. And the region now is **us-west-1**.

![Verify Failover](/images/4.failover/4.3.verifyfailover/4.3.5verifyfailover.png?width=90pc)


#### Congratulations, your website had been done failover to Secondary Region **N. California (us-west-1)** from Primary Region **N. Virginia (us-east-1)** successfully.