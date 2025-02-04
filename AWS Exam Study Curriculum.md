[[AWS Fundamentals]]
[[IAM, Accounts and AWS Organisations]]
[[AWS Simple Storage Service (S3)]]
[[AWS Virtual Private Cloud]]
[[AWS Elastic Compute Cloud]]
[[AWS Containers & Elastic Container Service]]
[[Advanced EC2]]
[[AWS Route 53 - Global DNS]]
[[AWS Relational Database Service (RDS)]]
[[Network Storage & Data Lifecycle]]
[[High Availability & Scaling]]
[[Serverless and Application Services]]
[[Global Content Delivery and Optimisation]]
[[Advanced VPC Networking]]
[[Hybrid Environments and Migration]]
[[Security, Deployments & Operations]]
[[Infrastructure as Code (Cloudfront)]]
[[NOSQL Databases & DynamoDB]]
[[Machine Learning 101]]
[[Other Services & Features]]


### Notes on further study

#### **First Practice Exam**

Result: You have reached 43 of 65 point(s), (66.15%)

 Categories
1. CSAA – Design Cost-Optimized Architectures 100%
2. CSAA – Design High-Performing Architectures 59.09%
3. CSAA – Design Resilient Architectures 73.68%
4. CSAA – Design Secure Architectures 63.64%

READ THE QUESTION CLOSELY

Amazon Artifact - no idea about generating complicance report
Amazon Macie - ML based monitoring for senstive data
- also don't know Kendra or Polly, other ML services
Database services - further knowledge needed about certain options:
- DB Authentication on RDS
- Dynamo DB streams for event driven triggers
- DynamoDBs attributes and pro/cons
- Database migration service
- DynamoDB partition keys (cardinality attributes)
Real-time large data processing:
- Kinesis data stream
AWS Direct Connect
AWS Transit Gateway
[AWS Storage Gateway]([https://docs.aws.amazon.com/storagegateway/latest/userguide/StorageGatewayConcepts.html](https://docs.aws.amazon.com/storagegateway/latest/userguide/StorageGatewayConcepts.html))
CloudFront 
- Origin failover
- [signed-cookies ](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-choosing-signed-urls-cookies.html)
AWS CloudHSM
AWS Auto-scaling groups
- when scaling in, which instances will be chosen to be folded down? [Default termination policy](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html#default-termination-policy)
A little brush up on CloudWatch Metrics from EC2 - not too bad. Unavailable are:
1. Memory utilization
2. Disk swap utilization
3. Disk space utilization
4. Page file utilization
5. Log collection
AWS Glue - don't know anything about this service and its ETL stuff
AWS API Gateway, look into:
- canary releases
AWS WAF
- [protecting against SQL injections]([https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-use-case.html#aws-managed-rule-groups-use-case-sql-db](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-use-case.html#aws-managed-rule-groups-use-case-sql-db))
- [general](https://docs.aws.amazon.com/waf/latest/developerguide/how-aws-waf-works.html)
Lambda Encryption of ENVVARS
- [KMS encryption helpers ](https://docs.aws.amazon.com/lambda/latest/dg/configuration-envvars.html#env_encrypt)
AWS Transfer for SFTP
AWS Resource Access Manager
AWS FSx
- [general]([https://aws.amazon.com/fsx/](https://aws.amazon.com/fsx/))
- for [lustre](https://aws.amazon.com/blogs/startups/picking-the-right-data-store-for-your-workload/](https://aws.amazon.com/fsx/))
AWS Lake Formation


#### Second practice exam 

You have reached 42 of 65 point(s), (64.62%)

 **Categories**
1. CSAA – Design Cost-Optimized Architectures 54.55%
2. CSAA – Design High-Performing Architectures 64.29%
3. CSAA – Design Resilient Architectures 73.68%
4. CSAA – Design Secure Architectures 61.9%

Cloudfront
Global accelerator
RDS 
- specifically failover behaviour (CNAME swaps to the secondary)

** [AWS Datasync](https://docs.aws.amazon.com/datasync/latest/userguide/what-is-datasync.html) (migration) vs Storage Gateway (ongoing hybrid infra) 

Can't have EIPs on ALB, only on NLBs

Cost-allocation tags + AWS Budget

AWS Data Migration service
- its functionality and abilities

SQS
- you can't set priorities on individual queue items

Snowmobile (large truck) vs Snowmobile edge (little package)

AWS Security Token Service

Amazon EMR 
Data lifecycle manager

VPC Gateway Endpoint

Allipcation load balancer

Snowball 

Guard Duty

VPC peering conections
Direct Connect
VPN

Decoupled architecture with SQS and SWF 

#### Third Practice Exam - (timed)

This was a redo of the first one (didn't realise they repeated across types)

You have reached 62 of 65 point(s), (95.38%)

Categories
1. CSAA – Design Cost-Optimized Architectures 100%
2. CSAA – Design High-Performing Architectures 95.45%
3. CSAA – Design Resilient Architectures 100%
4. CSAA – Design Secure Architectures 90.91%

wrong again:
[DB Authentication](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/UsingWithRDS.IAMDBAuth.html) - you can get access to a DB (Postgres and MySQL) via tokens generated and linked to an IAM user or profile.

DynamoDB *still has a schema* in the sense that the schema is just the defintion of the model or structure of the data
- scales very well and globally (unlike relational databases)

Cloudfront failover policy will improve hit rate for end users during periods of high traffic


#### Fourth Practice Exam 

A little bit of Kinesis:
- default settings
- feature set

Service Role Policies

READ THE QUESTION'

[EC2 Placement groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)

[cloudfront OAI](https://tutorialsdojo.com/s3-pre-signed-urls-vs-cloudfront-signed-urls-vs-origin-access-identity-oai-origin-access-control-oac/)

[Fargate](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ECS_GetStarted_Fargate.html)

Cloudfront

[VPC Subnets ](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html)

#### Fifth Practice Exam 

**Amazon Textract**
**Amazon Comprehend Medical**

