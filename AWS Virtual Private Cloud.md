VPCs are **a virtual network** within your AWS account

Each VPC is within **1 account and 1 region** and they operate across **multiple AZs** and are thus **regionally resilient** via their subnets

by default they are **private and isolated** (services within can communicate with each other, but nothing goes in or out unless configured otherwise)

TWO types:
- Default VPC, of which you can have **only one per region** - These come pre-configured by AWS and are a lot less flexible, but will be **predictablely configured**
- Custom VPCs are unlimited and can (and must) be configured however you like, in detail, meaning they are very flexible and will be used in virtually every solution

All VPCs will have an IP address range which is the **VPC CIDR**
- the **default VPC CIDR** is always  172.31.0.0/16

VPC's will be divided internally into subnets using a subset of their IP address range (default will always be all three subnets available)

##### DEFAULT VPC NOTES

Always 1 or 0 per region (you can delete the one that exists initially)
- however, some services do **assume the default VPC exists** so generally good to leave it

- the structure is always the same and predictable
	- **VPC CIDR** is always  172.31.0.0/16
	- subnets are always all 3 AZs etc
	- Internet Gateway, Security Group, and Network ACL all exist and are pre-configured 
	- Services deployed into this VPC will be assigned a public IPv4 address
