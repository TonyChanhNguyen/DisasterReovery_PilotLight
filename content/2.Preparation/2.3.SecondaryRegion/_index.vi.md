---
title : "Vùng thứ cấp"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 2.3 </b> "
---
### Triển khai cấu hình mạng sử dụng Amazon CloudFormation Templates
1. Tạo cơ sở hạ tầng mạng tại vùng thứ cấp **N. California (us-west-1)** bằng việc khởi chạy [CloudFormation Template](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/create/template?stackName=network-stack&templateURL=https://ws-assets-prod-iad-r-pdx-f3b3f9f1a7d6a3d0.s3.us-west-2.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/NetworkStack.yaml) này.
2. Tại trang CloudFormation, nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.1secondaryregion.png?width=90pc)


3. Tại trang **Specify stack details**, nhập tên ```network-stack```.
4. Sau đó, nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.2secondaryregion.png?width=90pc)

5. Tại trang **Configure stack options**. Cuộn xuống và nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.3secondaryregion.png?width=90pc)

6. Tại trang **Review network-stack**. Cuộn xuống và nhấn **Submit**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.4secondaryregion.png?width=90pc)

7. Stack hạ tầng mạng của bạn đang được tạo.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.5secondaryregion.png?width=90pc)

8. Sau 1 phút, stack của bán sẽ được tạo thành công.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.6secondaryregion.png?width=90pc)

### Triển khai ứng dụng
1 Tạo ứng dụng của bạn trong vùng thứ cấp **N. California (us-west-1)** bằng việc khởi chạy [CloudFormation Template](https://us-west-1.console.aws.amazon.com/cloudformation/home?region=us-west-1#/stacks/create/template?stackName=pilot-secondary&templateURL=https://ws-assets-prod-iad-r-pdx-f3b3f9f1a7d6a3d0.s3.us-west-2.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/PilotLight.yaml) này.
2. Tại trang CloudFormation, nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.7secondaryregion.png?width=90pc)

3. Tại trang **Specify stack details**:
    + Cấu hình **IsPrimary** là **No**
    + Giữ **LatestAmiId** mặc định
    + Giữ **NetworkStackName** mặc định (network-stack)

4. Sau đó, nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.8secondaryregion.png?width=90pc)

5. Tại trang **Configure stack options**. Cuộn xuống và nhấn **Next**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.9secondaryregion.png?width=90pc)

6. Tại trang **Review pilot-primary**, cuộn xuống cuối trang.
7. Tích chọn tại ô **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
8. Sau đó, nhấn **Submit**.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.10secondaryregion.png?width=90pc)

9. Stack ứng dụng của bạn đang được tạo. Sẽ mất khoảng 15 phút để hoàn tất.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.11secondaryregion.png?width=90pc)

10. Sau chừng 15 phút, stack của bạn được tạo thành công.
![Secondary Region](./images/2.preparation/2.3.secondaryregion/2.3.12secondaryregion.png?width=90pc)
