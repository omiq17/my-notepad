---
layout: default
title: AWS VPC
parent: AWS
---

## AWS VPC

### Virtual Private Cloud

Region-> VPC -> 1/M AZ -> 1 Public and 1 Private Subnet.

**Public Subnet** -> Connected to web via IGW. 

**Private Subnet** -> Connected to Public Subnet via NAT Gateway (AWS Managed). Then it can access internet.


AWS Services are by default access over Public Subnet.
If deployed any application in the VPC Private Subnet, it may not have internet access. So it uses a Private Link (e.g. Bedrock VPC endpoint or S3 Gateway endpoint) that establishes connection between our application and required AWS services (like Bedrock).
