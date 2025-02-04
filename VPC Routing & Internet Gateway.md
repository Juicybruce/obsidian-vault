Every VPC has a highly available VPC router
- every subnet has a network interface address to this on `network + 1`
- this just routes traffic between subnets

You can can control outgoing traffic on each subnet via **route tables**
 - the **main** route table is the default one, but you can associate a **custom route table** with a subnet 
	 - each subnet **always** has 1 route table, but a route table can apply to many subnets 

![[Pasted image 20250122120919.webp]]
- local routes are not editable and take highest priority
- all other custom routes are given priority by the prefix specificity


### Internet Gateway

This service provides internet access to a VPC and is **regional**, you only need 1 to cover the whole VPC

This runs within the AWS Public Zone and runs traffic between the attached VPC and the Internet or Public Zone services (S3, SQS etc)

So to make a subnet public:
1. create IGW
2. Attach a IGW to a VPC
3. create a custom route table
4. associate it to our subnet
5. add IPv4 default routes to the IGW
6. configure the subnet to allocate IP addresses automatically
![[Pasted image 20250122121706.webp]]

>[!error] How does addressing work within a VPC
>While you are allocating 'public IPs' to services within a VPC, they are actually **kept as records within the IGW** that link that 'public IP' to the actual private IP address
>
>This means the Operating system on say an EC2 only ever see the private address it has. **The services never touch the 'public IP' they are allocated**, these are simply markers that allow the IGW to map it
>
>The IGW will alter packets to allow routing over the private internet, changing the source IP from the private IP (that the service knows) to the 'public IP' (that the IGW maps to the private one)
>![[Pasted image 20250122122445.webp]]
>
>On the way back, a packet is addressed to the 'public IP' of the service, which is ACTUALLY addressed to the IGW, which can map it to the private IP so it can be sent through the VPC to the correct destination
>![[Pasted image 20250122122626.webp]]
>
>>[!error] THIS IS NOT THE CASE FOR IPv6
>>These are **actually** public







