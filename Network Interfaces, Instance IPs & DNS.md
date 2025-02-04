

EC2s start with a primary interface (ENI)
- you can attach secondary ENIs 
![[Pasted image 20250123122836.webp|535]]
- Important to note that a lot of things you think of as being attached to an EC2 are actually attached to the ENI
	- note that security groups are applied on the ENI, not the EC2
- traffic is discarded if the ENI IP doesn't match the source or destination (you can turn this off)

![[Pasted image 20250123123402.webp]]
- note that the public DNS hostname will resolve to the **public IP** from outside the VPC but will resolve to the **private IP** inside the VPC
- Elastic IPs are account wide
	- if you assign one to an instance it **replaces** the public IP, if you remove it a **new public IP will be given**

>[!error] Exam tips
>- secondary ENI + mac addresses allow you to swap the licensing of a program that is tied to a MAC address (which is tied to a secondary ENI that can be swapped to new instances)
>- Multi-homed (subnets) for separating management and data
>- you might use multiple ENIs because you will add different security groups 
>- The OS **does not ever see the public IPv4**
>- IPv4 public IPs are **dynamic**, if you stop and start you will get a **different IP address**
>- Public DNS will **resolve to private IP** in the VPC, **public IP outside it**

