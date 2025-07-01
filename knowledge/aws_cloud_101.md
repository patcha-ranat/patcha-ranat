# AWS Cloud 101

*Patcharanat P.*

# Table of Contents
- [1. AWS Cloud Practitioner Essentials](#1-aws-cloud-practitioner-essentials)
    - [1.2 AWS Cloud Practitioner Essentials - Module 2 - Compute in the cloud](#12-cloud-essentials---module-2---compute-in-the-cloud)
    - [1.3 AWS Cloud Practitioner Essentials - Module 3 - Severless](#13-cloud-essentials---module-3---severless)
        - [1.3.1 Additional Compute Services](#131-additional-compute-services)
    - [1.4 AWS Cloud Practitioner Essentials - Module 4 - Introduction to going Global](#14-cloud-essentials---module-4---introduction-to-going-global)
    - [1.5 AWS Cloud Practitioner Essentials - Module 5 - Networking](#15-cloud-essentials---module-5---networking)
        - [1.5.1 Concepts](#151-concepts)
        - [1.5.2 Services](#152-services)
        - [1.5.3 Additional Services](#153-additional-services)
        - [1.5.4 Subnets, Security Groups, and Network Access Control Lists](#154-subnets-security-groups-and-network-access-control-lists)
        - [1.5.5 Global Networking](#155-global-networking)
        - [1.5.6 Global Architecture](#156-global-architecture)
    - [1.6 AWS Cloud Practitioner Essentials - Module 6 - Storage](#16-aws-cloud-practitioner-essentials---module-6---storage)

# 1. AWS Cloud Practitioner Essentials

## 1.1 AWS Cloud Practitioner Essentials - Introduction

1. AWS Shared Reponsibility Model
- Customer Responsibility - responsible for security and application deployed ***IN*** Cloud
    - *including Network ACLs and security groups*
- AWS Responsibility - responsible for security and hardware ***OF*** cloud

## 1.2 AWS Cloud Practitioner Essentials - Module 2 - Compute in the cloud

1. Scaling vs Elasticity
    1. elastic = adjusting resource (scale) automatically in response to changes in demand
    2. scaling = scaling up-down / out-in
2. EC2 and type + pricing
    1. on-demand
    2. spot
    3. saving plans
    4. reserved instances
    5. Multi-tenancy (same instances while isolated)
3. Amazon Machine Image (AMI)
4. Auto Scaling (scaling up / out)
5. ELB: Elastic Load Balancing → route traffic, not scaling
6. SQS: Simple Queue Service: message/queue service
7. SNS: Simple Notification Service: publish-subscribe service (+topic)
8. EventBridge: Serverless event-driven service

## 1.3 AWS Cloud Practitioner Essentials - Module 3 - Severless

1. Unmanaged / Managed / Fully-Managed
2. AWS Lambda - function - event-driven
3. ECS: Elastic Container Service (Orchestrator)
4. EKS: Elastic Kubernetes Service (Orchestrator)
5. ECR: Amazon Elastic Container Registry
6. AWS Fargate (compute option) (unless, EC2) - serverless compute engine for container

### 1.3.1 Additional Compute Services

- Elastic Beanstalk - deploying on EC2 without concerning scaling, load balancing (fully managed)
    - good for - web app / RESTful API / mobile backend / microservices with automated scaling
- AWS Batch - a compute service for processing massive dataset without scaling and infrastructure concerns
    - parallel is possible
    - suit for scientific computing - analysis / big data processing / machine learning training
- Amazon Lightsail - simplified web app hosting
    - virtual private server (VPS), storage, database, and networking
    - suit for small business, basic workloads (no scaling, just minimal included in one package)
- AWS Outposts - hybrid-cloud
    - low-latency / data processing in remote / migrating legacy application

## 1.4 AWS Cloud Practitioner Essentials - Module 4 - Introduction to going Global

- CLoudFront - edge location → low-latency by caching concept (located separatedly from region)
- multi-region / multi-az are related to
    - latency of user
    - compliance
    - fault-tolerance
    - and cost to operate
- CloudFormation - Infrastructure as Code (IaC)

## 1.5 AWS Cloud Practitioner Essentials - Module 5 - Networking

### 1.5.1 Concepts

- Amazon Networking = Virtual Private Cloud (VPC)
    - is used to establish boundaries around AWS resources
- public / private
- subnet
    - can be used to organize your resources and can be made publicly and privately accessible
    - segments of VPC
    - subnet is a range of IP addresses in VPC
    - private subnet shouldn’t be directly exposed to public internet, unless with VPN
- Virtual Private Network (VPN) → creates a connection that is more like a secure tunnel through the internet.
    - A VPN encrypts your internet traffic, helping protect it from anyone who might try to intercept or monitor it.
- bypass all the VPN traffic with AWS Direct Connect
- Virtual private gateway
    - A virtual private gateway allows protected internet traffic to enter into the VPC.
    - A virtual private gateway is the virtual private network (VPN) endpoint on the AWS side. It provides a way for you to establish a secure, encrypted connection between your on-premises network and your virtual private cloud (VPC).

### 1.5.2 Services

- AWS Client VPN
    - provides secure access to AWS resources and on-premises networks from anywhere with VPN. It is elastic and fully managed.
- AWS Site-to-Site VPN
    - create a secure connection between your data center or branch offices and your AWS Cloud resources
    - secure connection (encrypted) between remote locations
- AWS PrivateLink
    - with PrivateLink, you can use to privately connect your VPC to your external services and resources as if they were in your VPC
    - you control specific API endpoints, sites, services, and resources that are reachable from your VPC
    - Still, traffic jams are possible because PrivateLink use the same connection as other clients, that’s why sometimes we need a dedicated private connection for a lot of bandwidth
- AWS Direct Connect
    - establish a dedicated private connection between your network and VPC
    - reduce network cost, increase amount of bandwidth
    - best or latency-sensitive application / large-scale data migration / hybrid cloud architecture

### 1.5.3 Additional Services

- AWS Transit Gateway
    - connect VPC and on-premise networks through central-hub
- Network Address Translation (NAT) Gateway
    - to make instances in private subnet can connect to services outside your VPC, but external services can’t initiate a connection with those instances
- Amazon API Gateway
    - securing API

### 1.5.4 Subnets, Security Groups, and Network Access Control Lists

- Packet -> VPC - Internet Gateway (IGW) -> Public Subnet -> Evaluate ***Network Access Control List*** (Network ACL) -> Security Group
- Network ACL (Stateless) -> only check if sender is in the approved list (not checking the content). confition for in and out can be different
    - Subnet Level
- Security Group (Stateful) can be configured to accept only specified type of connections
    - Instance Level
- In VPC creation demo, VPC can be created in AWS VPC service and private/public subnet can also be created within the service.
    - don't set Auto-assign UP settings to keep it private subnet.
    - public subnet can't be public without **Internet Gateway** (IGW) attached to VPC
    - Route Table contains a set of rules called routes, used to determined where network traffic is directed
        - Each subnet in the VPC must be associated with a route table to control the route for that subnet
        - Use Route table to route internet traffic to Internet Gateway (or to route traffic inside the network)

### 1.5.5 Global Networking

- Edge Networking Services - Secure and speedy networking for user-facing application data
    - DNS Resolver + Server - Translating Domain Name to IP Address
- Amazon Route 53 is an AWS DNS Service 
- CloudFront is Content Delivery Network (CDN) - delivery service for your content with faster loading time (caching)
- AWS Global Accelerator - networking service that helps your application run faster *globally* by adding fault-tolerance and changing route when some AZ goes down.
    - example - global gaming company use case, Financial Service application

### 1.5.6 Global Architecture

- VPN should be used when it needs
    - Secure
    - Flexible
    - Remote Access
    - Small-scale
    - Dedicated isn't necessary
- AWS Direct Connect should be used when it needs
    - High bandwidth
    - Low latency
    - Large data transfer / Consistent performance
    - Critical application

## 1.6 AWS Cloud Practitioner Essentials - Module 6 - Storage

- Block Storage
    - AWS EC2 instance store - unmanaged non-persistent - high performance block storgae
    - Amazon Elastic Block Store (EBS) - managed service - persistent block storage
- Object Storage
    - Amazon Simple Storage Service (S3)
- File Storage - Shared file system
    - Amazon Elastic File System (EFS)
    - Amazon FSx 
- Additional Storage Services
    - AWS Storage Gateway
    - AWS Elastic Disaster Recovery

---