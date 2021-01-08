---
updated: '2020-12-30'
cards-deck: AWS::Networking & Content Delivery::Direct Connect

---

# Direct Connect

## Features

- Allows you to create private connections (without using internet) to increase bandwidth throughput, improve network consistency (for real time applications), or hybrid environments (cloud + on premise) using AWS Direct Connect
- You can connect multiple [[VPC]]s to a customer network using Direct Connect Gateway and Private Virtual Interface

## Security

## Notes

## Questions / Flashcards

- Can I use a Direct Connect Gateway to route traffic between [[VPC]]s?:: No, Direct Connect Gateways don't route network traffic in between [[VPC]]s only to Customer Network, for that case you need VPC Peering
^1609763777673
- Can I connect different regions and accounts in a Direct Connect Gateway?:: No, you can connect different regions to a customer datacenter, but not different accounts
^1609763777678
- How many types of Direct Connect connection types are?:: There are two types of connection types in Direct Connect: Dedicated Connections (physical dedicated ethernet port on request with 1Gbps or 10Gbps), or Hosted Connections (handled by Direct Connect partners from 50Mbps to 10Gbps)
^1609763777683
- Is traffic encrypted in a Direct Connect connection?:: No, traffic is only private, if you require encryption you need to setup an VPN between the Direct Connect partners and your customer network
^1609763777697
