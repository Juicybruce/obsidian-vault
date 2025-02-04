How best to choose EBS vs IS? What volume types?

Best things for EBS
**Persistence**
- instance store is temporary
**Resilience**
- if you a relying on snapshot of a single volume, you need EBS
**Isolation**
- if you need your storage lifecycle to be isolated from your instance lifecycle, instance store doesn't suit

There are scenarios where it isn't as clear:
- you need **resilience**, but your app has built in replication across many volumes.....well it depends
- you need **high performance**, though **super-high** needs to be instance store
- **Cost** concerns might lean you toward the instance store (it comes with your EC2)

>[!Error] Key exam notes
>- **Cost is a concern** - go with with SC1 or ST1 (hard disk)
>- if you need **throughput or streaming** - ST1
>- If you need **boot capabaility** - can't be either of the HDD based 
>- **performance**
>	- GP2/3 can provide up to 16,000 IOPS
>	- IO1/2 can provide up 64,000 (\*256,000 on block express on larger EC2s instance types)
>	- RAID0 + EBS can be used to get up to 260,000 IOPS (this is the absolute maximum allowed by any EC2 instance)
>	- if you need **more than** 260,000, you will require instance store (but they will not be persistent)

