November 20, 2020

The Exam Blue Print
Objective
Weighting
Cloud Concepts
26%
Security
25%
Technology
33%
Billing and Pricing
16%

Exam Guide : https://d1.awsstatic.com/training-and-certification/docs-cloud-practitioner/AWS-Certified-Cloud-Practitioner_Exam-Guide.pdf

White Paper: https://docs.aws.amazon.com/whitepapers/latest/aws-overview/what-is-cloud-computing.html
*** https://d1.awsstatic.com/whitepapers/aws-overview.pdf
** https://d0.awsstatic.com/whitepapers/aws_pricing_overview.pdf
https://aws.amazon.com/compliance/shared-responsibility-model/

Three Types of Cloud Computing:

* Infrastructure As A Service (IAAS)
* Platform As A Service (PAAS)
* Software As A Service (SAAS)


Three Types of Cloud Computing Deployments
* Public Cloud - AWS, Azure, GCP
* Hybrid - Mixture of public and private
* Private Cloud (Or On Premise) - You Manage it, in your datacenter.Openstack or Vmware

AWS - High Level Services


What will you learn in this course:
Compute
* EC2
* Lambda
Databases
* Relational Database Service (RDS)
* DynamoDB (Non Relational Databases)
Storage
* Simple Storage Service(S3)
* Glacier
Network
* VPC
* Route53

Region:
A region is a physical location in the world which consists of two or more availability zones(AZ’s)

Availability Zone:
An AZ is one or more discrete data centers, each with redundant power, networking and connectivity, housed in separate facilities.

Edge Locations:
Edge locations are endpoints for AWS which are used for caching content. Typically this consists of CloudFront, Amazon’s Content Delivery Network(CDN)

Choosing the right AWS region?
* Data sovereignty laws
* Latency to end users
* AWS Services

Understanding the difference support packages:
* Basic - Free
* Developer - $29 a month (Scales based on usage)
* Business - $100 a month (Scales based on usage)
* Enterprise - $15000 a month (Scales based on usage) - TAM, Technical account manager)

Setting up on a mac
* Download BBEDIT from Appstore
* Download RDP(Microsoft Remote Desktop) to connect to windows machines
* Terminal

IAM
 Key Features of IAM
* Centralized control of your AWS account
* Shared access to your AWS account
* Granular permissions
* Multi-factor authentication
* Ability to provide temporary access for users, devices, and services where necessary
* A customizable password rotation policy.
* Integration with many different AWS services
 Key Terminology for IAM
* Users : End users, such as people, employees of an organization, etc
* Groups: A collection of users. Each user in the group will inherit the permissions of the group.
* Roles: you can create roles and assign them to AWS resources.
* Policies: Policies are made up of documents, which are called policy documents. These documents are formatted in Javascipt object notation(JSON) and provide permissions for users, groups, and roles.

S3:(Simple Storage Service)
What is S3:
* S3 is safe place to store your files.
* It is Object-based storage.
* The data is spread across multiple devices and facilities.
The basics of S3:
* S3 is Object-based - i.e allows you to upload files.
* Files can be from 0 Bytes to 5TB.
* There is unlimited storage.
* Files are stored in Buckets.
* S3 is universal namespace. That is, names must be unique globally.
* When you upload a file to S3, you will receive a HTTP 200 code if the upload is successful.
S3 - Objects:
S3 is Object based. Think of Objects just as files. Object consist of the following:
* Key (This is simply the name of the object)
* Value (This is simply the data and is made up of a sequence of bytes).
* Version ID (Important for versioning)
* Metadata (Data about data you are storing)
* Subresources;
               - Access control lists
               - Torrent
How does data consistency work for S3?
* Read after write consistency for PUTS of new Objects.
* Eventually consistency for overwrite PUTS and DELETES (can take some time to propagate).
S3 has the following features:
* Tiered storage available.
* Lifecycle management.
* Versioning.
* Encryption.
* Secure your data using access control lists and bucket policies.
S3 Storage classes:
* S3 standard
* S3 - IA (Infrequently Accessed)
* S3 One Zone - IA (Infrequently Accessed)
* S3 - Intelligent Tiering
* S3 Glacier
* S3 Glacier Deep Archive
* S3 Outposts
Restricting Bucket Access
* Bucket policies - Applies across the whole bucket
* Object Policies - Applies to individual files.
* IAM Policies to Users & Groups - Applies to Users & Groups.
CloudFront:
What is CloudFront?
 A content delivery network(CDN) is a system of distributed servers(network) that deliver webpages and other web content to a user based on the geographic locations of the user, the origin of the webpage, and a content delivery server.
Key Terminology:
Edge location - This is the location where content will be cached. This is separate to an AWS Region/AZ.
Origin - This is the origin of all the files that the CDN will distribute. This can be an S3 bucket, an EC2 Instance, an Elastic Load Balancer, or Route53.
Distribution - This is the name given the CDN which consists of a collection of Edge locations.

Types of CloudFront distributions:
* Web - Typically used for websites.
* RTMP - Used for media streaming.

EC2 : Elastic Cloud Compute
What is EC2?
  Amazon Elastic Compute Cloud(Amazon EC2) is just a virtual server(or servers) in the cloud.
 Amazon EC2 reduces the time required to obtain and boot new server instances to minutes, allowing you to quickly scale capacity, both up and down, as your computing requirements change.
EC2 Pricing models:
* On Demand - Allows you to pay a fixed rate by the hour (Or by the second) with no commitment.
* Reserved - Provides you with a capacity reservation, and offer a significant discount on the hourly charge for an instance. Contract terms are 1 year or 3 years terms.
* Spot - Enables you to bid whatever price you want for instance capacity, providing for even greater savings if your application have flexible start end times.
* Dedicated hosts - Physical EC2 server dedicated for your use. Dedicated Hosts can help you reduce costs by allowing you to use your existing server-bound software licenses.






EC2 Instance Types:
   




EBS volume types:
SSD:
*    General Purpose SSD(GP2)
*    Provisioned IOPS SSD(IO1)
Magnetic:
*    Throughput Optimized HDD (ST1)
*    Cold HDD (SC1)
*    Magnetic
Relational databases on AWS-RDS

Six different types of DB technologies:
* SQL Server
* Oracle
* MySQL Server
* Postgres SQL
* Aurora
* MariaDB
RDS has two keys features:
* Multi-AZ- for disaster recovery
* Read Replicas - For performance
Amazon’s Non-Relational Database is called DynamoDB
Red Shift OLAP 

What is ElastiCache?
   ElastiCache is a Web service that makes it easy to deploy, operate, and scale an in-memory cache in the cloud. The service improves the performance of web applications by allowing you to retrieve information from fast, managed, in-memory caches, instead of relying entirely on slower disk-based databases
* Memcached
* Redis

Route53:

* Amazons DNS Service is called Route53.
* Its global, similar to IAM and S3.
* You can use it to direct traffic all around the world you can use it to register a domain name.

Elastic Beanstalk:

With Elastic Beanstalk, you can quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure that runs those applications. You simply upload your application, and Elastic Beanstalk automatically handles the details of capacity provisioning, load balancing,scaling, and application health monitoring.

Architecting for the Cloud:
Traditional Computing vs Cloud Computing:
* IT Assets as provisioned resources.
* Global, Available, and scaleable capacity.
* Higher level managed services
* Built-in security.
* Architecting for cost
* Operations on AWS
Scalability:
* Scale up
* Scale out
              - Stateless applications
              - Distribute load to multiple nodes
              - Stateless components
              - Stateful components
              - Implement session affinity
              - Distributed processing
              - Implement distributed processing
Infrastructure As code
* Cloud Formation
Automation:
*  Serverless management and deployment
* Infrastructure management and deployment
              - AWS Elastic Beanstalk
              - AWS EC2 auto recovery
              - AWS systems manager
              - Auto scaling
      
*  Alarms and Events
             - Amazon CloudWatch alarms
             - Amazon cloud watch events
             - Amazon Lambda scheduled events
             - AWS WAF security automations

Caching:
* Application caching
* Edge caching

Global AWS Services
* IAM
* Route53
* CloudFront
* SNS
* SES
Some services give global views but are regional
* S3
What AWS Services can be used on Premises?
* Snowball - Gigantic Disk
* Snowball Edge (like computer with storage)
* Storage Gateway
* CodeDeploy
* Opsworks
* IoT Greengrass

Amazon CloudWatch:
  Amazon CloudWatch is a monitoring service to monitor your AWS resources, as well as the applications that you run on AWS.
CloudWatch can monitor things like
*  Compute
              - EC2 Instance
              - Autoscaling Groups
              - Elastic Load Balancers
              - Route53 Health Checks
*  Storage & content Checks 
              - EBS Volumes
              - Storage Gateways
              - CloudFront
*    Host Level Metrics Consist of
              - CPU
              - Network
              - Disk
              - Status Check
AWS Systems Manager Explained
* Systems Manager can be used to manage fleet of EC2 Instances and machines
* A piece of software installed on each VM.
* Can be both inside AWS and on premise
* Run command is used to instal, patch, uninstall software.
* Integrates with CloudWatch to give you a dashboard of your entire estate.
Know the 6 advantages of Cloud

* Trade capital expense for variable expense
* Benefit from massive economies of scale
* Stop guessing about capacity.
* Increase speed and agility
* Stop spending money running and maintaining data centers
* Go global in minutes.

Billing and Pricing

Capex vs Open
* Capex stands for capital expenditure which where you pay up front. Its fixed , sunk cost.
* Opex stands for Operational Expenditure which is where you pay for what you use. Think of utility billing such s electricity, gas, water etc.
The basic pricing policies are as follows:
* Pay as you go
* Pay less when you reserve
* Pay even less per unit by using more
* Pay even less as AWS grows
* Custom pricing.
Understanding the fundamentals of Pricing
There are three fundamental drivers of cost with AWS:
* Compute
* Storage
* Data Outbound
The following services are free:
* Amazon VPC
* Elastic Beanstalk
* CloudFormation
* IAM
* Auto Scaling
* Opsworks
* Consolidated Billing
What Determine price?
* Clock hours of server time
* Instance type
* Pricing model
* Number of Instances
* Load Balancing
* Detailed monitoring
* Auto scaling
* Elastic IP addresses
* Operating systems and software packages

What determines price for Lambda?




What Determines price for EBS?
* Volumes (Per GB)
* Snapshots (Per GB)
* Data Transfer
What Determines price for S3?
* Storage class (standard or IA or 1 AZ IA etc)
* Storage
* Requests (GET, PUT, COPY)
* Data transfer
What determines price for Glacier?
* Storage
* Data retrieval times


What is Snowball?
  AWS Snowball is a PB-scale data transport solution that uses secure appliance to transfer large amounts of data into and out of the AWS cloud
   Think of it as a gigantic disk to move your data into AWS.
What determines price for Snowball?
* Service fee per job
               - Snowball 50TB : $200
               - Snowball 80TB: $250
* Daily charge
              - First 100 days are free, after that it is $15 a day
*  Data Transfer
              - Data transfer into S3 is free. Data transfer out is not

RDS
What determines price for RDS?
* Clock hours of server time
* Database characteristics
* Database purchase type
* Number of database instances
* Provisioned storage
* Additional storage
* Requests
* Deployment type
* Data transfer
What determines price for DynamoDB?


AWS Budgets:
*  AWS Budgets gives you the ability to set custom budgets that alert you when your costs or usage exceed (or are forecasted to exceed) your budgeted amount.
* Used to budget costs BEFORE they have been incurred.

AWS Cost Explorer:
* AWS Cost Explorer has an easy-to-use interface that lets you visualize, understand and manage your AWS costs and usage over time.
* Used to explore costs AFTER they have been incurred.

AWS Support Plans:







Tags:

What are tags?
* Key value pairs attached to AWS resources
* Metadata (data about data)
* Tags can sometimes be inherited.
Resource groups make it easy to group your resources using the tags that are assigned to them. You can group resources that share one or more tags.
* Region
* Name
* Healthchecks
* 
What is AWS Organizations?
   AWS organizations is an account management service that enables you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

Available in two features sets:
* Consolidated billing
* All features

CloudTrail vs CloudWatch
* CloudWatch monitors performance
* Cloud trail monitors API calls in the AWS platform.
CloudTrail : 
* Per AWS account and is enabled per region
* Can consolidate logs using an S3 bucket.
                 1. Turn on CloudTrail in paying account.
                 2. Create a bucket policy that allows cross-account access.
                 3. Turn on CloudTrail in the other accounts and use the bucket in the paying account.
                  
AWS Calculators
AWS help you to calculate your costs using a couple of different calculators.
Available in two features sets:
* AWS simple monthly calculator
* AWS total cost of ownership calculator

## IAM
- IAM Best Practices
  - Root Account: Only use the root account to create your AWS account. Do not use it to login
  - Users: One user should equal one real human being. Dont create phanton users
  - Users/Groups/Policies : Always place users in groups, and then apply policies to the groups. This makes management easier.
  - Roles: Use roles to access other AWS services
  - IAM credential report : Use IAM credential reports to audit the permissions of your users/accounts.