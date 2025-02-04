This service is managed container based compute service

Architecturally this is how they work:
![[Pasted image 20250123161003.webp]]
- We need to hand over some container images as **container definition**
- then we have a **task definition**, which represents the application as a whole
	- this stores the resources, permissions (**task roles**), networking etc
- **service definitions t**ell ECS how your would like your tasks to run (scalability, load balancing etc)

**Container definitions** - images being used and ports exposed
**task definition** - application as a whole, its security (and task roles), resources to use
**Task Role** - this is the IAM role assumes by anything within the task
**service definition** - how many copies, availability and scaling and restarts etc

