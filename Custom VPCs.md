VPCs are a regionally isolated network that operates within all AZ's of the region
- By default nothing goes IN or OUT without explicit configuration

When you create a VPC you need to be careful whether you are picking **default** or **dedicated tenancy** 
- be careful here, if you pick dedicated, all services within will also be dedicated (at a cost premium)

VPCs when created:
- gets 1 primary private CIDR block (min /28 max /16)
- optional secondary IPv4 blocks
- optionally you can assign a IPv6 CIDR block (either AWS assigned, or assinged those you own)

VPC gets route 53 DNS automatically available on the IP =  `VPC Base IP + 2`
- two options
	- `enableDNSHostnames` - gives instances hostnames
	- `enableDNSSupport` - enables DNS resolution