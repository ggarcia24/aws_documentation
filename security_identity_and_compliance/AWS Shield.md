---
updated: '2020-12-29'
cards-deck: AWS::Security, Identity, & Compliance::AWS Shield

---

# AWS Shield


## Features

- Standard
    - Activated by default
    - Protection from
        - SYN/UDP Floods
        - Reflection Attacks
        - Other Layer 3/4 attacks
- Advanced
    - Optional service
    - 24/7 access to a response team
    - Protection from
        - Sophisticated DDoS attacks
            - [[EC2]]
            - [[EC2#Elastic Load Balancers]]
            - [[CloudFront]]
            - [[Global Accelerator]]
            - [[Route 53]]
        - Higher fees during usage spikes during DDoS
- Integrates into [[AWS WAF]]

## Security

## Notes

## Questions / Flashcards

- How can I mitigate mitigate DDoS attacks in a [[VPC]]?:: You can use AWS Shield Advance to detect and mitigate DDoS attacks.
^1609855699723
