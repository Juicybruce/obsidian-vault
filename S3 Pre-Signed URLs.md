This is way you can give access to a specific object in a bucket

When a bucket is private, all requests need to be authenticated, if you need an anonymous user to access an object you need to:
- give them an AWS identity (no longer anon)
- provide AWS credentials (admin overhead, security risk)
- make the bucket public (security risk)
None of these are ideal

This is where pre-signed URLS comes in:
![[Pasted image 20250116150024.webp]]
- a IAM user can generate a presigned-URL for a bucket and/or object, with an expiry etc 
- this URL can then be used by an anon user to access the configured bucket/objects (or for PUT objects)
- that object is access AS the identity that accessed it

Another architecture that uses pre-signed URLS:
![[Pasted image 20250116150339.webp]]
- If we are hosting media on an s3 bucket, it needs to be public or we need to give users IAM roles. Not Ideal
- However, we can instead make a new IAM user for the application
	- Then when media is requested by the user, the application can generate the pre-signed URL which then returns to the user
- so when media is offloaded to s3 OR you are using serverless architecture, these presigned URLs are useful 

>[!error] Exam 
>- You only **need an expiry and a target object** to make a presigned URL, so technically you can actually **generate a URL that gives no access (because you have no access)**
>- When you use a URL, the permissions match the identity that generate it, **AT THE POINT THE URL IS USED, NOT WHEN THE URL WAS GENERATED**
>	- This can mean the generating ID **never had access** or **DOESN'T NOW**
>- You should never generate a pre-signed url with a role, **its temporary credentials will likely expire before the URL**, which will break the URL