Subnets are what services run from, and add structure to your VPC

This is our current structure with a bare VPC shell:
![[Pasted image 20250122115722.webp]]

Subnets are:
- Subnets are **private** by default
- these are AZ resilient and are contained within a single AZ **always** (1 subnet is always in 1 AZ, though there can be many subnets within an AZ)
- the CIDR used is within the VPC CIDR and **must not overlap with other subnets**
- by default, subnets can communicate with every other subnet in the VPC (the VPC isolation is at the perimeter)

5 IP address are always reserved:
- starting address of the subnet is the  `network`  address
- `network + 1` is the VPC router
- `network + 2` DNS
- `network + 3` Reserved future use
- last address is the `broadcast address`

configuration options that are assigned at a subnet level:
- The DHCP config settings on the VPC flow through to the subnet
- whether a public IPv4 (and optionally IPv6) address is assigned
