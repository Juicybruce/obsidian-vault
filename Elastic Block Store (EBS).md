This is a service that provides **block storage**

EC2s will see a block device, that the OS can then lay a file system over

EBS is a AZ service, so resilient and isolated to a single AZ
>[!error] You cannot communicate between AZs with networked storage

The process is to **create a volume** then are attached to an instance:
- these volumes are **attached** to an instance, but their lifecycles are not tied to that instance. They can be detached and reattached elsewhere

EBS takes snapshots of volumes as backups regularly, and volumes can be created from these snapshots

EBS is priced (generally) on GB/month 

![[Pasted image 20250123100403.webp]]

### Storage Types

**General Purpose SSD** - **GP2**
![[Pasted image 20250123102251.webp]]
- Volumes can be 1GB to 16TB
- When created, you get assigned a number of IO credits that are consumed by the storage activity
	- Credit capacity is 5.4 millon and credits are **refilled as a baseline rate + the bucket size**
		- base is 100 IO credits a second, beyond that you fill at 3 IO credits per second per GB of volume size
	- You can burst up to 3000 IOPS using these credits
- Any volumes about 1000GB your baseline performance becomes more that your burstable amount

**General Purpose SSD** - **GP3**

Very similar to GP2, but 20% cheaper up to 3000 IOPS:
![[Pasted image 20250123102447.webp]]
- you can purchase up to 16,000 IOPS

**Provisioned IOPS SSD** - **io1/2** and **io 2 block express**

![[Pasted image 20250123102853.webp]]
- much faster than GP SSD
- consistently low latency and jitter
- Need to be aware of the maximum level of performance between this type of EBS and the EC2 instance. At this level of performance of the storage, the cap on the EC2 becomes the bottleneck

**HDD-based**

Generally you will be using this storage type when performance is not really what you are after (hard drives are slow)
![[Pasted image 20250123103524.webp]]
- **st1** is designed for frequently access data like big data, data warehouses or log processing