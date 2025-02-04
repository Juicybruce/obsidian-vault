These are the two different ways that a changing load can be managed across a system

### **Vertical Scaling**

In EC2, when we want to vertically scale we would provision a **larger instance**
- this would require a reboot and would disrupt customers 
- larger instances carry a premium
- there is an upper cap of instance size
- one **benefit** is that we don't have to change our application at all =

### **Horizontal Scaling**

Instead of the instance getting **larger**, you simply add more instances
- you will need to route the traffic across all the instances with a **load balancer**

Important notes:
- sessions are everything. You need to make sure that end-users have consistent sessions 
	- your application needs to handle this, or use **off-host sessions** where your servers are **stateless**

Benefits include:
- there is no disruption while scaling
- no real limits 
- you don't trigger the premium of larger instances
- allows a lot of granularity with how much you scale

>[!error] Exam tips