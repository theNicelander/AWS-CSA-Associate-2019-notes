`2019 AWS CSA - Associate notes`
==============================

# HA architecture
## Elastic Beanstalk
> Quickly deploy and manage applications in the AWS Cloud without worrying about the infrastructure that runs those applications.
* Simply upload your app, and EB automatically handle the details of capacity provisioning, load balancing, scaling and application health monitoring.
## CloudFormation
> Completely script your cloud environment
* Quick starts a bunch of templates already built by AWS Solutions Architects 
## Load balancing
* Types of load balancers
    * **Application**: Layer 7 aware, use in production
    * **Network**: Tesla, Extreme performance
    * **Classic**: Simple, keep costs down
    * **Elastic**: Automatically distributes incoming application traffic across multiple targets
* Have their own DNS name, not IP address. 
    * X-forwarded-for to get public IP 
* Reported as InService / OutofService -- Health checks check the instance health
* Sticky sessions allows a user to stick to the same instance - Useful if the instance stores data on that user in the session.
* Cross Zone for cross AZ load balancing
## Other
* Read replicas
* 504 error - Gateway timed out
* **Availability**: % chance the is likely to be operational
* **Reliability**: How often a system fails (mean time)
* **Resilience**: Ability to recover from problems
* **Durability**: 