# [AWS Certified Cloud Practitioner Exam](https://aws.amazon.com/certification/certified-cloud-practitioner/)

## The AWS Certified Cloud Practitioner examination is intended for individuals who have the knowledge and skills necessary to effectively demonstrate an overall understanding of the AWS Cloud, independent of specific technical roles addressed by other AWS Certifications. The exam can be taken at a testing center or from the comfort and convenience of a home or office location as an online proctored exam.

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







































































































































