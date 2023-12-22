---
title : "Primary region"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Deploy Network Configuration using Amazon CloudFormation Templates
1. Create Network Infrastructure in primary region **N. Virginia (us-east-1)** by launching this [CloudFormation Template](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=network-stack&templateURL=https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/NetworkStack.yaml).
2. At CloudFormation interface, click on **Next**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.1primaryregion.png?width=90pc)

3. At **Specify stack details** interface, input stack name ```network-stack```.
4. Then, click on **Next**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.2primaryregion.png?width=90pc)

5. At **Configure stack options** interface. Scroll down and click on **Next**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.3primaryregion.png?width=90pc)


6. At **Review network-stack** interface. Scroll down and click on **Submit**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.4primaryregion.png?width=90pc)

7. Your network stack is creating.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.5primaryregion.png?width=90pc)

8. After a minute, your stack will be created successfully.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.6primaryregion.png?width=90pc)


### Deploy Application
1. Create application in primary region **N. Virginia (us-east-1)** by launching [CloudFormation Template](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=pilot-primary&templateURL=https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/PilotLight.yaml).
2. At CloudFormation interface, click on **Next**.

![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.7primaryregion.png?width=90pc)

3. At **Specify stack details** interface:
    + Keep **IsPrimary** as default (Yes)
    + Keep *LatestAmiId* as default
    + Keep **NetworkStackName** as default (network-stack)

4. Then, click on **Next**.

![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.8primaryregion.png?width=90pc)

5. At **Configure stack options** interface. Scroll down and click on **Next**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.9primaryregion.png?width=90pc)

6. At **Review pilot-primary** interface, scroll down to the end of page.
7. Check at box **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
8. Then, click on **Submit**.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.10primaryregion.png?width=90pc)

9. Your application stack is creating. It will take you about 15 minutes to finish.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.11primaryregion.png?width=90pc)

10. After about 15 minutes, your stack had been created successfully.
![Primary Region](./images/2.preparation/2.2.primaryregion/2.2.12primaryregion.png?width=90pc)