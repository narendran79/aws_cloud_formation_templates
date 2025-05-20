# CloudFormation Template: Deploying a Simple Web Service

This CloudFormation template allows you to deploy a simple web service in AWS, including the following resources:
- VPC (Virtual Private Cloud)
- Public and Private Subnets
- Internet Gateway for public access
- EC2 Instance for running the web application
- RDS MySQL Database for data storage
- S3 Bucket for object storage
- Security Group for controlling access to the EC2 instance

## Overview

This template provides the basic infrastructure for a simple web service, allowing you to deploy the following components in an isolated network:
1. A **VPC** with public and private subnets across two Availability Zones for high availability.
2. An **EC2 instance** in the public subnet that acts as the web server.
3. An **RDS MySQL instance** in the private subnet for data storage.
4. An **S3 bucket** to store any necessary files.
5. A **Security Group** to control access to EC2 instances.

### Resources Deployed:
- **VPC**: A Virtual Private Cloud to isolate the resources.
- **Subnets**: Public and private subnets across multiple Availability Zones.
- **Internet Gateway**: Enables internet access for the public subnet.
- **EC2 Instance**: A small web server (`t2.micro` instance type).
- **RDS MySQL Database**: A MySQL instance in the private subnet.
- **S3 Bucket**: A private S3 bucket for storing files.
- **Security Group**: Configured to allow HTTP (port 80) traffic to the EC2 instance.

## Prerequisites
We have two option to deploy our CFT template
 - Using AWS Console UI - we require either free tier or root access account.
 - Using AWS CLI - we need to make sure CLI installed in our system and configured with aws account using access key.

## Parameters

The template accepts the following parameters that you can modify to customize the deployment:

- `EnvironmentName`: A prefix for naming resources (e.g., EC2 instance, S3 bucket).
- `VpcCIDR`: CIDR block for the VPC.
- `PublicSubnetCIDR`: CIDR block for the public subnet.
- `PrivateSubnetCIDR`: CIDR block for the private subnet.
- `PrivateSubnet2CIDR`: CIDR block for a second private subnet.
- `AvailabilityZone`: The primary Availability Zone for resources.
- `SecondaryAvailabilityZone`: A secondary Availability Zone for high availability.
- `KeyName`: EC2 key pair to allow SSH access to the EC2 instance.
  
### SnapShot:
- **VPC**
  <img width="634" alt="vpc-cft" src="https://github.com/user-attachments/assets/42583109-c9eb-4f43-bc38-09fb03fae940" />
- **Security Group**
  <img width="806" alt="sg-cft" src="https://github.com/user-attachments/assets/c7bd02c0-95e1-4d08-8293-73a33f52ef50" />
- **EC2**
  <img width="818" alt="ec2-cft" src="https://github.com/user-attachments/assets/17493362-1e85-403a-b5fd-8bcb6c656b66" />
- **RDS**
  <img width="792" alt="rds-cft" src="https://github.com/user-attachments/assets/50ea45ba-44b0-4ea2-be03-65730232a35c" />
- **S3**
  <img width="798" alt="s3-cft" src="https://github.com/user-attachments/assets/6b87a618-288a-4f05-9b7c-1d60f5f7936e" />
