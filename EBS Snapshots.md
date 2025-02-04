These snapshots provide resilience and migration of EBS volumes, they are essentially backups of those volumes stored in s3

They are **incremental backups**
![[Pasted image 20250123110848.webp|311]]
- the first snapshot is **all of the data on a volume**
- all future snapshots are incremental, just storing the difference between the snapshot and its previous one
	- Do note that AWS snapshots are smart enough to cope with you deleting one of these incremental snapshots. The data will be copied so that subsequent snaps don't lose the missing data

Volumes can be restored from a snapshot
- they can be used in another region OR another AZ because they are stored in s3

![[Pasted image 20250123110308.webp]]

>[!error] important notes
>When you create a new EBS volume, full performance is available immediately
>- When you restore a volume from a snapshot, it will **read data lazily**. 
>	- The process of copying the data will be going on in the background, but if you try and read data that hasn't been copied yet, it will be fetched from s3 (slower than usual)
>- You can force a read of every block at the OS level 
>	- you can also use Fast Snapshot Restore, you get 50 of these per region and are set of the snapshot and AZ

Billing is done via a GB-month, and you are **only charged for the used data**
- a snapshot of a 40gb volume that is only 10gb full, you are only charged for the **used data (the 10GB)**