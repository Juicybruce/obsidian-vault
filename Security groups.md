Security groups are **stateful**, so will handle the response of allowed requests

The major limitation is that they don't allow a EXPLICIT DENY. 
- this means that you can't target a specific bad actor, you will use NACLs to do this 

They do allow references to logical resources, including other security groups or even **itself**

>[!error] SGs are always attached to (Elastic) Network Interfaces, not subnets or VPCs

![[Pasted image 20250122141210.webp]]
- the 'boundary' that traffic is monitored across is the the network interface

**Logical references** can be used by SGs in its rules
![[Pasted image 20250122141600.webp]]
- so instead of trying to allow IP ranges etc, we can just reference another security group or similar
- in this case, anything with the referenced SG will be allowed to have its traffic enter/exit
	- we dont have to use IP AND it scales really well, massively reducing admin overhead

SGs can also reference themselves within a rule
![[Pasted image 20250122141759.webp]]
- here we have unrestricted traffic on anything with the current security group

