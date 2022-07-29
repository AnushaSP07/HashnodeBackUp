## Beginners Guide to AWS - Virtual Private Cloud [VPC]

Hey **Reader**!!!!

You're here and you want to know more about the technical concepts.

## **Contents of the blog include:**

- Steps to Create Virtual Private Cloud [VPC] in Amazon Web Service

The following sections demonstrate how to create and configure a VPC for use with AWS Directory Service.


![vpc1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641795409122/eF94mW0p4.png)


### **Create a new VPC**

This tutorial uses one of the VPC creation wizards to create the following:

- The VPC
- One of the subnets
- An Internet gateway

**To create your VPC using the VPC wizard**

- Open the Amazon VPC console at https://console.aws.amazon.com/vpc/

- In the navigation pane, click VPC Dashboard. If you do not already have any VPC resources, locate the Your Virtual Private Cloud area of the dashboard and click Get started creating a VPC. Otherwise, click Start VPC Wizard.

- Select VPC service from AWS console

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794319096/z3gFNhaZ8.png)

- Welcome console will look as below

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794384208/vI_u0a0lo.png)

- Click on Launch VPC Wizard

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794451457/nf1Znv2El.png)

- Select “VPC with Public and Private Subnets” and click “Select”

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794475183/DY1HjMH7K.png)

- Provide VPC name, valid CIDR range for Public and Private subnets. Select availability zones for Public and private subnets [as per standards public and private should be in different availability zones]. Provide elastic IP for NAT gateway
After keying the details click on “Create VPC

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794504712/ud_jzEUGA.png)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794512259/gZvpg9kpC.png)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794517159/XoV5Ct0i-.png)

- On click of “OK”, the list will be displayed as below

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794536770/L6e8HqtAN.png)

- After successful creation of VPC, Subnets, Route Tables and Internet Gateway will be created automatically

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794559372/K_FLhX2IVn.png)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794568044/94kWBkQAB8.png)


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794574081/hNEqavpQM.png)


- Verify Public subnet route configuration is open for Public access. In order to have public access the CIDR must be 0.0.0.0/0 and Target should be Internet Gateway.
Each VPC should have only 1 Internet gateway.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794594943/NNQffF1R_.png)


- Navigate to “Route tables“ and associate Public subnet -> Public route and Private Subnet -> Private route

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794621651/_CYKzfwlR.png)

Route Table displayed as “Main” must be mapped to Private subnet

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794638801/lzd0olGQu.png)


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794645717/DiUCg7ngR.png)


- Private route tables route config has NAT gateway configured which helps Private EC2 to access Internet for only outbound traffic


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794667578/kPkm4gXn6.png)

- Enable Auto assign IP for Public subnet in order to allocate public IPs for Instances launched in Public subnet. This IP can be still overridden by providing Elastic IPs.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794698449/x_TfYYO9s.png)


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1641794704370/fxwtUzS5Q.png)


*Thank you for reading, Please like the article, It will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!*