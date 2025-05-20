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

- **AWS CLI** installed and configured with appropriate IAM permissions.
- Access to your AWS account to deploy CloudFormation templates.

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
  
### Example:
```yaml
EnvironmentName: my-web-service
VpcCIDR: 10.0.0.0/16
PublicSubnetCIDR: 10.0.1.0/24
PrivateSubnetCIDR: 10.0.2.0/24
PrivateSubnet2CIDR: 10.0.3.0/24
AvailabilityZone: us-east-1a
SecondaryAvailabilityZone: us-east-1b
KeyName: my-keypair
