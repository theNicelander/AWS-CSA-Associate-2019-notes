# Applications

## SQS
> A way to de-couple your infrastructure. 
**Pull based**, distributed web-based message queue that can be used to store messages (256kb) while waiting for a component to process them. 
This acts as a buffer for up to 14 days, resolving issues if one component is faster than the other. 
Standard guarantees a message will be delivered **at least once**, sometimes more often (increase visibility timeout if happens). FIFO preserves the order, delivers **only once.**
* Queue messages that one component generates, to be consumed by another component, allowing them to run independently
* 256kb max per message, stays in the queue for 1minute to 14 days  
* A queue is a temporary repository for messages that are awaiting process 
* acts as a buffer, resolving issues if one component is faster than another 
* Types:
    * **Standard queue**: Nearly unlimited no. transactions per second. Message will be delivered **at least** once, sometimes more often and out of order. Generally only once though. No promise though.
    * **FIFO** (First-In-First-Out): Order strictly preserved until consumer processes and deletes a message. 300 messages per second
* **Visibility timeout**: amount time that a message is invisible to SQS after it's been read. If the job isn't processed and deleted within that time, the message's available again and so could be delivered twice
    * Max 12 hours
* **Short polling** always responds (can be empty)
* **Long polling** only responds if there's a message in the queue

## SWF - Simple Work Flow
> Task oriented API allowing for a way to coordinate work across distributed applications. Each task is assigned only once, no duplicates.  Could be used with human interactions. Starters / Deciders / Workers. 
* Tasks represent invocations of processing steps. 

## SNS - Simple notification service
> **Push-based** web-based instant notifications to mobile, text, http. Group recipients using topics. 

## Elastic transCoder
> Convert media from one format into another able to play on all devices. 
Pay by minute & resolution

## API Gateway 
> "Front-door to AWS". Call AWS resources through a cheap, autoScaling API. Results can be cached (cost-- && performance++). For multiple domains enable CORS.
* Define API and resources. For each resource, set HTTP methods, security and target. 
* Deploy to stage (default or custom domain)
* Can cache responses so doesn't have to query hardware for the response each team. 
* **Same origin policy**. Allow one page to access the data of another, but only if they have the same domain name. Done to prevent cross-site scripting. 
* **CORS** allows getting data from another webpage
    * ERROR: "Origin policy cannot be read at the remote resource" -- enable CORS on API gateway 
## Kinesis
> Platform to send streaming data to. 
Kinesis stream stores data in shards for 24h to 7 days. 
Kinesis FireHose doesn't store data.
Kinesis analytics for analysing stream data
* **Streaming data** is data generated continuously (tweets, purchases, stocks)
* Analyse data and build 
* **Kinesis stream**
    * Store streaming data for 24h - 7 days in "**Shards**". 
    * Consumers (eg. EC2 instance) can then analyse, process and store those shards somewhere else. 
    * Read: 5 transactions/sec && Max 2MB/sec
    * Write: 1000 transactions/sec && 1MB/sec 
* **Kinesis FireHose**
    * No storage, process data immediately and output it somewhere.
* **Kinesis analytics**
    * Analyse data in Kinesis stream/FireHose

## Web Identity Federation & Cognito
> AWS Cognito is a Web Identity Federation service. Sign-up and sign-in to your apps using Facebook/AWS/Google. Handles interactions between applications using SNS. User pool handles users: Registrations/auth/recovery. Identity Pool actually grants access to resources. 
* Web Identity Federation can give users access to AWS resources after logging in with providers like Amazon, Facebook & Google. 
    * Success = temp AWS security credentials
* **User Pools**: USERS. Directories to manage sing-up/in functions for mobile and web. Acts as an identity provider.
* **Identify pools**: Temp credentials to access AWS resources in form of IAM role
* Push synchronization across multiple devices when a change is made
* **Process in background**:  
    * User signs into Facebook
    * Facebook sends response to Cognito, which converts it to a JWT token (User Pool) 
    * Send token to Identity pool which grants AWS credentials (IAM role)
    * Can now access AWS resources 