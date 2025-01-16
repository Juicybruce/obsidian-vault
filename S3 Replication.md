This allows you to configure replication of object from one bucket to another.

Two types:
- cross region replication (CRR)
- Same region replication (SRR)

The architecture is fairly simple, but will change depending on whether the destination is in the **same AWS account**
![[Pasted image 20250116144153.webp]]
- replication config sits on the source bucket
- within the same account, the IAM role automatically has access because the account is trusted
- on different accounts, the source account wont automatically be trusted
	- you need to add a bucket policy to trust the role being assumes

#### **Options**

- **All objects** or a **subset chosen by a filter** 
- default to same **storage class**, but you can **configure the destination to use a different one**
- default to **source account ownership of replicated object**, but can configure to **override the owner** (useful for when replicating to a bucket in a different account, otherwise that account might not actually have access to that object)
- Replication Time Control (RTC), to add a SLA to the replication, otherwise its **best effort**
	- This will guarantee the **replication will occur within 15 minutes**

>[!error] Exam considerations
>- **Replication is not retroactive**, existing objects are not replicated when you enable it
>	- Batch replication can be used to catch the older objects, but that is manually triggered
>- **Versioning needs to be on** for both buckets
>- **Replication is one way** source -> destination
>	- more recently **bi-directional** replication has been added but need specific configuration
>- Can handle **unencrypted**, and all **SSE objects** (SSE-KMS takes extra config)
>	- SSE-C is recently added 
>- **Source bucket owner needs permissions** to the objects 
>- NO **System events,** **glacier storage objects** can be replicated
>- NO DELETES (though delete marker replication can be configured)


Why would you use this?
- log aggregation
- Prod and test sync
- Resilience with strict data sovereignty
- Improve resilience (if using CRR you can get regional resilience)
- Latency reduction (if using CRR you can have users access data at a closer bucket)