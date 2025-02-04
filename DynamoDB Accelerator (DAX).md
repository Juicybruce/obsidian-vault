![[Pasted image 20250130145048.webp]]
- when using DAX, you use the SDK 
- The DynamoDB handles the caching, which is much more efficient than the client handling the cache hits/misses


![[Pasted image 20250130145240.webp]]


>[!error] EXAM
>- is HA, where the primary node will hand over to a secondary node
>- Much faster reads and generally reduced costs if you are doing heavy reads on the same set of data
>- scaling can be done up or out 
>- supports write-throughs 
>- DAX is within a VPC (note that DynamoDB is in the public zone)

