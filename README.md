# [AWS Certified Cloud Practitioner Exam](https://aws.amazon.com/certification/certified-cloud-practitioner/)

## Brief Notes for AWS CPP

## Section 3: Cloud Computing and AWS

### Legacy IT
In Legacy IT, you had a corporate data center which contained it's own servers, storage servers, routers, switches, firewalls and backup systems. A company would either lease this space (co-location) or might own the entire building. Regardless if the company owns the building or not, they do own the equipment in this model. This model is very capital intensive -- you have to purchase all this equipment prior to operation. The company's corporate office is connected into this datacenter and the IT staff would have to design, build, operate and manage equipment. So, this leads to alot of cost. These costs include: data center building, data center security, physical IT hardware, software licensing costs, maintenance contracts, power, internet connectivity, staff wages (design, build, operations and maintenance).

### Examples of Cloud Computing
Some examples of cloud computing include: Gmail, Salesforce, Dropbox, AWS. So, what defines a cloud service? Well, the service can be described with the following terms: on-demand, self-service, broad network access (provided by internet access), with resources pooling. Resource pooling means that the provider is able to leverage a large number of compute resources to share for the actual delivery of the service. These services are known to have rapid elasticty. Rapid elasticity means that your services can grow very quickly as demand goes up and also shrink very quickly as demand decreases for those services. With cloud computing you typically are paying on a pay-per-use basis -- depending on your contract you usually would be using a pay as you go model.

### Cloud vs Traditional IT
Cloud Computing: on-demand, self-service, with broad network access, resource pooling (always enough capacity to meet your needs), rapid elasticity, measured service.

Traditional IT: requires human involvement, with internal network access and limited public presence (have to setup a remote way to access the resources), single-tenant hardware (can be virtualized) - only your company using the hardware, limited in terms of scaling, usage not typically measured and not charged back to the department responsible for application.

### Examples of Cloud Computing

| Non-Cloud Services | Cloud Services |
| ------------------ | -------------- |
| Email server       | Gmail          |
| File server        | Dropbox        |
| CRM (Customer Relationship Manager) | Salesforce       |

With cloud services you don't own or manage the infrastructure on which the service runs. Cloud services are offered on a subscription / consumption model. The service will scale as demand changes.

### Example of Deploying a Website On-Premise (Traditional IT Model)
1. Purchase hardware (4-12 weeks)
2. Install and build (4-8 weeks)
3. UAT (2-4 weeks)
4. Handover to Operations (1-2 weeks)
Total Time: 3-6 months

### Example of Deploying a Website in the Cloud
1. Admin uses browser to deploy website to AWS Cloud

Much faster because you don't have to purchase and install servers. This can be faster and much cheaper because you don't have the same sort of capital expenses -- you are only paying for on-demand (aka what is used).

### Cloud Service Models
1. Private cloud - is a cloud environment owned and managed by you. It includes the servers, hypervisors, applications in the stack. It can have self-service, multi-tenancy, metering and elasticity but it is managed by you. It is much easier to use public cloud services like AWS than to try to do this yourself. A private cloud is like owning a home where you are responsible for taking care of everything.

2. Infrastructure as a Service (IaaS) - you manage the VM, the OS running on the VM and the applications which run on the VM. Some examples of IaaS include: Amazon Elastic Compute Cloud (EC2), Azure Virtual Machines, Google Compute Engine. IaaS is different than home ownership (aka private cloud). It is more like renting a room or rooms at a hotel. You get the structure that you need for only the time which it is needed but you have to see to it once in the room.

3. Platform as a Service (PaaS) - you only manage the applications and databases on the VM. In this model you are only uploading data and managing code. You don't have to worry about anything else in this model. Examples: AWS Elastic Beanstalk, Azure WebApps and Google Compute App Engine.

4. Software as a Service (SaaS) - you don't manage anything, you only use the software. Examples: Salesforce, Google Apps, Zoom, etc.

### Cloud Delivery Models
1. Private Cloud - you build your own infrastructure including: virtualization cluster, storage & backup, network and firewall. Then, you layer on top of this your self-service portal, automation and configuration management, billing and reporting and multi-tenancy controller. This private cloud is not shared with any other company, so it is called single tenancy. Benefits include: complete control of the entire stack, security - in some cases organizations have to keep all of their applications in-house due to compliance reasons. Examples of private clouds include: VMware, Microsoft, RedHat and OpenStack.

2. Public Cloud - you are connected from Corporate Office to AWS Cloud via the Internet or a Private Link. Public cloud services in AWS Cloud would include compute, storage, network and database. Benefits: variable expenses (instead of capital expense), economies of scale, massive elasticity. Examples: AWS, Microsoft Azure, Google Cloud Platform.

3. Hybrid Cloud - Private Cloud connected to Public Cloud via the Internet or a Private Link. Benefits: allows companies to keep the critical applications and sensitive data in a traditional data center environment or private cloud, take advantage of public cloud resources like SaaS (latest applications) and IaaS (elastic virtual resources), facilitates portability of data, apps and services and more choices for deployment models. So, you can fail over in the cloud or burst into the cloud when needed using this model.

4. Multicloud - this is where you are taking advantage of multiple cloud providers (AWS, Azure, VMware, OpenStack). So, you are getting the best of each of these providers. This allows you to put your applications where they are best suited. 

### Overview of AWS
Amazon recognized different amount of infrastructure was required at different times in the year. During the Christmas season there is an increased demand for infrastructure whereas during mid-February that infrastructure was just sitting there idle. AWS solves this problem for their customers. AWS attributes: a subsidiary of Amazon, a hyperscale public cloud provider, services are offered on-demand, 25 regions around the world, charge for services based on usage.

AWS Service Categories include machine learning, media services, networking, end user computing, internet of things, analytics, database, storage and compute services. There are many categories and more than 200 services.

AWS charges based on (3) things:
1. Compute - amount of resources such as CPU, RAM and duration
2. Storage - quantity of data stored
3. Outbound Data Transfer - quantity of data that is transferred out from all services

### AWS Cloud Overview Summary
1. AWS Region is a geographical area
2. Each region consists of 2 or more Availability Zones (AZs)
3. Each region is designed to be completely isolated from the other regions
4. Availability Zones are locations into which you launch resources
5. Availability Zones are physically separated and isolated from each other
6. Availability Zones span 1 or more data centers. They have direct, low-latency, high throughput and redundant retwork connections between each other.
7. Each Availability Zone is designed to be an independent failure zone
8. Availability Zones are physically separated within a typical metro region and use different power sources

### AWS Global Infrastructure
The AWS Global Infrastructure is comprised of the 25 regions and contained availability zones. A region is a physical location in the world and is independent. Every region is connected via a high bandwidth, fully redundant network. There are 25 regions around the world. Each region consists of 2 or more availability zones. An availability zone is composed of one or more data centers. Between the region and the user is the AWS Local Zone. A local zone extend regions closer to end users.

Deploying services globally - with the AWS Management Console you can launch virtal servers (instances) and databases globally.

### 6 Advantages of Cloud Computing
1. Trade capital expense (CAPEX) for variable expense (OPEX)
2. Benefit from massive economies of scale
3. Stop guessing capacity
4. Increase speed and agility
5. Stop spending money on running and maintaining data centers
6. Go global in minutes

## Section 4: Identity and Access Management (AWS IAM)

### IAM Summary
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources. You use it to control who is authenticated (signed in) and who is authorized (has permissions) to use resources.

Users are the individual accounts which a human logs in with. Users have NO PERMISSIONS by default. Groups are used for organizing users and applying policies to users in those groups. Policies are JSOn documents used for defining permissions which are applied to groups. Roles are used as delegates and are used, as needed, by services.

Users log into the AWS Management Console with a username and password. While access keys are used for CLI and API programmatic use. Access keys consist of an access key ID and a secret access key. The Root User is the use that created the AWS account. Root users have full permissions and cannot be restricted.

Multi-factor authentication (MFA) uses something only you know (password) with something you have (physical device or virtual pin) and should be applied to all users.

Service Control Policies (SCPs) are a feature of AWS Organizations. Service Control Policies control the maximum available permissions in an AWS account. SCPs do NOT actually grant permissions but rather they just define what is allowed.

### IAM Best Practices
1. Lock away your AWS account root user access keys
2. Create individual IAM users (do not share accounts between users)
3. Use groups to assign permissions to IAM users
4. Grant the least privilege possible for users to do their job
5. Get started using permissions with AWS managed policies (use these if inexperienced writing policies)
6. Use custom managed policies (apply to groups or roles) instead of inline policies (apply direcly to individual user)
7. Use access levels to review IAM permissions (This means constantly review the permissions assigned to users. Ensure they only have those permissions needed to do their job.)
8. Configure a strong password policy for your users (Upper, lower cases, digits, special characters, length, etc.)
9. Enable MFA
10. Use roles for applications that run on Amazon EC2 instances (don't put access keys in code)
11. Use roles to delegate permissions
12. Do NOT share access keys
13. Rotate credentials regularly (i.e. weekly, monthly, quarterly, etc. - done with password policy)
14. Remove unneeded credentials (remove old user accounts, access keys, etc.)
15. Use policy conditions for extra security (for example, restrict to certain IP addresses, etc.)
16. Monitor activity in your AWS account - watch for anything suspicious

## Section 5: AWS Compute Services

### AWS Compute Services Summary
Amazon Elastic Cloud Computing (EC2) is a web service with which you can run virtual servers (instances) in the cloud. These EC2 instances can run the Windows, Linux or MacOS operating systems. An Amazon Machine Image (AMI) is used to launch an EC2 instance which consists of an EB2 snapshot, permissions and configuration.

Amazon EC2 Metadata and User Data - user data is data that is supplied by the user at instance launch in the form of a script. Whereas instance metadata is data about your instance that you can use to configure or manage the running instance. User data and metadata are NOT encrypted. You can find metadata about the instance at http://169.254.169.254/latest/meta-data and do curl requests to get information about this metadata.

Access keys can be used on EC2 instances to gain permissions to other AWS Services. Remember, these are credentials which are associated with your account and can be used to authenticate with. They are actually stored in plain text on the hard drive of the EC2 instance ... so, they are NOT secure and should NOT be used if possible. It is better to delegate a role to the EC2 instance for work it needs to do rather than access keys because of this security concern.

AWS Batch is a service which enables developers to easily run thousands of batch computing jobs on AWS. It can use a large amount of processing power and AWS Batch will coordinate all the services necessary to run these scripts. AWS Batch dynamically provisions the optimal quantity and type of compute resources.

Amazon Lightsail is a service for less technical users. It does not require deep technical knowledge of AWS to provision compute services. Amazon Lightsail provides compute, storage and networking capacity to deploy and manage websites, web applications and databases in the cloud. Best suited to smaller projects which only require maybe a dozen or less instances. It is lower cost than EC2 but you do not get the same features as EC2 in terms of scalability and level of control. Provides a simple UI and is ideal for blogs, simple websites and web applications (e-commerce web sites). You can deploy load balancers and attach block storage to Amazon Lightsail instances.

Amazon Elastic Container Service (ECS) is used to run containers in the cloud. In ECS, containers are called tasks. ECS Tasks are defined by Task Definitions.
There are (2) ECS Launch Types: 
1. EC2 Launch Type - in this type you manage the EC2 instances which are the hosts for ECS tasks running inside of the ECS cluster
2. Fargate Launch Type - in this type, AWS manages the underlying compute, cluster and scaling

Amazon ECS Registry (ECR) is a private container registry where you can keep your images for your Docker containers. 


## Section 6: AWS Storage Services Summary

### Amazon Elastic Block Store (EBS) Facts
An EBS volume data persists independently of the life of the instance. EBS volumes do not need to be attached to an instance. You can attach multiple EBS volumes to 1 EC2 instance. There is also a mult-attach option to attach a volume to multiple instances but with some constraints. EBS volumes must be in the same Availability Zone (AZ) which they are attached to. Root EBS volumes are deleted on termination by default. Whereas extra non-boot volumes are not deleted on termination by default. Snapshots capture a point-in-time state of an instance. Snapshots are stored on S3. If you make periodic snapshots of a volume, the snapshots are incremental. While EBS volumes are AZ-specific, snapshots are region-specific because they are stored on Amazon S3.

Data Lifecycle Manager (DLM) - automates the creation, retention and deletion of EBS snapshots and EBS-backed AMIs (Amazon Machine Images). DLM helps with the following: it protects valuable data by enforcing a regular backup schedule, it can create standardized AMIs that can be refreshed at regular intervals, it can also be used to retain backups as required by auditors or for internal compliance reasons. DLM can reduce storage costs by deleting outdated backups. You can use DLM to create a Diaster Recovery (DR) backup policy that backs up data to isolated accounts.

Instance Store Volumes - are high performance local disks that are physically attached to to the host computer on which an EC2 instance runs. Instance stores are ephemeral which means the data is lost when powered off (non-persistent). They are ideal for temporary storage of information that changes frequently (buffers, caches or scratch data).

### Amazon Elastic File System (EFS) Facts
Amazon Elastic File System (EFS) is a file-based storage system. It uses the NFS protocol so is only for Linux (no Windows). You can connect many EC2 instances concurrently to 1 EFS. You can connect to EFS from other VPCs.