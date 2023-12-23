---
title : "Verify website"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Primary Region
1. Click [CloudFormation Stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/events?stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fnetwork-stack%2F97f9d5d0-9f10-11ee-a02a-06401036bc1b&filteringText=&filteringStatus=active&viewNested=true) to navigate to the dashboard in **N. Virginia (us-east-1)** region.
2. Choose the **pilot-primary** stack.
3. Click the **Output** link.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.1verifywebsite.png?width=90pc)

4. Click on the **WebsiteURL** output link and open in a new browser tab or window.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.2verifywebsite.png?width=90pc)

5. At web page, click on **Sign up** to register account.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.3verifywebsite.png?width=89pc)

6. Fill needed information to sign up account.
7. Then, click on **Signup** to finish this step.

{{%notice warning%}}
Keep remember information which you provided for this step.
{{%/notice%}}
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.4verifywebsite.png?width=90pc)

8. Click on **Log in**.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.5verifywebsite.png?width=89pc)
9. Fill information which you provided.
10. Then, click on **Login**.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.6verifywebsite.png?width=90pc)

11. After log in successfully, click to **Unicorn** you want. Then click on **Add to cart** to add it into your cart.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.7verifywebsite.png?width=90pc)

12. After you add **Unicorn** item to cart successfully, check **Cart** icon to see the quantity was increased.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.8verifywebsite.png?width=90pc)

13. Repeat step 12 to add more items to your cart.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.9verifywebsite.png?width=90pc)

14. After finish those step. Save the quantity of your cart and its region. We will verify them again after performing replicate website into secondary region.

{{%notice note%}}
In my situation, the quantity of cart is **5** and region is **us-east-1** (Primary region).
{{%/notice%}}
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.10verifywebsite.png?width=90pc)


### Secondary Region
Your secondary region should be unavailable. In a pilot light disaster recovery strategy there are no compute instances.

1. Go to [CloudFormation Stacks]() in region **N. California (us-west-1)**.
2. Choose the **pilot-secondary** stack.
3. Click the **Outputs** link.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.11verifywebsite.png?width=90pc)

4. Click on the WebsiteURL output link and open in a new browser tab or window.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.12verifywebsite.png?width=90pc)

5. You should see a 404 error page.
![Verify website](/images/2.preparation/2.4.verifywebsite/2.4.13verifywebsite.png?width=90pc)