---
updated: '2021-01-04'
cards-deck: AWS::Networking & Content Delivery::CloudFront

---

# CloudFront

Content delivery network

Reference:
- https://aws.amazon.com/cloudfront/features/

## Features

- Uses catching at EDGE locations to improve read performance
- Origin
    - [[S3]] bucket
        - Enhance security with Origin Access Identity (S3 read-only by CloudFront)
        - Can be used to upload files to bucket
    - Custom Origin
        - Application Load Balancer
        - [[EC2]] Instance
        - [[S3]] Website
        - Anything that supports HTTP
- Distributes files and caches them at the edge (S3)
- Can use [[IAM]] to enhance security by using Origin Access Identity to allow the 

## Security

- Can White/Blacklist access based on geographic distribution
- Has DDoS protection
- Integrates with [[Web Application Firewall]]
- Can expose external HTTPS certificates
- Can use HTTPS internally
- There's a list of the IPs of Edge Locations

## Notes

## Questions / Flashcards
