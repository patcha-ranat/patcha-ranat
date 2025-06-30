# AWS Cloud 101

*Patcharanat P.*

# Table of Contents
- [1.Cloud Essentials](#1-cloud-essentials)
    - [1.2 Cloud Essentials - Module 2 - Compute in the cloud](#12-cloud-essentials---module-2---compute-in-the-cloud)
    - [1.3 Cloud Essentials - Module 3 - Severless](#13-cloud-essentials---module-3---severless)
        - [1.3.1 Additional Compute Services](#131-additional-compute-services)
    - [1.4 Cloud Essentials - Module 4 - Introduction to going Global](#14-cloud-essentials---module-4---introduction-to-going-global)
    - [1.5 Cloud Essentials - Module 5 - Networking](#15-cloud-essentials---module-5---networking)
        - [1.5.1 Concepts](#151-concepts)
        - [1.5.2 Services](#152-services)
        - [1.5.3 Additional Services](#153-additional-services)

# 1. Cloud Essentials

## 1.2 Cloud Essentials - Module 2 - Compute in the cloud

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

## 1.3 Cloud Essentials - Module 3 - Severless

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

## 1.4 Cloud Essentials - Module 4 - Introduction to going Global

- CLoudFront - edge location → low-latency by caching concept (located separatedly from region)
- multi-region / multi-az are related to
    - latency of user
    - compliance
    - fault-tolerance
    - and cost to operate
- CloudFormation - Infrastructure as Code (IaC)

## 1.5 Cloud Essentials - Module 5 - Networking

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

---