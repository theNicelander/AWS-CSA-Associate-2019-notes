# Applications

## Lambda
> Very cheap, global compute service where you can upload your code and create lambda functions. AWS runs your code and takes care of the underlying hardware. 1 event = 1 function -- Scales horizontally.  AWS X-ray to debug. 
* Examples
    * Event driven: AWS runs your code in response to event (upload file S3, update table DynamoDB). 
    * Compute in response to HTTP request using API Gateway or AWS calls. 
* API Gateway serves your request
* Price
    * Number of Requests: 1 million requests are free. $0.20 per 1 million requests
    * Duration: Rounded to the nearest 100ms, $1.667E-05 per GB-second 

