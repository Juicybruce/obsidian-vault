By default, when you put objects into a bucket with SSE-S3, each one will use the default s3 KMS key to create a DEK for that object
![[Pasted image 20250116123520.webp|700]]
- this can quickly stack up many KMS calls for creating DEK
- this can also cause throttling issues

Instead, we enable bucket keys which can then use the KMS key to generate a single **time-limited** key for the bucket, which are then used to create the DEKs
- this will solve the pricing and throttling problems

>[!note] Some important notes
>- Cloud trail will obviously report many fewer KMS events
>- But will also no longer report the **object arn** for events, instead you will see the **bucket arn**
>- Replication has some nuance:
>	- replicated objects will use the destinations bucket settings
>	- if the source **doesn't** encrypt but the destination uses bucket keys, this can result in `ETAG` changes on the object which might need to be accounted for