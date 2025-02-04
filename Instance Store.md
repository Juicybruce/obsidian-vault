This storage has many pros and cons

This still provides block storage, but **not over the network**
- these are **physically attached** to the instance host, but are **isolated to that host**

Because they are locally attached, they are **much faster** than network storage

>[!error] These are ATTACHED AT LAUNCH ONLY, you cannot add them later

- If an instance moves between hosts or the host has a hardware failure, the instance store on the old host is **LOST**
	- this can happen for **many reasons**, so 

>[!error] it is important to treat all instance store volumes as EPHEMERAL 

One of the primary pros of the instance store is **performance**
- they generally perform much faster than their EBS counterparts

>[!error] EXAM NOTES
>- **local** on the EC2 host
>- added on **LAUNCH ONLY**
>- lost on instance **move, resize, hardware failure**
>- highest **data performance possible in AWS**
>- You always pay for the instance store that comes with the EC2 instance