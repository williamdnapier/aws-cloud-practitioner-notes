# [AWS Certified Cloud Practitioner Exam](https://aws.amazon.com/certification/certified-cloud-practitioner/)

## Brief Notes for AWS CPP

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
    2. Increase relability (predictible performance)
    3. Increase bandwidth (predicible bandwidth)
    4. Decrease latency
5. Direct connect is charged by the port hours and data transferred
6. Available in 1Gbps and 10Gbps
7. Or, if you choose an AWS Direct Connect Partner, you can choose speeds of 50Mbps, 100Mbps, 200Mbps, 300Mbps, 400Mbps, 500Mbps

### Databases - Relational vs Non-Relational
1. Relational
    1. Organized by tables, rows and columns
    2. Rigid schema (SQL)
    3. Rules enforced within a database
    4. Typically scaled vertically
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
7. 

