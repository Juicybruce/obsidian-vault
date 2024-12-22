This service provides **instances** which are virtual machines that can be configured in various ways which can be used for whatever server tasks you require

**Private** service that deploys into a single VPC subnet
- if you wish it to be public, that needs to be configured via VPC networking (default VPC will do that for you)
- This means they are AZ resilient, if an **AZ fails, so will your instance**

Various sizes and capabilities available, which govern general resources and specialised resources (GPUs, specific networking capabilities etc)

Storage is available via various methods, but two popular ones are **on-host local storage** and another service called **Elastic Block Store (EBS)**

There are various **states** the instance can be in, such as **runnning, stopped or terminated**. This will effect your billing:
- **running** instances are charging for all physical resources (memory, CPU, storage etc)
- **stopped** will not use any resources **except for storage** (still charged for that)

##### Amazon Machine Image

These are an image of an instance, used to **create EC2s** or can be created **from** an EC2. This contains:
- permissions for the AMI (who can use this image)
- **Root volumes** that boots the system (and optionally other volumes)
- Block Device Mapping, that presents the volumes to the OS

EC2 are connected to via:
- Remote Desktop protocol via port 3389 on Windows Instances
- SSH protocol on port 22

