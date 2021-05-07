# [AWS Certified Cloud Practitioner Exam](https://aws.amazon.com/certification/certified-cloud-practitioner/)

## Brief Notes for AWS CPP

## Section 3: Cloud Computing and AWS

### Legacy IT
In Legacy IT, you had a corporate data center which contained it's own servers, storage servers, routers, switches, firewalls and backup systems. A company would either lease this space (co-location) or might own the entire building. Regardless if the company owns the building or not, they do own the equipment in this model. This model is very capital intensive -- you have to purchase all this equipment prior to operation. The company's corporate office is connected into this datacenter and the IT staff would have to design, build, operate and manage equipment. So, this leads to alot of cost. These costs include: data center building, data center security, physical IT hardware, software licensing costs, maintenance contracts, power, internet connectivity, staff wages (design, build, operations and maintenance).

### Examples of Cloud Computing
Some examples of cloud computing include: Gmail, Salesforce, Dropbox, AWS. So, what defines a cloud service? Well, the service can be described with the following terms: on-demand, self-service, broad network access (provided by internet access), with resources pooling. Resource pooling means that the provider is able to leverage a large number of compute resources to share for the actual delivery of the service. These services are known to have rapid elasticty. Rapid elasticity means that your services can grow very quickly as demand goes up and also shrink very quickly as demand decreases for those services. With cloud computing you typically are paying on a pay-per-use basis -- depending on your contract you usually would be using a pay as you go model.

### 6 Advantages of Cloud Computing
1. Trade capital expense for variable expense
2. Benefit from massive economies of scale
3. Stop guessing capacity
4. Increase speed and agility
5. Stop spending money on running and maintaining data centers
6. Go global in minutes

### AWS Cloud Overview
1. AWS Region is a geographical area
2. Each region consists of 2 or more Availability Zones (AZs)
3. Each region is designed to be completely isolated from the other regions
4. Availability Zones are locations into which you launch resources
5. Availability Zones are physically separated and isolated from each other
6. Availability Zones span 1 or more data centers. They have direct, low-latency, high throughput and redundant retwork connections between each other.
7. Each Availability Zone is designed to be an independent failure zone
8. Availability Zones are physically separated within a typical metro region and use different power sources

### 3 Fundamentals of AWS Pricing
1. Compute
2. Storage
3. Outbound Data Transfer

### Payment Models
1. On-Demand. Used for compute and database capacity. No long-term commitments or upfront payments.
2. Dedicated Instances. Hardware is dedicated to a single customer.
3. Spot Instances. Purchase spare capacity with *no* commitments.
4. Reservations. Up to 75% discount in exchange for a term commitment

### Reservation Options
1. Options for 1 or 3 year terms
2. Options to pay:
    1. No Upfront
    2. Partial Upfront
    3. All Upfront
3. Available for the following services:
    1. Amazon EC2 Reserved Instances
    2. Amazon DynamoDB Reserved Capacity
    3. Amazon ElastiCache Reserved Nodes
    4. Amazon Relational Database Service Reserved Instances
    5. Amazon RedShift Reserved Nodes

### AWS Acceptable Use Policy describes the prohibited uses of AWS

### Identity and Access Management (IAM)
Keep the root user secret and only login as needed. Secure with MFA.

Here are the AWS tasks that require a root user to do things:
[https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html](https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html)

### IAM Users
1. An IAM user is an entity that represents a person or service
2. Can be assigned:
    1. An access key ID and secret access key for programmatic access to the AWS API, SDK and other development tools
    2. A password for access to the management console
3. By default, users cannot access anything in the account
4. The account root user credentials are the email address used to create the account and password
5. The root account has full administrative permissions and these cannot be restricted
6. Best practices for root accounts:
    1. Don't use the root user credentials
    2. Don't share the root user credentials
    3. Create an IAM user and assign administrative permissions as required
    4. Enable Multi-Factor Authentication (MFA)
7. IAM users can be created to represent applications and these are known as service accounts
8. You can have 5,000 users per AWS account
9. Each user account has a friendly name and an Amazon Resource Name (ARN) which uniquely identifies the user across AWS
10. You should create individual IAM accounts for users. It is a best practice to *not* share accounts.
11. A password policy can be defined for enforcing password length, complexity, etc. (applies to all users)

### IAM Groups
1. Groups are collections of users and have policies attached to them
2. A group is *not* an identity and cannot be identified as a principal in an IAM policy
3. Use groups to assign permissions to users
4. Use the principal of least priviledge when assigning permissions
5. You cannot nest groups within groups

### IAM Roles
1. Roles are created and then assumed by trusted entities and define a set of permissions for making AWS service requests
2. With IAM Roles you can delegate permissions to resources for users and services without using permanent credentials
3. IAM users or AWS services can assume a role to obtain temporary security credentials that can be used to make AWS API calls
4. You can delegate using roles
5. There are no credentials associated with a role (password or access keys)

### IAM Policies
1. Policies are documents that define permissions and can be applied to users, groups and roles
2. Policy documents are written in JSON (key - value pair document that consists of attributes and values)
3. All permissions are denied by default
4. The most restrictive policy is used if multiple policies applied
5. The IAM policy simulator helps you to test and validate policies
6. The condition element can be used to apply further conditional logic

### 3 Authentication 
1. Access key ID + secret access key for programmatic access --> API <-- (MFA can be added to API operations)
2. IAM user + password --> AWS Management Console <-- (MFA can be added)
3. Signing Certificate --> Some AWS service

### IAM Access Keys
1. A combination of access key and secret access key
2. Used to make programmatic calls to AWS with the API
3. You can create, modify, view or rotate access keys
4. When created you get the access key and secret key
5. Secret key is only returned at creation time and a new key must be created
6. Ensure access keys and secret access keys stored securely
7. Users can be given access to change their own keys through IAM policy (not through the console)
8. You can disable a user access key which prevents it from being used for API calls

### IAM Console Password
1. A password that the user can enter to sign into interactive sessions such as the AWS Management Console
2. You can allow users to change their passwords
3. You can allow selected IAM users to change their passwords by disabling the option for all users and using and IAM policy to grant permissions for selected users

### IAM Server Certificate/Signing Certificate (SSL certificate)
1. SSL/TLS certificates that you can use to authenticate with some AWS services
2. AWS recommends that you use the AWS Certificate Manager (ACM) to provision, manage and deploy your server certificates
3. Use IAM only when you must support HTTPS connections in a region that is not supported by ACM

### Multi-Factor Authentication in AWS
1. Something you know (IAM username & password)
2. Something you have (Google authenticator on phone, physical MFA usb stick)

### AWS Security Token Service (STS)
1. The AWS Security Token Service (STS) is a web service that enables you to request temporary, limited-privilege credentials for IAM users or for users that you authenticate (federated users)

### IAM Best Practices
1. Lock away the AWS root user access keys
2. Create individual IAM users
3. Use AWS defined policies to assign permissions whenever possible
4. Use groups to assign permissions to IAM users
5. Grant least privilege
6. Use access levels to review IAM permissions
7. Configure a strong password policy for users
8. Enable MFA
9. Use roles for applications that run on AWS EC2 instances
10. Delegate by using roles instead of sharing credentials
11. Rotate credentials regularly
12. Remove unnecessary credentials
13. Use policy conditions for extra security
14. Monitor activity in your AWS account

### Amazon EC2
1. Amazon Elastic Compute Cloud (Amazon EC2) is a web service in the AWS Compute suite of products that provides secure, resizable compute capacity in the cloud.
2. Elastic Web-Scale computing - you can increase or decrease capacity within minutes and commission 1 to thousands of instances at the same time.
3. Completely controlled - you have complete control to include root access to each instance and can stop and start instances w/o losing data and using web service APIs.
4. Flexible Cloud Hosting Services - you can choose from multiple instance types, operating systems, and software packages as well as instances with varying memory, CPU and storage configurations.
5. You select an instance family and type depending on your application requirements - this determines the amount of CPU, RAM, disk, and network throughput your instance has.

### Amazon Machine Image (AMI)
1. An Amazon Machine Image (AMI) provides the information required to launch an instance.
2. An AMI includes the following:
	- One or more EBS snapshots, or, for instance-store-backed AMIs, a template for the root volume of the instance (for example, an operating system, an application server, and applications).
	- Launch permissions that control which AWS accounts can use the AMI to launch instances
	- A block device mapping that specifies the volumes to attach to the instance when it's launched
	
### 3 Types of AMIs
1. Community AMIs - free to use. You just select the OS you want to use
2. AWS Marketplace AMIs. Typically come with some 3rd party software and involve licensing fees
3. My AMIs - AMIs you create and use yourself

### User Data
1. User data is data that is supplied by the user at instance launch time in the form of a script
2. Typically, a series of commands that you can run. For example, `yum update` or `yum upgrade` etc. (Yum update is better to use.)
3. Limited to 16KB. So, it can't be too much.
4. It is not encrypted

### Metadata
1. Instance meta data is data about your instances that you can use to configure or manage the running instance
2. For example, IP address, ID of instance, Availability Zone where located, etc.
3. Instance meta data is availabe at http://169.254.169.254/latest/meta-data (local ip)
4. The Instance Metadata Query tool allows you to query the instance metadata without having to type out the full URI or category names

### Amazon ECS (Amazon Elastic Container Service)
1. Amazon Elastic Container Service (ECS) provides highly scalable, high performance container management service that supports Docker containers
2. A container is similar to a virtual instance but there is much less to manage (You don't manage the OS of the container, just collection of programs.)
3. With containers - the code, runtime, system tools, system libraries and settings are all packaged up together. Everything is packaged into the image.
4. Containers run quickly and reliably from one computing environment to another
5. Amazon ECS eliminates the need for you to install, operate and scale your own cluster management infrastructure

### Amazon ECS Launch Types
1. An Amazon ECS launch type determines the type of instance of infrastructure on which your tasks and services are hosted
2. There are 2 main launch types

### 2 Different ECS Launch Types
1. Amazon EC2
    1. You explicitly provision EC2 instances
	2. You are responsible for upgrading, patching and care of the EC2 instance pool
	3. You must handle cluster optimization
	4. More granular control over infrastructure
	
2. Amazon Fargate
    1. The control plane asks for resources and Fargate auto provisions resources
	2. Fargate provisions compute as needed
	3. Fargate handles cluster optimization
	4. You have limited manual control because the infrastructure is automated by Fargate
	
### AWS Lambda
1. AWS Lambda is a serverless computing technology that allows you to run code without provisioning or managing servers
2. You literally just put your code into AWS Lambda; not on a server you manage
3. You pay nothing for the code until it executes. Then, you only pay for execute time itself.
4. AWS Lambda scalses automatically depending on the amount of resources required

### Benefits of AWS Lambda
1. No servers to manage
2. Continuous scaling
3. Subsecond metering
4. Integrates with almost all other AWS services

### Amazon LightSail
1. Amazon Lightsail is great for users who do *not* have deep AWS technical expertise as it makes it very easy to provision compute services
2. Amazon Lightsail provides developers compute, storage, and networking capacity and capabilities to deploy and manage websites, web applications, and databases in the cloud
3. Amazon Lightsail includes everything you need to launch your project quickly -- a virtual machine, SSD-based storage, data transfer, DNS management and a static IP
4. Amazon Lightsail provides preconfigured virtual private servers that include everything you need to deploy applications and create a database

### Comparisons of EC2, ECS (EC2 Launch Type), ECS (Fargate Launch Type) and Lambda
1. EC2
    1. EC2
	    1. You manage the operating system
		2. Scale vertically - more CPU/Mem/HDD or scale horizontally (automatic) with auto scaling
		3. Use for traditional applications and long running tasks
		4. Pay for instance runtime based on family/type
2. ECS (EC2 Launch Type)
    1. You manage container instance (EC2) and the containers (tasks)
	2. Manually add container instances or use ECS Services and EC2 Auto Scaling
	3. Use for microservices and batch use cases where you need containers and need to retain management of underlying platform
	4. Pay for instances runtime based on family/type
3. ECS (Fargate Launch Type)
    1. You manage the containers (tasks)
	2. AWS scales the cluster automatically
	3. Use for microservices and batch use cases
	4. Pay for container run time based on allocated resources
4. Lambda
    1. You manage the code
	2. Lambda automatically scales concurrent executions up to default limit (1,000)
	3. Use for ETL, infrastructure automation, data validation, mobile backends
	4. Pay only for execution time based on memory allocation
	
### Amazon Simple Storage Service (S3)
1. Amazon S3 is object storage built to store and retrieve any amount of data from anywhere -- websites, mobile apps, corporate apps, data from IOT sensors, etc.
2. Any type of file can be stored in S3
3. S3 is designed to deliver 99.99999999999% (11 9s after decimal lol) durability
4. Typical use cases:
    1. Backup and Storage - Provide data backup and storage for other services
    2. Application Hosting - Provide services that deploy, install and manage web apps
    3. Media Hosting - Build a redundant, scalable, and HA infrastructure that hosts video, photo and/or music
    4. Software Delivery - Host your software apps that customers can download
    5. Static Website - you can configure and S3 bucket to serve up static website files (not dynamic)

### Amazon S3
1. Files are stored in buckets
2. Buckets are root level folders
3. Files can be anywhere from 0 bytes to 5TB
4. There is unlimited storage available
5. S3 uses a universal namespace. So, bucket names and URLs must be unique globally
6. However, you actually specify that the bucket actually be created in a certain region (Northern VA, Ohio, etc.)
7. Best practice is to create buckets closest region to your users to reduce latency
8. Objects consist of:
    1. Key (the name of the object)
    2. Value (data or a sequence of bytes)
    3. Version ID (used for versioning)
    4. Metadata (information about the stored data file)
    
### Amazon S3 Pricing
1. Storage
2. Requests
3. Storage management pricing
4. Data transfer pricing
5. Transfer acceleration pricing is extra

### Amazon S3 - 6 S3 Storage classes
1. S3 Standard - durable, immediately available, frequently accessed
2. S3 Intelligent-Tiering - automatically moves data to the most cost-effective tier
3. S3 Standard-IA - durable, immediately available, infrequently accessed
4. S3 One Zone-IA - lower cost for infrequently accessed data with less resilience
5. S3 Glacier - archived data, retrieval times in minutes or hours
6. S3 Glacier Deep Archive - lowest cost storage class for long term retention

### Amazon Virtual Private Cloud (VPC)
1. Virtual Private Cloud - A virtual private cloud (VPC) is a virtual network dedicated to your AWS account
2. Analogous to having your own data center (DC) in AWS
3. It is logically isolated from other virtual networks in the AWS Cloud
4. Provides complete control over the virtual networking environment including selection of IP ranges, creation of subnets, and configuration of route tables and gateways
5. You can launch your AWS resources, such as Amazon EC2 instances, into your VPC
6. When you create a VPC, you must specify a range of IPv4 addresses for the VPC in the form of a Classless Inter-Domain Routing (CIDR) block. Example: 10.0.0.0/16
7. A VPC spans all availability zones (AZs) in the region
8. You have full control over who has access to the AWS resources inside your VPC
9. By default, you can create up to 5 VPCs per region
10. A default VPC is created in each region with a subnet in each AZ

### Security Groups
1. Operates at the instance (interface) level
2. Support allow rules only
3. Stateful
4. Evaluates all rules
5. Applies to an instance only if associated with a group

### Network Access Control List (ACL)
1. Operates at the subnet level
2. Supports allow and deny rules
3. Stateless
4. Processes rules in order
5. Automatically applies to all instances in the subnets it is associated with

### Public IP Address
1. Lost when the instance is stopped
2. Used in Public subnets
3. No charge
4. Associated with a private IP address on the instance
5. Cannot be moved between instances

### Private IP Address
1. Retained when the instance is stopped
2. Used in Public and Private subnets

### Elastic IP Address
1. Static Public IP address - used when you need to retain a public IP
2. You are charged if not used
3. Associated with a private IP address on the instance
4. Can be moved between instances and Elastic Network Adapters

When you need to place an EC2 instance in a private subnet but provide access to the internet, you can use either NAT instance or NAT gateway. For most cases, you would use a NAT gateway instead of NAT instance because it auto-managed by AWS.

### NAT Instance (Network Address Translation)
1. Managed by you (e.g. software updates)
2. Scale up instance type manually and used enhanced networking
3. No high availability - scripted/auto-scaled HA possible using multiple NATs in multiple subnets
4. Need to assign Security Group
5. Can use as a bastion host
6. Use an Elastic IP address or a public IP address with a NAT instance
7. Can implement port forwarding through manual customization

### NAT (Network Address Translation) Gateway
1. Managed by AWS
2. Elastic scalability up to 45 Gbps
3. Provides automatic high availability within an AZ and can be placed in multiple AZs
4. No Security Groups
5. Cannot access through SSH
6. Choose the Elastic IP address to associate with a NAT gateway at creation
7. Does not support port forwarding

### Options for securely connecting to a VPC
1. AWS managed VPN - fast to setup (uses the public internet, in terms of performance not too reliable)
2. AWS Direct Connect - high bandwidth, low-latency, very reliable but takes weeks to months to setup
3. VPN CloudHub - used for connecting multiple sites to AWS
4. Software VPN - use 3rd party software

### AWS Direct Connect
1. AWS Direct Connect is a network service that provides an alternative to using the Internet to connect to a customer's on prem sites to AWS
2. Can be used to create a hybrid cloud where some resources are on-prem and some in cloud
3. Data is transmitted through a private network connection between AWS and a customer's datacenter or corporate network
4. Benefits
    1. Reduce cost when using large volumes of traffic
    2. Increase reliability (predictable performance)
    3. Increase bandwidth (predictable bandwidth)
    4. Decrease latency
5. Direct connect is charged by the port hours and data transferred
6. Available in 1Gbps and 10Gbps
7. Or, if you choose an AWS Direct Connect Partner, you can choose speeds of 50Mbps, 100Mbps, 200Mbps, 300Mbps, 400Mbps, 500Mbps

### Databases - Relational vs Non-Relational
1. Relational
    1. Organized by tables, rows and columns
    2. Rigid schema (SQL)
    3. Rules enforced within a database
    4. Typically, scaled vertically
    5. Supports complex queries and joins
    6. Amazon RDS, Oracle, MySQL, IBM DB2, PostgresSQL
2. Non-Relational
    1. Varied data storage models
    2. Flexible schema (NoSQL) - data stored in key-value pairs, columns, documents or graphs
    3. Rules can be defined in application code (outside database)
    4. Scales horizontally
    5. Unstructured, simple language that supports any kind of schema
    6. Amazon DynamoDB, MongoDB, Redis, Neo4j

### Data Store and Use Case
1. Database on EC2
    1. Need full control over instance and database
    2. 3rd party database engine (not available in RDS)
2. Amazon RDS
    1. Need traditional relational database
    2. e.g. Oracle, PostgresSQL, Microsoft SQL, MariaDB
    3. Data is well-formed and structured
3. Amazon DynamoDB
    1. NoSQL database
    2. In-memory performance
    3. High I/O needs
    4. Dynamic scaling
4. Amazon RedShift
    1. Data warehouse for large volumes of aggregated data
5. Amazon ElastiCache
    1. Fast temporary storage for small amounts of data

### Amazon Relational Database Service (Amazon RDS)
1. Amazon Relational Database Service (Amazon RDS) is a managed service that makes it easy to set up, operate and scale a relational database in the cloud.
2. Amazon RDS uses EC2 instances, so you must choose an instance family/type
3. Relational databases are known as Structured Query Language (SQL) databases
4. Amazon RDS is an Online Transaction Processing (OLTP) type of database
5. Easy to setup, highly available, fault tolerant, and scalable
6. Common use cases include online stores and banking systems
7. You can encrypt your Amazon RDS instances and snapshots at rest by enabling the encryption option for your Amazon RDS DB instance
8. Encryption uses AWS Key Management Service (Amazon KMS)

### Amazon RDS supports the following database engines
1. Microsoft SQL Server
2. Oracle
3. MySQL Server
4. PostgreSQL
5. Aurora
6. MariaDB

### Amazon RDS Facts:
1. Amazon RDS can only be scaled by increasing instance size (compute and storage)
2. Fault tolerance/disaster recovery with Multi-AZ option
3. Automatic failover for Multi-AZ option
4. Read replicas option for read heavy workloads

### Amazon DynamoDB Facts:
1. Fully managed NoSQL database service that provides fast and predictable performance with seamless scalability
2. Push button scaling means that you can scale the DB at any time without incurring downtime
3. Data is synchronously replicated across 3 facilities (AZs) in a region
4. Amazon DynamoDB global tables provide a fully managed solution for deploying a mult-region, mult-master database
5. Amazon DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for DynamoDB that delivers up to a 10x performance improvement

### Amazon Redshift Facts:
1. Amazon Redshift is a fast, fully managed data warehouse that makes it simple and cost-effective to analyze all your data using standard SQL and existing Business Intelligence (BI) tools
2. RedShift is a SQL based data warehouse used for analytics applications
3. RedShift is a relational database that is used for Online Analytics Processing (OLAP) use cases
4. RedShift is ideal for processing large amounts of data for business intelligence
5. RedShift uses Amazon EC2 instances, so you must choose an instance family/type
6. RedShift uses columnar data storage
7. RedShift always keeps 3 copies of your data
8. RedShift provides continuous/incremental backups

### ElastiCache Facts:
1. ElastiCache is a web service that makes it easy to deploy and run Memcached or Redis protocol-compliant server nodes in the cloud
2. The in-memory caching provided by ElastiCache can be used to significantly improve latency and throughput for many read-heavy application workloads or compute-intensive workloads
3. ElastiCache nodes run on Amazon EC2 instances, so you must choose your instance family/type

### ElastiCache Use Cases:
1. Web Session Store - in cases with load-balanced web servers, store web session information in Redis so if a server is lost, the session information is not lost and another web server can pick it up
2. Database Caching - use Memcached in front of AWS RDS to cache popular queries to offload work from RDS and return faster results to users
3. Leaderboards - use Redis to provide a live leaderboard for millions of users of your mobile app
4. Streaming data dashboards - provide a landing spot for streaming sensor data on the factory floor, providing live real-time dashboard displays

### 2 Types of ElastiCache Engines:
1. Memcached - simplest model, can run large nodes with multiple cores/threads, can be scaled in and out, can cache objects such as DBs
2. Redis - complex model, supports encryption, master/slave replication, cross AZ(HA), automatic failover and backup/restore

### Elastic Load Balancing (ELB) Types:
1. Application Load Balancer
    1. Instance Protocol: HTTP, HTTPS
    2. Load Balancer Protocol: HTTP, HTTPS
2. Network Load Balancer
    1. Instance Protocol: TCP, TCP_UDP
    2. Load Balancer Protocol: TCP, TLS, UDP, TCP_UDP
3. Classic Load Balancer
    1. Instance Protocol: TCP, SSL, HTTP, HTTPS
    2. Load Balancer Protocol: TCP, SSL, HTTP, HTTPS
    
### Elastic Load Balancer (ELB) - Application Load Balancer
1. Operates at the request level
2. Routes based on the content of the request (layer 7)
3. Supports path-based routing, host-based routing, query string parameter-based routing, and source IP address-based routing
4. Supports IP addresses, Lambda Functions and containers as targets

### Elastic Load Balancer (ELB) - Network Load Balancer
1. Operates at the connection level
2. Routes connections based on IP protocol data (layer 4)
3. Offers ultra high performance, low latency and TLS offloading at scale
4. Can have static IP/Elastic IP
5. Supports UDP and static IP addresses as targets

### Elastic Load Balancer (ELB) - Classic Load Balancer
1. Old generation; not recommended for new applications
2. Performs routing at layer 4 and layer 7
3. Use for existing applications running in EC2-Classic

### Elastic Load Balancer (ELB) Facts:
1. ELB automatically distributes incoming application traffic across multiple targets, such as Amazon ECS instances, containers and IP addresses
2. ELB can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones
3. ELB features high availability, automatic scaling, and robust security necessary to make your applications fault tolerant

### 3 Types of Elastic Load Balancer (ELB) on AWS:
1. Application Load Balancer (ALB) - layer 7 balancer that routes connections based on the content of the request
2. Network Load Balancer (NLB) - layer 4 load balancer that routes connections based on IP protocol data
3. Classic Load Balancer (CLB) - this is the oldest of the 3 and provides basic load balancing at both layer 4 and layer 7

### Amazon EC2 Auto Scaling
1. Amazon EC2 Auto Scaling provides horizontal scaling
2. Auto Scaling provides elasticity and scalability
3. AWS Auto Scaling automates the process of adding (scaling up) OR removing (scaling down) EC2 instances based on the traffic demand of your application
4. Auto Scaling helps to ensure that you have the correct number of EC2 instances available to handle the application load
5. You create collections of EC2 instances, called Auto Scaling Group (ASG)
6. You can specify the minimum number of instances in each ASG, and AWS Auto Scaling will ensure the group never goes beneath this size
7. You can also specify the maximum number of instances in each ASG and the group will never go above this size
8. A desired capacity can be configured and AWS Auto Scaling will ensure the group has this number of instances

### Amazon Route 53
1. Amazon Route 53 is the AWS Domain Name Service
2. Amazon Route 53 is a Global Service
3. Amazon Route 53 performs 3 main functions:
    1. Domain Registration - Amazon Route 53 allows you to register domain names
    2. Domain Name Service (DNS) - Amazon Route 53 translates name to IP addresses using a global network of authoritative DNS servers
    3. Health Checking - Amazon Route 53 sends automated requests to your application to verify that it's reachable, available and functional
4. DNS failover (automatically change domain endpoint if system fails)
5. Integrates with Amazon Elastic Load Balancer (ELB), Amazon Simple Storage Service (S3) and CloudFront as endpoints
6. Routing policies determine how Amazon Route 53 DNS responds to queries

### Amazon CloudFront
1. CloudFront is a content delivery network (CDN) that allows you to store (cache) your content at "edge locations" located around the world
2. This allows customers to access content more quickly and provides security against DDoS attacks
3. CloudFront can be used for data, videos, applications and APIs
4. CloudFront Benefits:
    1. Cache content at Edge Location for fast distribution to customers
    2. Built-in Distributed Denial of Service (DDoS) attack protection
    3. Integrates with many AWS services (S3, EC2, ELB, Route 53, Lambda)

### Amazon CloudFront - Origins and Distributions:
1. An origin is the origin of the files that the CDN will distribute
2. Origins can be either an S3 bucket, an EC2 instance, an Elastic Load Balancer, or Amazon Route 53 - can also be external (non-AWS)
3. To distribute content with CloudFront you need to create a distribution
4. There are 2 types of distribution:
    1. Web Distribution
    2. RTMP Distribution
5. CloudFront uses Edge Locations and Regional Edge Caches
    1. An edge location is the location where content is cached (separate to AWS regions/AZs)
    2. Requests are automatically routed to the nearest edge location
    3. Regional Edge Caches are located between origin web servers and global edge locations and have a larger cache
    4. Regional Edge caches aim to get content closer to users
    
### Amazon CloudWatch
1. Amazon CloudWatch is a monitoring service for AWS cloud resources and the applications you run on AWS
2. CloudWatch is for performance monitoring (CloudTrail is for auditing)
3. Used to collect and track metrics, collect and monitor log files, and set alarms
4. CloudWatch is a regional service
5. CloudWatch Alarms can be set to react to changes in your resources
6. CloudWatch Events generates events when resource states change and delivers them to targets for processing
7. CloudWatch Logs collects and centralizes logs from AWS resources
8. Any log files generated by your applications
9. Gain system-wide visibility into resource utilization

### Amazon CloudTrail
1. AWS CloudTrail is a web service that records activity made on your account and delivers log files to an Amazon S3 bucket
2. CloudTrail is for auditing (CloudWatch is for performance monitoring)
3. CloudTrail is about logging and saves a history of API calls for your AWS account
4. Provides visibility into user activity by recording actions taken on your account
5. API history enables security analysis, resource change tracking, and compliance auditing
6. Logs API calls made via:
    1. AWS Management Console
    2. AWS SDKs
    3. Command Line Tools
    4. Higher-level AWS services (such as CloudFormation)
    
### AWS CloudFormation
1. AWS CloudFormation provides a common language for you to describe and provision all the infrastructure resources in your cloud environment
2. CloudFormation can be used to provision a broad range of AWS resources
3. Think of CloudFormation as deploying infrastructure as code
4. Elastic Beanstalk is more focused on deploying applications on EC2 (PaaS)

### AWS Elastic Beanstalk
1. AWS Elastic Beanstalk can be used to quickly deploy and manage applications in the AWS Cloud
2. Developers upload applications and Elastic Beanstalk handles the deployment details of capacity provisioning, load balancing, auto-scaling, and application health monitoring
3. Considered as a Platform as a Service (PaaS) solution

### CloudFormation Facts:
1. Template-driven provisioning
2. Deploys infrastructure using code
3. Uses JSON or YAML template files
4. CloudFormation can deploy Elastic Beanstalk enrollments
5. Similar to Terraform

### Elastic Beanstalk Facts:
1. Web apps made easy
2. Deploys applications on EC2 (PaaS)
3. Deploys web applications based on Java, .NET, PHP, Node, Python, Ruby, Go and Docker
4. Uses ZIP or WAR files or Git
5. Elastic Beanstalk cannot deploy using CloudFormation
6. Similar to Google App Engine

### AWS Pricing Facts:
1. What you get for free vs. what you are charged forCloudFormation

    

