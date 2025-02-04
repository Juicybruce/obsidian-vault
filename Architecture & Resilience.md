Some key points:
- Each instance is a virtual machine that run on either **shared** or **dedicated hosts**

>[!error] AZ resilience is KEY to EC2 and its related services
>EBS, volumes, Hosts are all running in a single AZ. Everything is locked into that AZ
>
>You cannot network between any of these directly


What is an EC2 good for?
- you have a traditional OS + Application compute need 
- long running compute needs 
- Server style applications 
- can handle **burst** or **steady state** load
- **monolithic application** stacks
- **migrated application workloads** or **disaster recovery**

EC2 tends to be the default compute service, other services tend to be for niche cases





