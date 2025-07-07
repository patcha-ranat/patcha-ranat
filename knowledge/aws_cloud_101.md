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
        - [1.6.1 Block Storage](#161-block-storage)
        - [1.6.2 Object Storage](#162-object-storage)
        - [1.6.3 File Storage - Shared File System](#163-file-storage---shared-file-system)
        - [1.6.4 Additional Storage Services](#164-additional-storage-services)
    - [1.7 AWS Cloud Practitioner Essentials - Module 7 - Databases](#17-aws-cloud-practitioner-essentials---module-7---databases)
        - [1.7.1 Relational Database Services](#171-relational-database-services)
        - [1.7.2 NoSQL Database Services](#172-nosql-database-services)
        - [1.7.3 In-Memory Caching Services](#173-in-memory-caching-services)
        - [1.7.4 Additional Database Services](#174-additional-database-services)
    - [1.8 AWS Cloud Practitioner Essentials - Module 8 - AI/ML and Data Analytics](#18-aws-cloud-practitioner-essentials---module-8---aiml-and-data-analytics)
        - [1.8.1 AI/ML On AWS](#181-aiml-on-aws)
        - [1.8.2 Generative AI on AWS](#182-generative-ai-on-aws)
        - [1.8.3 Intro to Data Analytics](#183-intro-to-data-analytics)

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
2. **EC2** and type + pricing
    1. on-demand
    2. spot
    3. saving plans
    4. reserved instances
    5. Multi-tenancy (same instances while isolated)
3. **Amazon Machine Image (AMI)**
4. **Auto Scaling** (scaling up / out)
5. **ELB**: Elastic Load Balancing → route traffic, not scaling
6. **SQS**: Simple Queue Service: message/queue service
7. **SNS**: Simple Notification Service: publish-subscribe service (+topic)
8. **EventBridge**: Serverless event-driven service

## 1.3 AWS Cloud Practitioner Essentials - Module 3 - Severless

1. Unmanaged / Managed / Fully-Managed
2. **AWS Lambda** - function - event-driven
3. **ECS: Elastic Container Service** (Orchestrator)
4. **EKS: Elastic Kubernetes Service** (Orchestrator)
5. **ECR: Amazon Elastic Container Registry**
6. **AWS Fargate** (compute option) (unless, EC2) - serverless compute engine for container

### 1.3.1 Additional Compute Services

- **Elastic Beanstalk** - deploying on EC2 without concerning scaling, load balancing (fully managed)
    - good for - web app / RESTful API / mobile backend / microservices with automated scaling
- **AWS Batch** - a compute service for processing massive dataset without scaling and infrastructure concerns
    - parallel is possible
    - suit for scientific computing - analysis / big data processing / machine learning training
- **Amazon Lightsail** - simplified web app hosting
    - virtual private server (VPS), storage, database, and networking
    - suit for small business, basic workloads (no scaling, just minimal included in one package)
- **AWS Outposts** - hybrid-cloud
    - low-latency / data processing in remote / migrating legacy application

## 1.4 AWS Cloud Practitioner Essentials - Module 4 - Introduction to going Global

- **CloudFront** - edge location → low-latency by caching concept (located separatedly from region)
- multi-region / multi-az are related to
    - latency of user
    - compliance
    - fault-tolerance
    - and cost to operate
- **CloudFormation** - Infrastructure as Code (IaC)

## 1.5 AWS Cloud Practitioner Essentials - Module 5 - Networking

### 1.5.1 Concepts

- Amazon Networking = **Virtual Private Cloud (VPC)**
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

- **AWS Client VPN**
    - provides secure access to AWS resources and on-premises networks from anywhere with VPN. It is elastic and fully managed.
- **AWS Site-to-Site VPN**
    - create a secure connection between your data center or branch offices and your AWS Cloud resources
    - secure connection (encrypted) between remote locations
- **AWS PrivateLink**
    - with PrivateLink, you can use to privately connect your VPC to your external services and resources as if they were in your VPC
    - you control specific API endpoints, sites, services, and resources that are reachable from your VPC
    - Still, traffic jams are possible because PrivateLink use the same connection as other clients, that’s why sometimes we need a dedicated private connection for a lot of bandwidth
- **AWS Direct Connect**
    - establish a dedicated private connection between your network and VPC
    - reduce network cost, increase amount of bandwidth
    - best or latency-sensitive application / large-scale data migration / hybrid cloud architecture

### 1.5.3 Additional Services

- **AWS Transit Gateway**
    - connect VPC and on-premise networks through central-hub
- **Network Address Translation (NAT) Gateway**
    - to make instances in private subnet can connect to services outside your VPC, but external services can’t initiate a connection with those instances
- **Amazon API Gateway**
    - securing API

### 1.5.4 Subnets, Security Groups, and Network Access Control Lists

- Packet -> VPC - Internet Gateway (IGW) -> Public Subnet -> Evaluate ***Network Access Control List*** (Network ACL) -> Security Group
- **Network ACL (Stateless)** -> only check if sender is in the approved list (not checking the content). confition for in and out can be different
    - Subnet Level
- **Security Group (Stateful)** can be configured to accept only specified type of connections
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
- **Amazon Route 53** is an AWS DNS Service 
- **CloudFront** is Content Delivery Network (CDN) - delivery service for your content with faster loading time (caching)
- **AWS Global Accelerator** - networking service that helps your application run faster *globally* by adding fault-tolerance and changing route when some AZ goes down.
    - example - global gaming company use case, Financial Service application

### 1.5.6 Global Architecture

- VPN should be used when it needs
    - Secure
    - Flexible
    - Remote Access
    - Small-scale
    - Dedicated isn't necessary
- **AWS Direct Connect** should be used when it needs
    - High bandwidth
    - Low latency
    - Large data transfer / Consistent performance
    - Critical application

## 1.6 AWS Cloud Practitioner Essentials - Module 6 - Storage

### 1.6.1 Block Storage

- **AWS EC2 instance store** - unmanaged non-persistent - high I/O performance block storage (gone with EC2 instance stopped) come with default EC2 setup
- **Amazon Elastic Block Store (EBS)** - managed service - persistent hard drives (EBS volumes) - can be attached to EC2
- Data Lifecycle = creating + backing up + deleting / snapshots
    - Incremental Backup = faster + storage efficient
    - snapshot = point-in-time
    - **Amazon Data Lifecycle Manager** = automated snapshot lifecycle management 
    - EBS snapshots - using s3 for storing backup (redundantly in multiple-AZs)
        - EBS snapshots can capture the exact state of volume at a point in time, making them able to be duplicated environment for testing purpose

### 1.6.2 Object Storage

- **Amazon Simple Storage Service (S3)** - virtually unlimited storage, object life cycle management, broad range of use cases
    - pay-as-you-use
    - S3 Storage Class - different type of storage behavior leading to cost optimized
        - S3 Standard - access regularly / general-purpose
        - S3 Standard-IA - Infrequent Access / perfect for backup
        - Glacier - long-term archiving - relatively slow for retrieval / lower cost
        - Glacier Instant Retrival - quick access occasionally e.g. medical images / media files
        - Glacier Flexible Retrieval
        - Glacier Deep Archive - the most cost effective option - suit for data hardly ever need
        - Additional Options - One Zone - stored in only one AZ (the standard option stores in three of it)
            - S3 Express One Zone - faster than the standard but more cost saving
            - S3 Express One Zone-IA suit for secondary backup
        - Outposts - offer storage on on-premise environment on AWS Outposts
    - S3 Lifecycle
        - help you move data between classes automatically as defined or delete when it's no longer needed
        - S3 Intelligent-Tiering - automatically move data between classes **based on data usage**
        - Transition Actions (change storage class) e.g. regular data that changes in access frequency 
        - Expiration Actions (delete) - e.g. logs

### 1.6.3 File Storage - Shared file system

- **Amazon Elastic File System (EFS)**
    - good for use case that have multiple instances accessing the data at the same time, scaled up and down automatically
    - multi-AZs redundancy
    - EBS is not **automatically scale** and the same AZ with EC2 is required in order to connect.
    - EFS can be connected even across region (cloud & on-premises)
    - Storage Classes
        - EFS Standard / ESF Standard-Infrequent Access (Standard-IA)
        - EFS One Zone / EFS One Zone-Infrequent Access (One Zone-IA)
        - EFS Archive
    - Amazon EFS data lifecycle
- **Amazon FSx**
    - EFS focus more on Network File System (NFS) but FSx supports mutiple filesystem protocols, reducing complexity of managing infrastructure.
    - Windows File Server / NetApp ONTAP / OpenZFS / Lustre
    - Use cases:
        - Migrate Windows File to AWS
        - Accelerate hybrid workloads
        - Reduce SQL Server Deployment Cost
        - Streamline virtual desktop and streaming
        - etc.

### 1.6.4 Additional Storage Services

- **AWS Storage Gateway**
    - hybrid cloud storage service, giving you seamless on-premises access to virtually unlimited cloud storage
    - local caching
    - Three types
        - S3 File Gateway - with S3
        - Volume Gateway - local block storage on on-premises
            - Cached Volume Mode - low-latency
            - Stored Volume Mode - backing up to EBS snapshots
        - Tape Gateway - Physical Tape to Cloud (S3)
    - backing up critical data to cloud without changing backup workflow
- **AWS Elastic Disaster Recovery**
    - replicated with block-level data
    - near-instant recovery

## 1.7 AWS Cloud Practitioner Essentials - Module 7 - Databases

Fully-managed / Managed / Unmanaged

- **AWS Database Migration Service (AWS DMS)** - A key benefit of AWS DMS is that the source database remains fully operational during migration, which minimizes downtime to applications.

### 1.7.1 Relational Database Services

- **Amazon Relational Database Service (Amazon RDS)**
    - Managed service
    - patching up + backup + security (network isolation / encryption)
    - supports Amazon Aurora, MySQL, PostgreSQL, Microsoft SQL Server, MariaDB, Oracle
    - Multi-AZ
- **Amazon Aurora**
    - designed to help unnecessary I/O
    - highly available storage architecture offering higher throughput than the regular db
        - distributing I/O across multiple storage nodes

### 1.7.2 NoSQL Database Services

- **DynamoDB** - fully managed serverless NoSQL
    - fast, flexible schema, no ACID

### 1.7.3 In-Memory Caching Services

- **Amazon ElastiCache**
    - storing frequently accessed data at easily accessible location, improving time performance for heavy read traffic.
    - serverless is available
    - with cache, we can even use a smaller size of database

### 1.7.4 Additional Database Services

- ****AWS** DocumentDB** - MongoDB compatible (DynamoDB is not compatible with MongoDB)
- **AWS Backup** - EBS / EFS / RDS / DynamoDB - Centralized backup management
- **AWS Neptune** - graph database e.g. social network user connection mapping - low-latency query on highly connected datasets
- **AWS Managed Blockchain** - create + manage blockchain networks

## 1.8 AWS Cloud Practitioner Essentials - Module 8 - AI/ML and Data Analytics

### 1.8.1 AI/ML On AWS

3 Tiers

1. **AI Services** - pre-built models that are already trained to perform specific functions
    - Language Services
        - **Amazon Comprehend** - NLP text summary
        - **Amazon Polly** - text-to-speech
        - **Amazon Transcribe** - speech-to-text
        - **Amazon Translate** - Language Translation
    - Computer vision and search services
        - **Amazon Kendra** - NLP search to query enterprise content
        - **Amazon Rekognition** - image/video analysis & detection
        - **Amazon Textract** - extract text from input (handwritten, form, tables)
    - Conversational AI and personalized services
        - **Amazon Lex** - adding voice and text to conversational app [Natural Language Understanding / Automatic Speech Recognition] (NLU / ASR) 
        - **Amazon Personalize** - personalized recommendation
2. **AWS ML Service**
    - a more customized approach with **Amazon SageMaker AI** where you build, train, and deploy your own ML models **with fully managed**. also including experiment tracking, data visualization, debugging, monitoring workflow, **IDE integrated**.
3. **ML frameworks and infrastructure**
    - a completely custom approach to building models using purpose-built chips that integrate with popular ML frameworks
    - using only AWS infrastructure to develop their own ML solution

### 1.8.2 Generative AI on AWS

- **Amazon SageMaker JumpStart** - An ML Hub with Foundation Models (FMs) and pre-built ML solutions deployable with a few click
    - Rapid ML deployment with a few click
    - fine-tuned pre-trained Foundation Model with your Data
    - ML experiment and prototypes
- **Amazon Bedrock** - A fully managed service for adapting and deploying FMs from Amazon or other leading AI companies
    - Production-ready (enterprise-grade) genAI seamlessly integrated with your AWS application
    - Multimodal content generation
    - Advanced conversational AI 
- **Amazon Q** - An interactive AI Assistant that can be integerated with a company's information repositories
    - **Amazon Q Business** - answer question, help solve problem for business, such as information requests, automated workflows, insight extraction
    - **Amazon Q Developer** - help development in coding, faster code generation, improving reliability and security, automated code reviews

### 1.8.3 Intro to Data Analytics

- **Amazon Redshift** - Data Warehouse for high performance analytical workload
- **Amazon Athena**
    - fully managed serverless service submit SQL job to query from various types of source
    - only pay for query you run
- **Amazon Kinesis** - Ideal for large-scale real-time data ingestion
- **Amazon Data Firehose** - fully managed near-real-time ingestion (to multiple consumers)
- **AWS Glue Data Catalog** - centralized metadata repository for org's datasets (data discovery)
- **AWS Glue** - Managed Service
    - visual ETL job creation, built-in job scheduling
    - also offer code-free script creation
- **Amazon EMR** - large-scale data processing service used with popular framework, like Apache Spark, Hadoop, Hive
    - suit for data expert according to highly customizable configuration
- **Amazon QuickSight**
    - Unified Business Intelligence (BI)
    - Interactive Dashboard
    - with Amazon Q integrated within, NLP is available for EDA
- **Amazon OpenSearch Service**
    - real-time search, monitoring, and analysis
    - e.g. application monitoring, log analytics, observability, and website search

---