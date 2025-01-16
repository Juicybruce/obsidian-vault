This improves the manageability of s3 buckets

By default, if you have a massive bucket with millions of objects being accessed by hundreds of individuals, you would have to have an **extremely complex bucket policy**

Access points allow you to logically split this into many different access points, each of which have a policy:
- controlling access by users
- controlling **network access controls**

>[!tip]
These can be created in the console, or by using the command `aws s3control create-access-point` in the CLI

Architecture diagram of a possible situation:
![[Pasted image 20250116164124.webp]]
- this would be unwieldy within a single bucket policy
- You can configure the access origin 

>[!note] Acess points can be thought of as 'mini buckets'
>They are logical separations of the main bucket 
>
>Each has their own policy, endpoint and DNS record for network access
>
>Access point policies permissions need to match on the bucket policy, or **delegated to the access point policy by the bucket policy** by opening access and letting the access point do the granular access

