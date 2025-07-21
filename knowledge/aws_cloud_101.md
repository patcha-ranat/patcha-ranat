# AWS Cloud Practitioner Essentials

*Patcharanat P.*

# Table of Contents
- [1. AWS Cloud Practitioner Essentials - Introduction](#1-aws-cloud-practitioner-essentials---introduction)
- [2. AWS Cloud Practitioner Essentials - Module 2 - Compute in the cloud](#2-cloud-essentials---module-2---compute-in-the-cloud)
- [3. AWS Cloud Practitioner Essentials - Module 3 - Severless](#3-cloud-essentials---module-3---severless)
    - [3.1 Additional Compute Services](#31-additional-compute-services)
- [4. AWS Cloud Practitioner Essentials - Module 4 - Introduction to going Global](#4-cloud-essentials---module-4---introduction-to-going-global)
- [5. AWS Cloud Practitioner Essentials - Module 5 - Networking](#5-cloud-essentials---module-5---networking)
    - [5.1 Concepts](#51-concepts)
    - [5.2 Services](#52-services)
    - [5.3 Additional Services](#53-additional-services)
    - [5.4 Subnets, Security Groups, and Network Access Control Lists](#54-subnets-security-groups-and-network-access-control-lists)
    - [5.5 Global Networking](#55-global-networking)
    - [5.6 Global Architecture](#56-global-architecture)
- [6. AWS Cloud Practitioner Essentials - Module 6 - Storage](#6-aws-cloud-practitioner-essentials---module-6---storage)
    - [6.1 Block Storage](#61-block-storage)
    - [6.2 Object Storage](#62-object-storage)
    - [6.3 File Storage - Shared File System](#63-file-storage---shared-file-system)
    - [6.4 Additional Storage Services](#64-additional-storage-services)
- [7. AWS Cloud Practitioner Essentials - Module 7 - Databases](#7-aws-cloud-practitioner-essentials---module-7---databases)
    - [7.1 Relational Database Services](#71-relational-database-services)
    - [7.2 NoSQL Database Services](#72-nosql-database-services)
    - [7.3 In-Memory Caching Services](#73-in-memory-caching-services)
    - [7.4 Additional Database Services](#74-additional-database-services)
- [8. AWS Cloud Practitioner Essentials - Module 8 - AI/ML and Data Analytics](#8-aws-cloud-practitioner-essentials---module-8---aiml-and-data-analytics)
    - [8.1 AI/ML On AWS](#81-aiml-on-aws)
    - [8.2 Generative AI on AWS](#82-generative-ai-on-aws)
    - [8.3 Intro to Data Analytics](#83-intro-to-data-analytics)
- [9. AWS Cloud Practitioner Essentials - Module 9 - Security](#9-aws-cloud-practitioner-essentials---module-9---security)
    - [9.1 Security Control](#91-security-control)
    - [9.2 Network and Application Protection](#92-network-and-application-protection)
    - [9.3 Protecting Data](#93-protecting-data)
    - [9.4 Detection and Incident Response](#94-detection-and-incident-response)
- [10. AWS Cloud Practitioner Essentials - Module 10 - Monitoring, Compliance, and Governance](#10-aws-cloud-practitioner-essentials---module-10---monitoring-compliance-and-governance)
- [11. AWS Cloud Practitioner Essentials - Module 11 - Pricing and Support](#11-aws-cloud-practitioner-essentials---module-11---pricing-and-support)
    - [11.1 Pricing and Billing](#111-pricing-and-billing)
    - [11.2 Support Plans](#112-support-plans)
    - [11.3 Marketplace and Partners](#113-marketplace-and-partners)
    - [11.4 Cost Optimization](#114-cost-optimization)
- [12. AWS Cloud Practitioner Essentials - Module 12 - Migrating to AWS Cloud](#12-aws-cloud-practitioner-essentials---module-12---migrating-to-aws-cloud)
    - [12.1 Database Migration](#121-database-migration)
    - [12.2 Migration Data to AWS](#122-migration-data-to-aws)
- [13. AWS Cloud Practitioner Essentials - Module 13 - Well-architectured Solutions](#13-aws-cloud-practitioner-essentials---module-13---well-architectured-solutions)


## 1. AWS Cloud Practitioner Essentials - Introduction

1. AWS Shared Reponsibility Model
- Customer Responsibility - responsible for security and application deployed ***IN*** Cloud
    - *including Network ACLs and security groups*
- AWS Responsibility - responsible for security and hardware ***OF*** cloud


## 2. AWS Cloud Practitioner Essentials - Module 2 - Compute in the cloud

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


## 3. AWS Cloud Practitioner Essentials - Module 3 - Severless

1. Unmanaged / Managed / Fully-Managed
2. **AWS Lambda** - function - event-driven
3. **ECS: Elastic Container Service** (Orchestrator)
4. **EKS: Elastic Kubernetes Service** (Orchestrator)
5. **ECR: Amazon Elastic Container Registry**
6. **AWS Fargate** (compute option) (unless, EC2) - serverless compute engine for container

### 3.1 Additional Compute Services

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


## 4. AWS Cloud Practitioner Essentials - Module 4 - Introduction to going Global

- **CloudFront** - edge location → low-latency by caching concept (located separatedly from region)
- multi-region / multi-az are related to
    - latency of user
    - compliance
    - fault-tolerance
    - and cost to operate
- **CloudFormation** - Infrastructure as Code (IaC)


## 5. AWS Cloud Practitioner Essentials - Module 5 - Networking

### 5.1 Concepts

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

### 5.2 Services

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

### 5.3 Additional Services

- **AWS Transit Gateway**
    - connect VPC and on-premise networks through central-hub
- **Network Address Translation (NAT) Gateway**
    - to make instances in private subnet can connect to services outside your VPC, but external services can’t initiate a connection with those instances
- **Amazon API Gateway**
    - securing API

### 5.4 Subnets, Security Groups, and Network Access Control Lists

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

### 5.5 Global Networking

- Edge Networking Services - Secure and speedy networking for user-facing application data
    - DNS Resolver + Server - Translating Domain Name to IP Address
- **Amazon Route 53** is an AWS DNS Service 
- **CloudFront** is Content Delivery Network (CDN) - delivery service for your content with faster loading time (caching)
- **AWS Global Accelerator** - networking service that helps your application run faster *globally* by adding fault-tolerance and changing route when some AZ goes down.
    - example - global gaming company use case, Financial Service application

### 5.6 Global Architecture

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


## 6. AWS Cloud Practitioner Essentials - Module 6 - Storage

### 6.1 Block Storage

- **AWS EC2 instance store** - unmanaged non-persistent - high I/O performance block storage (gone with EC2 instance stopped) come with default EC2 setup
- **Amazon Elastic Block Store (EBS)** - managed service - persistent hard drives (EBS volumes) - can be attached to EC2
- Data Lifecycle = creating + backing up + deleting / snapshots
    - Incremental Backup = faster + storage efficient
    - snapshot = point-in-time
    - **Amazon Data Lifecycle Manager** = automated snapshot lifecycle management 
    - EBS snapshots - using s3 for storing backup (redundantly in multiple-AZs)
        - EBS snapshots can capture the exact state of volume at a point in time, making them able to be duplicated environment for testing purpose

### 6.2 Object Storage

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

### 6.3 File Storage - Shared file system

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

### 6.4 Additional Storage Services

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


## 7. AWS Cloud Practitioner Essentials - Module 7 - Databases

Fully-managed / Managed / Unmanaged

- **AWS Database Migration Service (AWS DMS)** - A key benefit of AWS DMS is that the source database remains fully operational during migration, which minimizes downtime to applications.

### 7.1 Relational Database Services

- **Amazon Relational Database Service (Amazon RDS)**
    - Managed service
    - patching up + backup + security (network isolation / encryption)
    - supports Amazon Aurora, MySQL, PostgreSQL, Microsoft SQL Server, MariaDB, Oracle
    - Multi-AZ
- **Amazon Aurora**
    - designed to help unnecessary I/O
    - highly available storage architecture offering higher throughput than the regular db
        - distributing I/O across multiple storage nodes

### 7.2 NoSQL Database Services

- **DynamoDB** - fully managed serverless NoSQL
    - fast, flexible schema, no ACID

### 7.3 In-Memory Caching Services

- **Amazon ElastiCache**
    - storing frequently accessed data at easily accessible location, improving time performance for heavy read traffic.
    - serverless is available
    - with cache, we can even use a smaller size of database

### 7.4 Additional Database Services

- **AWS DocumentDB** - MongoDB compatible (DynamoDB is not compatible with MongoDB)
- **AWS Backup** - EBS / EFS / RDS / DynamoDB - Centralized backup management
- **AWS Neptune** - graph database e.g. social network user connection mapping - low-latency query on highly connected datasets
- **AWS Managed Blockchain** - create + manage blockchain networks


## 8. AWS Cloud Practitioner Essentials - Module 8 - AI/ML and Data Analytics

### 8.1 AI/ML On AWS

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

### 8.2 Generative AI on AWS

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

### 8.3 Intro to Data Analytics

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


## 9. AWS Cloud Practitioner Essentials - Module 9 - Security

- Authentication: Verifying identity through credentials
- Authorization: Grant user access rights and permissions to determine what action they can perform in a system

### 9.1 Security Control

- Root User - Owner of the account, has permission to do anything
    - We don't want to use root user to operate daily task due to security risks
- **AWS Identity and Access Management (IAM)**, you can create IAM users to operate daily task with granted permission (none by default)
    - *Least Priviledge Principle* - grant permission only what they need for a task
    - *IAM Policy* = Permission
    - IAM Policy is JSON document that describe what API calls user can and cannot make
    - *IAM groups* make it more convenient to manage permission for a group of users
        - we can attach IAM Policy to the group to make all user in that group inherit those permissions
    - *Role* similar to users and groups, but without static credentials such as username and password
        - Role can be used to temporarily grant access to AWS resources to users, external identities, applications, even or other AWS services
        - Role is an identity that can be assumed to gain access to temporary permissions.
        - Role is helpful when trying to manage permission at scale in an organization by avoiding creating credentials for every single user in organization. Instead, use their coporate credentials mapping to IAM Roles
        - Role - Federated Identity / Cross-account
        - By role, user who assumes IAM role drops all the previous permissions to use access only available for a new role
- **IAM Identity Center** - single sign-on (SSO)
    - Federated Identity Management is a system that allows user to access multiple applications, services, or domains using single set of credentials
- **AWS Secret Manager** - manage, rotate, retrieve secrets (database credentials, API keys, etc.)
- **AWS System Manager** - provide centralized view of nodes across your organization's account

### 9.2 Network and Application Protection

- Distributed Deniel os Service (DDoS / DoS) - an attack on enterprise's infrastructure by overwhelming the capacity of your application
- **AWS Shield Standard** - automatically protects AWS resource from common DDoS, built into AWS services, like ELB, CloudFront, Route 53 at no extrac cost
- **AWS Shield Advanced** - attack diagnosis and ability to detect sophisticated DDoS attack
- **AWS Web Application Firewall (WAF)** - filter incoming traffic by checking IP Address against a web access control list (web ACL)
- Additional integration
    - AWS Shield + AWS WAF
    - Security Groups / ELB / AWS Region to prevent DDoS

### 9.3 Protecting Data

- Encryption-Decryption (key)
    - Data Encryption at rest
    - Data Encryption in transit - SSL/TLS are used to establish encrypted network connections
- **AWS Key Management Service (KMS)** - manage *cryptographic keys* (random string of digits used for encrypting and decrypting)
    - we can also specify which IAM users and roles can manage keys
- Secure Socket Layer (SSL)
- Transport Layer Security (TLS) - SSL upgraded
- Hypertext Transfer Protocol Secure (HTTPS), site secured by TLS or SSL
- **Amazon Macie**
    - monitor/assess using Machine Learning to check sensitive data   in S3
- **AWS Certificate Manager (ACM)** - 
    - Centralized SSL/TLS management + on-premises, provide data encryption in transit

### 9.4 Detection and Incident Response

- **Amazon Inspector** - automated security assessments for EC2, containers, lambda functions
- **Amazon GuardDuty** - identify threats by continuously monitoring account metadata & network activity
- **Amazon Detective** - investigate root cause + visualization
- **AWS Security Hub** - multiple security services in single place


## 10. AWS Cloud Practitioner Essentials - Module 10 - Monitoring, Compliance, and Governance

Governance - Secure, Monitor, Audit, Compliance

- **Amazon Cloud Watch** - one place to monitor infrastructure and the applications on AWS
    - CloudWatch metrics
    - CloudWatch alarms - alarm when metrics hit the set threshold (can also be integrated with SNS)
    - CloudWatch dashboard
    - CloudWatch logs
- **AWS CloudTrail** - logs every API request made to AWS into S3 - audit
- Compliance
    - **AWS Artifact** - AWS security and compliance
        - agreements
        - reports
    - **AWS Config** - assess, audit, evaluate configuration of AWS resources
    - **AWS Audit Manager** - audit AWS usage to simplify risk and compliance assessment, also collect evidence and manage audit
- **AWS Organization** - account management service to centralize multiple AWS account within an organization.
    - programmatically create AWS account / hierarchy / Service Control Policies (SCP) / Organization Unit (OU)
    - it can also manange an individual member account
- Governance
    - **AWS Control Tower** - setup and govern a secure, compliant, multi-account AWS env.
    - **AWS Service Catalog** - provision resource, apply access controls, find and deploy with self-service
    - **AWS License Manager** - help manage and govern your software licenses
- **AWS Health** - notify about service events, planned changes, account notification that affect your AWS resource health
- **AWS Trusted Advisor** - automated advisor, evaluating your resources against 5 categories of checks
- **IAM Access Analyzer** - set, verify, refine, validate IAM policies


## 11. AWS Cloud Practitioner Essentials - Module 11 - Pricing and Support

AWS Pricing
- Pay as you go
- Save when you commit
- Pay less by using more
Driving Factors
- Compute
- Storage
- Outbound data transfer

### 11.1 Pricing and Billing

- AWS Organizations
    - consolidate billing with multiple AWS account
- **AWS Billing and Cost Management Dashboard** - centralized cost management, showing current charges, usage, forecast, and detailed breakdowns + setting up payment methods
- **AWS Budget** - set custom budgets for cost, usage exceed thresholds
- **AWS Cost Explorer** - visualize, analyze, and manage AWS cost with interactive graphs, reports, and forecast
- **AWS Price Calculator** - web-based planning tool to estimate price

### 11.2 Support Plans

1. Basic Support - no cost (customer service, documentation, forums, AWS Trusted Advisor, AWS Health)
2. Developer Support - Basic Support + email to customer support directly
3. Business Support - 1. + 2. + phone access to AWS Support Team + Full access of Trusted Advisor
4. Enterprise Support - (On-ramp & Enterprise) all previous plans + reduced response time + architectural consultative

### 11.3 Marketplace and Partners

- **AWS Marketplace** - digital catalog for find, test, buy, deploy, and manage third-party software running on AWS
    - reduce cost of ownership + accelerate innovation
    - Software as a Service (SaaS)
    - Machine Learning and AI
    - Data and analytics
- **AWS Partner Network (APN)** - global community that uses AWS for their customers
    - Funding
    - Partner Events
    - Partner Training and Certification

### 11.4 Cost Optimization

- AWS Compute Optimizer
- Spot Instance
- Auto Scaling
- Caching with AWS ElastiCache
- S3 with Archive options


## 12. AWS Cloud Practitioner Essentials - Module 12 - Migrating to AWS Cloud

1. Assess
    - **Migration Evaluator** - estimate cost of relocation & developing migration rediness plan for business case
2. Mobilize
    - **AWS Application Discovery Service** - explore current on-premises setup and report what you would need
    - **AWS Migration Hub** - command center for moving process - discovery, assessment, planning, and execution
3. Migrate and Modernize
    - Migration Tools
        - **AWS Application Migration Service** - automated migration and minimal downtime to quickly move to cloud
        - **AWS Database Migration Service** -  reduce the cost of migrating and modernizing applications
    - Data Transfer Tools
        - **AWS DataSync**
        - **AWS Transfer Family**
        - **AWS Snow Family**

- **AWS Cloud Adoption Framework (AWS CAF)** - provide advice to enable quick migration to AWS
    - 6 aspects separated by roles (Business, People, Governance, Platform, Security, Operations)

- 7 Migration Strategies
    1. Rehost - Migrate to AWS as-is
    2. Relocate - on-premises to cloud
    3. replatform - mapping service + upgrade for more benefits
    4. refactor / rearchitecting
    5. repurchase - moving traditional license to SaaS model
    6. retain - stay where it lays, deprecated but keep it run for a while
    7. retire - no longer being used (end-of-life)

### 12.1 Database Migration

- AWS Database Migration Service (DMS) - a service to migrate your database (Relational Database, Data Warehouse, NoSQL, or Analytics workloads)
    - DMS is a VM, we configure source and target database, it migrate data while your original database is still alive
- **AWS Schema Conversion Tool (SCT)** - converting source's schema and code object (such as stored procedures, views, and functions) into a format compatible with the target database (some part require manual if it can't be converted automatically)
    - commercial db to open-source db
- Migration Types
    - Homogenous - from same type of database to same type
    - Heterogenous - from one type of database to different type

### 12.2 Migration Data to AWS

- Transferring Data Online
    - **AWS DataSync** - automating, accelerating data transfer between on-premises and AWS storage services
    - **AWS Transfer Family** - seamlessly manage and share data with secure and scalable file transfer with various protocols
    - AWS Direct Connect - from networking module is also a great solution 
- Transferring Data Offline
    - **AWS Snowball Edge Optimized Devices** - suit to offline large data migration, and also able to be used for edge computing 


## 13. AWS Cloud Practitioner Essentials - Module 13 - Well-architectured Solutions

- AWS Services for Specialized Use Case
    1. Development Services
        - **AWS CodeBuild** - automated CI service
        - **AWS CodePipeline** - automates your release pipeline (CI/CD)
        - **AWS X-Ray** - help monitor and debug your application (visualize application behavior)
        - **AWS AppSync** - help implement simpler GraphQL API
        - **AWS Amplify** - add authen, API, storage hosting for application on AWS with minimal infrastructure management
    2. Business Application Services
        - **Amazon Connect** - cloud-based contact center service
        - **Amazon Simple Email Service (SES)** - help send large volume of emails
    3. End-user Computing Services
        - **Amazon AppStream 2.0** - stream desktop application to users on any device, instead of installing software locally
        - **Amazon WorkSpaces** - fully managed virtual desktop infrastructure service
        - **Amazon WorkSpaces Secure Browser** *~~Amazon WorkSpaces Web~~* - Amazon WorkSpaces, but more light-weighted and only web-based (SaaS)
    4. IoT Services
        - **AWS IoT Core** - securely connect to IoT devices
- Well-Architectured Framework
    - 6 Pillars
        1. Operational Excellence - operations, monitoring, automation, continuous improvement
        2. Security - use security best practice (e.g. least priviledge)
        3. Reliability - recovery planning, system adaptability according to workload & demand
        4. Performance Efficiency - using right resource for right workload
        5. Cost Optimization - smart provisioning, reduce cost
        6. Sustainability - promote energy-efficient design
    - **AWS Well-Architectured Tool (AWS WA Tool)** - free, help assess

---