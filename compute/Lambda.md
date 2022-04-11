---
updated: '2021-01-04'
cards-deck: AWS::Compute::Lambda

---

# Lambda

## Features

- Pay per request and compute time
- Max 3Gb of RAM
- Integrated with
    - [[API Gateway]]
    - [[Kinesis]]
    - [[DynamoDB]]
    - [[S3]]
    - [[CloudFront]]
    - [[CloudWatch]] Events
    - [[SNS]]
    - [[SQS]]
    - [[Cognito]]
- #Logging and #Monitoring through [[CloudWatch]]
- CPU and Network performance increase with RAM
- Language Support
    - Javascript (Node.js)
    - Python
    - Java
    - C# (.NET Core / Powershell)
    - Golang
    - Ruby
    - Custom Runtime (community supported: i.e Rust)
- #Serverless
- Lambda@Edge
    - Change [[CloudFront]] requests and responses
    - Viewer Request: [[CloudFront]] receives a request
    - Origin Request: [[CloudFront]] forwards a request
    - Origin Response: [[CloudFront]] get response from origin
    - Viewer Response: [[CloudFront]] forwards response to viewer

## Security

## Notes

## Questions / Flashcards

- What's the max execution time of a Lambda function?:: 900 seconds or 15 minutes
^1610800305880
- What's the max memory allocation of a Lambda function?:: 3008Mb, min 128Mb
^1610800305890
- What's the default concurrent execution of Lambda?:: 1000 but it can be increased with a request 
^1610800305895

