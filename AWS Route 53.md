This is a AWS DNS Service that allows you to:
1. Register domains
2. Host Zones files and managed Name Servers 

This is a global service, and is thus globally resilient

In order to register domains, Route 53 maintains relationships with all registries
- when you register a domain Route53 will:
	1. check it is available in the relevant registry
	2. create a zone file for that domain
	3. allocate 4 NameServers for the domain
	4. add those nameservers to the registry (which is how the registry delegates the zone admin to us)

#### Zones

Hosted Zones in AWS are the **zone files** that are hosted on the allocated NameServers

Can be either public (part of the public DNS system) or private (accessible only within the VPC they are within)

### DNS Record Types

**NS records** - these allow delegation to another server for the hosting of the zone file of the domain

**A/AAAA records** - these map host names to IP addresses (A is IPv4, AAAA is IPv6)

**CNAME record** - these are host-to-host records kind of like 'DNS shortcuts'. 
- If you have a single record pointing at your load balancer for instance, you can use CNAMEs to point other subdomains to that records to reduce admin overhead
- CNAMEs only point to other names, not IP addresses

**MX Records** - these are essential to the functioning of email over the internet. They consist of two parts:
- priority
	- Lower values are used first, then higher values in order if any lower ones are non-functional
- value
	- with no host specified (no dot on the right), it is assumed to be part of the host it is within
	- if you include a dot, it becomes a Fully Qualified Domain Name, which can point outside your zone

These records are what are queried when an email is sent.
- The email server will query the MX records on the 'from address' (example@**FROM-ADDRESS.COM**)
- The MX record of the highest priority (lowest functional number) tells the web-server where to send the email via SMTP 

TXT record - These are generic records that provide additional functionality via arbitrary strings
- examples include verifying domain ownership etc 

### Time to Live (TTL)

This is the 'expiry time' in seconds attached to each record

Getting an **authoritative** answer for a specific query requires walking the tree of your DNS resolver and all the various steps of root -> TLD -> domain servers

While this authoritative answer will always be preferred, TTL times can help reduce this time by indicating how long the resolver should cache the result. So next time the record is queried, the requester will receive this cached,  **non-authoritative answer** much quicker