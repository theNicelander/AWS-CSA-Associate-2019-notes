# 2019 AWS CSA - Associate notes
> **THIS IS A WORK IN PROGRESS AS I'VE NOTE SAT THE EXAM YET**

Notes from doing the [A Cloud Guru course](acloud.guru) for the [AWS Certified Solutions Architect – Associate ](https://aws.amazon.com/certification/certified-solutions-architect-associate/) exam.

High level overview & index below  with detailed notes separate.

## To-be-organised
> Amazon Macie: ML powered security for S3 buckets. Protecting sensitive data. 

## 1. Intro 
## 2. IAM
#### VPC Flow Logs
> Capture information about IP traffic coming to and from network interfaces. Can write to S3 or Cloudwatch. Can we set on VPCs, subnet or network interfaces. 

#### AWS WAF - Web application firewall
> Control traffic by creating custom web security rules. Block common attacks like SQL injection or cross site scripting. Pay for use.
* Types: IP Match, Geo Match, String Match, SQL injection Match
* Optional: Regex match



## 3. S3s
## 4. EC2
## 5. Databases
> [Full Notes](05-Databases.md)

* Open Source: Aurora, MySQL, MariaDB or PostgreSQL
* Proprietary: SQL Server (MS), Oracle 

## 6. Route53
## 7. VPC
> [Full Notes](07-VPC.md)
#### VPC
> **Logical data centre within AWS**, in a given Region (max 5 per region). Can select your own IP address ranges, subnets, configure route tables between subnets and setup internet gateways. 
* You always launch instances into a VPC. 
* **Internet Gateways** enable communications to the internet, if instance has public IP
* **Route table**
* **NACL** - Network Access Control Lists are stateless: Allow and deny connections. 
** 
* **NAT gateways** allow communications to the internet, if instance only has private IP
* **Bastions** EC2 instance in public subnet you can connect to via SSH, to administer an instance in the private subnet
* **VPC Peering** enable connecting on VPC to another. No transitive peering. 

* **Hardware Virtual Private Network** can extend your corporate datacentre into AWS

## 8. HA Architecture
> [Full Notes](08-HA-Architecture.md)
#### Elastic Beanstalk
Quickly deploy and manage applications in AWS without worrying about the infrastructure that runs those applications. Handles provisioning, load balancing, scaling and monitoring.

#### CloudFormation
Completely script your cloud environment. Templates available from AWS Solutions Architects.

#### Types of load balancers
* **Application**: Layer 7 aware, use in production
* **Network**: Tesla, Extreme performance
* **Classic**: Simple, keep costs down
* **Elastic**: Automatically distributes incoming application traffic across multiple targets

#### Terminology 
* **Availability**: % chance the is likely to be operational
* **Reliability**: How often a system fails (mean time)
* **Resilience**: Ability to recover from problems
* **Durability**: Likelihood to disappear 



## 9. Applications
> [Full Notes](09-Applications.md)

## SQS
 **Pull based**, distributed web-based message queue that stores messages (max 256kb) while waiting for a component to process them. This acts as a buffer for up to 14 days, decoupling your components and resolving issues if one is faster than the other. 
* Standard SQS guarantees a message will be delivered **at least** once
* FIFO preserves the order, delivers **only** once

#### SWF - Simple Work Flow
Task oriented API to coordinate work across distributed applications. Each task is assigned only once with no duplicates. Could be used with human interactions, such as Amazon factory workers. 
* Starters / Deciders / Workers. 

#### SNS - Simple notification service
**Push-based** web-based instant notifications to mobile, text, http. Group recipients using topics. 

#### Elastic trans coder
Convert media from one format into another able to play on all devices. Pay by minute & resolution.

#### API Gateway 
"*Front-door to AWS*". Call AWS resources through a cheap, auto-scaling API. Results can be cached (cost-- && performance++). For multiple domains enable CORS.

#### Kinesis
Platform to send streaming data to. 
* **Kinesis Stream** stores data in shards for 24h to 7 days. 
* **Kinesis FireHose** doesn't store data. 
* **Kinesis Analytics** analyses stream data

#### Cognito
AWS Cognito is a **Web Identity Federation service**. Sign-up and sign-in to apps using Facebook/AWS/Google. Handles interactions between applications using SNS. 
* **User pool** handles users: Registrations/auth/recovery. 
* **Identity Pool** grants access to resources using info from User Pool. 

## 10. Serverless
> [Full Notes](10-Serverless.md)
#### Lambda
Very cheap (no. request + duration), global compute service where you can upload your code and create lambda functions.  AWS runs your code and takes care of the underlying hardware. AWS X-ray for debugging.
* 1 event = 1 function = scales horizontally. 



