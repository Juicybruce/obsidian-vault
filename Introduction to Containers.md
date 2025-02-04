What we have been talking about about **virtualisation**, is actually **operating system virtualisation**

One of the major problems is that the Guest OS consumes a large amount of the resources
- often we are duplicating the OS a huge amount 

Containerisation is architected differently:
![[Pasted image 20250123155410.webp]]
- the container engine helps orchestrate processes in tandem with the base OS as isolated **containers**
- These application containers are much lighter weight

#### Images

![[Pasted image 20250123155634.webp]]
Docker images are either created from scratch or using a base image 
- they are made up of read-only FS layers that are defined in your Dockerfile

All that happens when you make this image into a container is **another fs layer** is added, not just read only:
![[Pasted image 20250123155857.webp]]

### Container registry

These are public or private repositories of docker images:
![[Pasted image 20250123160040.webp]]

Container key concepts:
- Dockerfiles are used to build images
- containers are portable and predictable in how they run
- FS Layers are shared and reused
- containers only runs the applications and what that needs, they are very fast and lightweight
- provides most of the isolation that VMs do
- containers **expose** ports to the host and to the outside world
- application stacks can be multi-container

