#aws #programming 

### IAM Users

These are identities used for anything requiring long-term access to AWS services
- this applies to both humans or machine access

The steps for identities to authenticate and authorise their interactions are as follows:
1. a **principal** (machine or human) makes a request to IAM to authenticate with an **identity** within IAM. This principal **claims and proves this identity** either via usernames/passwords or access keys
2. The principal becomes an **authenticated identity** if successful
   
3. this identity takes an action against a resource and AWS checks the various policies that dictate that interaction
4. if successful, that action is carried out

>[!tip]
>Steps 1 + 2 is **Authentication**
>Steps 3 + 4 is **Authorisation**

>[!error] Important Exam Information
>- You can have **5000** users **per account**
>- Each user can be a member of **10 groups**
>  
>  These will have system design impacts on **large organisations** or **internet-scale applications.** In these situations, you shouldn't be using IAM users (using federation or Roles instead)

### ARNs

These are used to uniquely identify resources within any AWS accounts. They are defined via a specific syntax:
![[Pasted image 20250106120856.webp]]

The syntax are fields separated by colons (`:`), if you see chained colons it means there is an absent optional field

You can also wildcard to refer to an entire collection

>[!note]
>One of the most common trip-ups is mis-identifying a resource and its sub-resources. For for instance:
>
>`arn:aws:s3:::catgifs`
>`arn:aws:s3:::catgifs/*`
>
>The first refers to the **s3 bucket itself**, the second refers to the **objects within the buckets**
>
>These two ARNs **do not overlap**


