# Domain 0 - AWS Fundamentals

## Cloud Computing

Cloud computing is the on-demand delivery of IT resources over the internet with pay-as-you-go pricing. Instead of buying, owning, and maintaining physical data centers and servers, you can access technology services, such as computing power, storage, and databases, on an as-needed basis from a cloud provider like Amazon Web Services (AWS)

### Benefits:

- Lower costs - Pay only for what you use instead of upfront hardware investments.
- Scalability - Scale resources up or down automatically based on demand.
- Global footprint - Deploy applications close to users worldwide through AWS's global infrastructure.
- High availability - Built-in redundancy minimizes downtime across isolated data centers.
- Security - Enterprise-grade protections and compliance certifications are built into the platform.
- Innovation - Access new services and technologies without managing underlying infrastructure.

## Cloud Models

- Public Cloud - Resources owned and operated by a third-party provider like AWS.
- Private Cloud - Dedicated infrastructure used exclusively by a single organization.
- Hybrid Cloud - Combines public and private clouds for flexible workloads.

## Cloud Service Types

- Infrastructure as a service (IaaS) - Rent virtual machines, storage, and networking without managing physical hardware.
- Platform as a service (PaaS) - Build and deploy applications on a managed platform without managing the OS.
- Software as a service (SaaS) - Use complete software applications over the internet on a subscription basis.

## IaaS Drawbacks

- IT Expertise - You must configure, patch, and manage the operating system and applications yourself.
- Cost Management - Unmonitored usage can lead to unexpected spending on compute and storage.
- Vendor Lock-in - Migrating workloads to another provider can be complex and time-consuming.

## PaaS Advantages

- Focus - Developers concentrate on code rather than infrastructure management.
- Costs - Reduced overhead from managed runtimes and built-in tooling.
- Fully Fledged Development Platform - Includes databases, middleware, and deployment tools out of the box.
- Analytics - Built-in monitoring and reporting help track application performance.
- Data Integration - Simplified connectors make combining data sources easier.

## Software as a Service

- Amazon WorkDocs - Secure document sharing and collaboration for teams.
- Amazon Chime - Online meetings, video conferencing, and chat.
- Amazon Connect - Cloud-based contact center with voice and chat support.
- Amazon Q - Generative AI assistant for business users and developers.
- Amazon Q Developer - AI coding assistant integrated into the development workflow.

## Global Cloud

- Region - A geographic area containing multiple isolated Availability Zones.
- Availability Zones (AZ) - One or more discrete data centers within a Region.
- Local Zones - Extensions of AWS Regions that place compute closer to end users.

## Region

- Proximity to users - Lower latency when resources are deployed near your audience.
- Compliance - Data residency requirements may restrict which Regions you can use.
- Available Services - Not every AWS service is available in every Region.
- Costs - Pricing varies by Region based on local infrastructure and demand.

## Availability Zones

- Each region has at least 3 - Provides fault tolerance if one data center fails.
- 10s of miles from each other - Close enough for low latency but far enough to limit shared disaster risk.

## Local Zones

- For applications needing extremely low latency - Places compute within single-digit milliseconds of end users in metro areas.
- Streaming media, gaming, VR, AI - Workloads where even small delays noticeably degrade user experience.

## Pricing Models

- On-Demand Instances - Pay by the hour or second with no long-term commitment.
- Savings Plans - Commit to consistent usage for lower rates across compute services.
- Dedicated Hosts - Physical servers dedicated to your use for licensing or compliance needs.
- Spot Instances - Use spare AWS capacity at steep discounts when interruptions are tolerable.

## Shared Responsibility Model

- AWS responsibile for security OF the cloud - Protects the underlying infrastructure that runs all AWS services.
    - Protecting infrastructure
    - Physical security of data centers, hardware, software, networking, global

- Customer responsibile for security IN the cloud - Owns securing data, identities, and configurations you deploy.
    - Securing and managing deployed components

## AWS IAM

- IAM User - Person, app, or system
- IAM Group - Group of IAM Users
- IAM Role - Not a user. Identity with specific permissions
- MFA (Multi-factor authentication) - Requiring two or more proofs of identity to log in

## Policies

- Identity-based Policies - Attach to users, groups, or roles to define what they can do.
- Resource-based Policies - Attach directly to resources like S3 buckets to grant cross-account access.

## Account Tiers

- 12 months free tier - New accounts get limited free usage of popular services for one year.
- Always free - Selected services remain free within monthly usage limits indefinitely.
- Short-term trials - Time-limited access to premium services before standard charges apply.

# AWS Services

## Analytics

- AWS Data Exchange - Marketplace for finding and subscribing to third-party datasets.
- Amazon EMR - Managed clusters for big data processing with Hadoop and Spark.
- AWS Glue - Serverless ETL service and data catalog for preparing and discovering data.
- AWS Glue DataBrew - Visual, no-code tool for cleaning and transforming data.
- AWS Lake Formation - Builds and secures data lakes on top of S3.
- Amazon OpenSearch Service - Managed search and log analytics engine.
- Amazon Quick - Generative BI tool for exploring data with natural language.
- Amazon Redshift - Cloud data warehouse for large-scale analytics.

## Cloud Financial Management

- AWS Budgets - Set custom cost and usage budgets with alerts.
- AWS Cost Explorer - Visualize and analyze AWS spending over time.

## Compute

- Amazon EC2 - Resizable virtual servers in the cloud.
- AWS Lambda - Run code on demand without managing servers.

## Containers

- Amazon Elastic Container Service (Amazon ECS) - Run and orchestrate Docker containers on AWS.
- Amazon Elastic Kubernetes Service (Amazon EKS) - Managed Kubernetes for container orchestration.

## Database

- Amazon Aurora - High-performance MySQL and PostgreSQL–compatible relational database.
- Amazon DocumentDB (with MongoDB compatibility) - Managed document database compatible with MongoDB.
- Amazon DynamoDB - Serverless NoSQL key-value and document database.
- Amazon ElastiCache - Managed in-memory caching with Redis or Memcached.
- Amazon Neptune - Managed graph database for connected data.
- Amazon RDS - Managed relational databases for MySQL, PostgreSQL, and more.

## Developer Tools

- Kiro - AI-powered IDE for building applications on AWS.
- Strands Agents - Open-source SDK for building AI agents with tool use.
- Amazon Q - Generative AI assistant for developers and business users.

## Machine Learning

- Amazon Augmented AI (Amazon A2I) - Adds human review to ML predictions when needed.
- Amazon Bedrock - Access foundation models and build GenAI apps via API.
- Amazon Bedrock AgentCore - Managed runtime for deploying and scaling AI agents.
- Amazon Comprehend - NLP for sentiment, entities, and key phrases.
- Amazon Kendra - Intelligent enterprise search powered by ML.
- Amazon Lex - Build conversational chatbots and voice interfaces.
- Amazon Nova - AWS family of foundation models for text and multimodal tasks.
- Amazon Personalize - Real-time recommendations and personalization.
- Amazon Polly - Converts text to lifelike speech.
- Amazon Rekognition - Analyzes images and video for objects, faces, and labels.
- Amazon SageMaker AI - End-to-end platform to build, train, and deploy ML models.
- Amazon SageMaker JumpStart - Pre-built models and templates to deploy ML quickly.
- Amazon Textract - Extracts text and data from documents.
- Amazon Transcribe - Converts speech to text.
- Amazon Translate - Neural machine translation between languages.
- AWS Transform - AI agents that automate application modernization and cloud migration.

## Management and Governance

- AWS CloudTrail - Logs API calls and account activity for auditing.
- Amazon CloudWatch - Monitors metrics, logs, and alarms for AWS resources.
- AWS Config - Tracks resource configurations and compliance over time.
- AWS Trusted Advisor - Recommends best practices for cost, security, and performance.
- AWS Well-Architected Tool - Reviews workloads against AWS architecture best practices.

## Networking and Content Delivery

- Amazon CloudFront - Global CDN for fast content delivery.
- Amazon VPC - Isolated virtual network for your AWS resources.

## Security, Identity, and Compliance

- AWS Artifact - On-demand access to AWS compliance reports and agreements.
- AWS Audit Manager - Automates continuous compliance auditing.
- AWS Identity and Access Management (IAM) - Controls who can access AWS resources.
- Amazon Inspector - Scans workloads for software vulnerabilities.
- AWS Key Management Service (AWS KMS) - Creates and manages encryption keys.
- Amazon Macie - Discovers and protects sensitive data in S3.
- AWS Secrets Manager - Stores and rotates secrets like API keys and passwords.

## Storage

- Amazon S3 - Scalable object storage for any amount of data.
- Amazon S3 Glacier - Low-cost archival storage for long-term backups.
