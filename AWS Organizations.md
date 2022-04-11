---
updated: '2021-01-06'
cards-deck: AWS::Organizations

---

# AWS Organizations

Multi-account management

## Features

- #Global Service
- Allows to manage multiply AWS Accounts
- Main account cannot be changed
- Consolidated billing across all accounts i.e single payment method
- Pricing benefits from aggregated usage
- Has API to create child accounts
- [Strategies][1]
    - Business Unit
    - Environmental Lifecycle
    - Project Based
    - 

## Security

## Notes

## Questions / Flashcards

- To what level are the Service Control Policies applied?:: They are applied at the OU and account level
^1611408332885
- What users are affected by the Service Control Policies?:: SCP is applied to Users, Roles, including Root user, of the account, but it does not affects service-linked roles 
^1611408332890
- Can an AWS account belong to more than one organization?:: No, AWS accounts can only belong to a single organization, and be moved in between them
^1611407676369
- How can I restrict access to certain AWS services?:: You can use service control policies to prevent actions on the child organization accounts
^1611408222609

[1]: https://aws.amazon.com/blogs/mt/best-practices-for-organizational-units-with-aws-organizations/?org_product_gs_bp_OUBlog
