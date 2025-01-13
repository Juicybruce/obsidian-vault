#aws #programming 

>[!error] S3 is **private by default**
>The **only** identity that has any access is the account root user of the account that created the bucket

### S3 Bucket Policy

This is a type of resource policy, outlining a resource-based perspective (the inverse of the identity policies)

Identity policies are limited by their need to be attached to identities in the **same account**, 
- meaning that if you want to give access to an user **outside your account**, you need to do it at the resource level

>[!note] Resource Policy advantages
>- You can grant access outside your account
>- You can also grant anonymous access

In resource policies there is an explicit **principal** attribute on each statement:
![[Pasted image 20250110095518.webp|380]]
- in this example, this principal allows your own accounts, other accounts AND anonymous access (using the * wildcard)

Bucket policies have many different abilities:
![[Pasted image 20250110095718.webp|350]]
- block specific IP addresses

![[Pasted image 20250110095747.webp|427]]
- this allows all objects to be read, expect the `boris` prefix, which will be denied to people without MFA

### Access Control Lists

This is a legacy system that allows simple permissions 
- quite inflexible and simplistic

Almost entirely replaced by bucket policies and no longer recommended for use

### Block Public Access

This is a set of options that provide an **additional barrier** that restrict **public access to the bucket.** They will apply only to the configured *public access*, ie, an anonymous principal

>[!error] Exam - When to choose Identity or Bucket Policies
>Often there is no right answer here but some general guides:
>- Controlling many different resources - Identity
>- You want to control everything in 1 place - IAM Identity
>- You are granting access in one account - Identity
>
>- Just controlling one service or bucket - Bucket Policy
>- You need to grant Anonymous or Cross-account access - Bucket Policy
>  
>  NEVER USE ACLs, unless you absolutely **must**
