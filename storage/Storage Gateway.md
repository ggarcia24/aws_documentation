---
updated: '2021-01-06'
cards-deck: AWS::Storage::Storage Gateway

---

# Storage Gateway

## Features

- Bridge on-premise to [[S3]] buckets
- Support through virtualization or hardware appliance
- Storage Types
    - File Gateway
        - S3 buckets accessible through NFS/SMB
        - most recent data is cached
        - Can be mounted on many servers
    - Volume Gateway
        - 2 Types
            - Cached volumes: low latency to most recent data
            - Stored volumes: entire data is on-premise, scheduled backups to [[S3]]
        - S3 buckets accessible through iSCSI
        - point-in-time EBS snapshots
    - Tape Gateway
        - Virtual Tape library backed by [[S3]] and Glacier
        - Works with existing tape-based processes and vendors (iSCSI interface) 

## Security

## Notes

## Questions / Flashcards
