---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---


### Dọn dẹp S3
1. Đi đến [S3](https://s3.console.aws.amazon.com/s3/home).
2. Chọn **pilot-primary-uibucket-xxxx**.
3. Nhấn **Empty**.
![Cleanup Resources](./images/5.cleanup/5.1cleanup.png?width=90pc)

4. Nhập ```permanently delete```.
5. Sau đó, nhấn **Empty**.
![Cleanup Resources](./images/5.cleanup/5.2cleanup.png?width=90pc)

6. Lặp lại các bước trên với bucket tên **pilot-secondary-uibucket-xxxx**.


### Dọn dẹp CSDL
#### Vùng chính
1. Đi đến [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:) ở vùng **N. Virginia (us-east-1)**.
2. Chọn CSDL **unishop** dưới cụm **pilot-primary**.
3. Nhấn **Action**.
4. Sau đó nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.5cleanup.png?width=90pc)
5. Nhập ```delete me```.
6. Nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.6cleanup.png?width=90pc)

7. Sau khi CSDL **unishop** đã xóa, chọn cụm **pilot-primary**.
8. Nhấn **Actions**.
9. Nhấn **Remove from global database**.
![Cleanup Resources](./images/5.cleanup/5.9cleanup.png?width=90pc)

10. Nhấn **Remove and promote**.
![Cleanup Resources](./images/5.cleanup/5.10cleanup.png?width=90pc)

11. Sau khi đã xóa khỏi cụm toàn cầu, chọn cụm **pilot-primary**.
12. Nhấn **Actions**.
13. Nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.11cleanup.png?width=90pc)


14. Bỏ chọn tại ô **Create final snapshot**.
15. Chọn ô **I acknowledge that upon instance...**.
16. Nhập ```delete me```.
17. Sau đó, nhấn **Delete DB sluster**.
![Cleanup Resources](./images/5.cleanup/5.8cleanup.png?width=90pc)

#### Vùng thứ cấp
1. Đi đến [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-west-1#databases:) trong vùng **N. California (us-west-1)**.
2. Lặp lại các bước trên để xóa CSDL **unishop-pilot** trước, sau đó xóa cụm **pilot-secondary**.

Sau khi CSDL và cụm được xóa, bây giờ xóa **Global database**.

3. Chọn **pilot-global**.
4. Nhấn **Actions**.
5. Nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.12cleanup.png?width=90pc)

6. Nhập ```delete me```.
7. Nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.13cleanup.png?width=90pc)


### Dọn dẹp EC2
1. Đi đến [EC2](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Instances:instanceState=running) trong vùng **N. California (us-west-1)**.
2. Chọn máy chủ tên **pilot-secondary**.
3. Nhấn **Instance state**.
4. Nhấn **Terminate instance**.
![Cleanup Resources](./images/5.cleanup/5.14cleanup.png?width=90pc)

5. Đi đến [AMIs](https://us-west-1.console.aws.amazon.com/ec2/home?region=us-west-1#Images:visibility=owned-by-me).
6. Chọn AMI tên **pilotAMI**.
7. Nhấn **Actions**.
8. Nhấn **Deregister AMI**.
![Cleanup Resources](./images/5.cleanup/5.15cleanup.png?width=90pc)

9. Lặp lại các bước trên để xóa [AMIs](https://us-east-1.console.aws.amazon.com/ec2/home?region=us-east-1#Images:visibility=owned-by-me) tại vùng **N. Virginia (us-east-1)**.


### Dọn dẹp CloudFormation tại vùng thứ cấp
1. Đi đến [CloudFormation stacks](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/outputs?stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fpilot-secondary%2F03e01970-9f12-11ee-bb5d-0282085eba19&filteringText=&filteringStatus=active&viewNested=true) tại vùng **N. California (us-west-1)**.
2. Chọn stack tên **pilot-secondary**.
3. Sau đó nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.16cleanup.png?width=90pc)

4. Sau khi stack **pilot-secondary** được xóa, chọn stack tên **network-stack**.
5. Sau đó nhấn **Delete**.
![Cleanup Resources](./images/5.cleanup/5.17cleanup.png?width=90pc)
### Dọn dẹp CloudFormation tại vùng chính
1. Đi đến [CloudFormation stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true&stackId=arn%3Aaws%3Acloudformation%3Aus-west-1%3A170074558790%3Astack%2Fnetwork-stack%2F97f9d5d0-9f10-11ee-a02a-06401036bc1b) tại vùng **N. Virginia (us-east-1)**.

2. Lặp lại các bước trên để xóa stack **pilot-primary** trước, sau đó xóa stack **network-stack**.

#### Chúc mừng, bạn đã hoàn thành bài thực thành này! 
