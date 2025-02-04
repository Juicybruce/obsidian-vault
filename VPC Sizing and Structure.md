You will need to decide on the VPC CIDR (IP range) **in advance** as it isn't easy to change in the future and can cause large headaches if you get it wrong. This includes the considerations include:
- what size the the VPC should be
- are there any network we cannot use? 
- try and predict the future
- the structure of the VPC, ie, the tiers and AZ zones will take up space within the range

You might want to outline the current IP ranges that are in use and must be avoided. See below for a fictional example of Animals for Life, which illustrates this process:
![[Pasted image 20250122102653.webp]]
- note the **enormous** good range (using /9, which is half the octet of /8)

More considerations
- limits on sizing - /28 minimum /16 max
- usually avoid commonly picked ranges (10.0.. and 10.1)
- how many regions will your business be operating in? add a few
	- you will want 2+ networks in each region
	- this will be multiplied by the number of accounts (probably around 4)

General sizing gudie from AWS:
![[Pasted image 20250122113709.webp]]
- how many subnets will you need?
- how many IPs in total and per subnet

>[!tip]
>Remember that services are not launched in VPCs, they are launched within **subnets**
>
>The number of subnets will differ, but usually a best practice is 3 (for most regions have 3 AZs) plus 1 for future growth 

>[!error] Remember the prefix sizing
>Say you have a /16 IP range, that can be split into:
>- 2 /17s
>- 4 /18s
>- 8 /19s
>- or 16 /20s

