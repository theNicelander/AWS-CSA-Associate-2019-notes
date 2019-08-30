`2019 AWS CSA - Associate notes`
==============================

## VPC
> Logical data centre within AWS, in a given Region (5 per region)

## Subnets
> Logical division of the VPC
* Can have multiple Subnets in an AZ, but a subnet cannot strech across AZs
## Route tables
> Rules where network traffic is directed
* Internet Gateway
    * VPC component that allows communication between instances in a VPC and the internet
* Internet/NAT gateways
    * Attaching an IGW to a VPC allows instances with public IPs to access the internet, while NATs allow instances with no public IPs to access the internet
    * Instances in a VPC with an **Internet Gateway** need a public IP to connect to the internet
    * Instances in a VPC with a **NAT Gateway** DONT need a public IP to connect to the internet
* Network access control lists (Network ACL) - Stateless
    * Default ACL allows inbound & outbound, 
    * newly created denies inbound & outbound
    * can block IP addresses
    * ACL can be associated with multiple subnets, each subnet can only be associated with one ACL
* NAT instance / Gateways
    * USed to provide internet traffic to EC2 instances in private subnets
    * Instance must be in a public subnet, behind a security group
    * Instance must be a route out of the private subnet to the NAT instance
    * Having one gateway means you don't have high availability
* Security groups - Stateful
    * Can't span VPCs, only on instance level
    * Allow rules only, evaluate all rules before allowing traffic
* Bastions
    * Securely administer EC2 instance (SSH/RDP)
    * Can't use NAT Gateways as a Bastion Host, only instances
* VPC endpoints
    * Privately connect VPC to AWS, so traffic never leaves the AWS network
* NAT vs BASTION
    * NAT: general traffic
    * Bastion: admin 
* Application load balancer 
    * must be deployed into at least 2 subnets