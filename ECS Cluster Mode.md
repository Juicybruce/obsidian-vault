the two types are **EC2 Mode** or **Fargate Mode**
- this will essentially change how much you are managing vs what AWS is managing

### EC2 mode
![[Pasted image 20250123161802.webp]]
- in this mode an ECS cluster is created within your VPC which means it can benefit from the multiple AZs
- within the cluster, EC2s are created to run your containers
- according to your definitions, your containers will be deployed into your EC2s, but you are expected to manage:
	- the number, capability and availability of the EC2s

This is generally a middle ground, somewhat flexible

### Fargate Mode

In this mode, you don't manage the EC2 services yourself, it utilising a shared Fargate infrastructure 
![[Pasted image 20250123162126.webp]]
- the architecture is much the same **except** that each task is injected into your VPC and given an ENI
- still uses your definitions etc 
- you only pay for the containers you are using while using them, you are billed for no hosts etc

### EC2 vs ECS (EC2) vs Fargate

- if you use containers  - use **ECS**
- **Large** workload - **price** conscious - use **EC2 mode**
- More focussed on reducing overhead - use **Fargate**
- Bursty or small workloads - use **Fargate**
- Batch or Periodic workloads - use **Fargate**