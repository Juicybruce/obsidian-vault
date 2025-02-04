
What is NAT?
- its a set of processes that changes the source or destination IP addresses on packets
	- we saw the IGW doing this in a type of **static NAT**

The main version of NAT that people think of is **IP masquerading**, where a whole CIDR block is hidden behind a single IP address
- this is very popular because IPv4s are running out

Important to know that this is for **outgoing** internet access, given we are using a single point for a whole CIDR block, incoming access wont work
- the connections initiated by the private services can receive **responses**, but external access directly to these services is not possible

How to get NAT?
- historically you would use an EC2 configured to provide NAT
- These days there is a managed service called a NAT Gateway

Here is an illustration of an example structure:
![[Pasted image 20250122143408.webp]]
- here we **could** make the instances and subnets public, but NAT provides another option
  
- so we can configure the route table in the public subnet to allow in/out traffic from the IGW
- then we configure the private subnet route table to all in/out traffic from the NAT gateway

So to simulate a packet from one of these private instances:
1. an instance sends a packet
2. the route table sends this packet to the NAT Gateway
3. the NAT gateway records all information necessary to uniquely identify the communication stream for this packet into a **translation table**
4. The NAT gateway changes the source IP to its own 'public IP'
5. the packet goes to the IGW which **itself** remaps the 'public IP' of the NAT gateway to its own 'actually public IP', recording where it came from

>[!error] Considerations for running NAT
>- must be in a **public subnet**
>- they use Elastic IPs (these are unchanging IPs)
>- They are **AZ resilient service** and are **HA in that AZ**
>	- to get regional resilience you need to have a NAT in each AZ (with the rest of the required config like route tables pointing to the IGW etc)
>- managed service
>- scales to 45Gbps
>- Pricing is an **hourly charge** + a **data volume charge**


Implementing NATGW full resilience:
![[Pasted image 20250122151537.webp]]
- NATGW is an AZ level service, to be fully regionally resilient you need:
	- a NATGW in each AZ
	- private route tables in each AZ pointing to the relevant NATGW

>[!error] NATGW is NOT regionally resilient

NATGW vs NAT Instance

A NAT instance is just an EC2 that is configured to provide NAT
- still need a public IP in a public subnet and an IGW

Most of the time you will use a NATGW as that is what AWS suggests. But there are some instances where an instance is preferable
- NATGW is highly performant, highly available and scales if that is the what the concern is just use a NATGW. A NAT instance is only as available as the underlying instance
- **Cost is lower** for a NAT instance, particularly at high levels of data flow
	- NATGW is not free tier eligible
- NAT instances are multi-purpose and flexible. They are just an EC2, you could **run other services on it**, use it for **port forwarding** or as a **bastion host**. NATGWs cannot do any of this.
- Security groups cannot be applied to NATGW, only NACLs

>[!tip] NAT is not required with IPv6 
>IGW work with ALL IPv6 IPs directly and all addresses in AWS are publicly routable
>
>NATGWs **don't work with IPv6** AT ALL
