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
