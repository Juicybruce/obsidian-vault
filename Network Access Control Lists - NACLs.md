These are a optional security layer that is **associated with a subnet**

>[!error] NACLs effect traffic going through the perimeter of the subnet
>If there is traffic within a subnet, it will not be effected

We have **Inbound** and **Outbound** rules
- remember this doesn't match the 'request' and 'response', and NACLs are stateless so they don't know
- The rules allow explicit DENIES or ALLOWS

![[Pasted image 20250122125317.webp]]

>[!tip] the process
> If traffic is seen as Inbound or Outbound, those set of rules are assessed
> It goes in order from **lowest to highest rule number**
> if a match is found, be it deny or allow, **WE STOP**
> - this is really important to note because it means higher number rules can be ignored
> Finally, if nothing matches, there is a wildcard 'implicit' deny

NACLs are stateless, so we need individual in/outbound request/response rules:
![[Pasted image 20250122125540.webp]]
- note the coverage of ephemeral ports etc

Lets have a look at a more complex example where multiple subnets are being passed through:
![[Pasted image 20250122125827.webp]]
- always be aware of the rule pairs
- this becomes extremely complex as you add elements

When a subnet is created, the default NACL has a wildcard deny BUT a rule that allows all traffic, which results in all traffic being allowed

When you create a **custom NACL**:
- the only rule is the implicit deny
- it is associated with no subnets (be careful when associating it due to the overall DENY behaviour)

>[!error] Things to be aware of with NACLs
>- They are **stateless**, requiring rule pairs for requests and responses
>- only impact traffic crossing the subnet boundary
>	- This means that rules becomes complex if you are communicating **between subnets**
>- NACLs can explicitly allow and deny
>	- explicit deny is a feature unique to NACLs, the other security services don't usually allow this. Means you can directly target the IPs of bad actors
>- They allow IPs, Ports and protocols, they are **UNAWARE** of logical resources
>- Often used with security groups for their explicit DENY capabilities
>- Each subnet can have **one** NACL (default or custom)
>	- A single NACL can be applied to many subnets

