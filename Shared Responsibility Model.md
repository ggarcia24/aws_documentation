---
updated: '2020-12-29'
cards-deck: AWS::Shared Responsibility Model

---

# Shared Responsibility Model

![asdasd](https://d1.awsstatic.com/security-center/Shared_Responsibility_Model_V2.59d1eccec334b366627e9295b304202faf7b899b.jpg)

Reference:
    - [https://aws.amazon.com/compliance/shared-responsibility-model/]


![[Pasted image 20211108135152.png]]

https://www.youtube.com/watch?v=Rwptm1zKXx8

https://www.youtube.com/watch?v=Rwptm1zKXx8


## AWS responsibility

- Cloud security
    - Underlying infrastructure operations
        - Hardware
        - Firmware
        - Virtualization Software
        - Facilities
        - Networking
    - Managed Services
        - [[S3]]
        - [[DynamoDB]]
        - [[RDS]]
        - etc.
        
## Customer Responsibility

- Instance Security
    - Guest OS
    - Firewall
    - Network configuration / Security groups
    - [[IAM]]
    - Encryption
    - Security Configuration within the running software
        - i.e user public database access