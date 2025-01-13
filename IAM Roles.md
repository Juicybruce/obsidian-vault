#aws #programming 

A role is a type of identity within an AWS account
- while a **user** is generally for a single principal, a single person or machine
- a **role** however is designed to be used with multiple principals, either many people or applications, or when that number is indeterminate

Roles tend to be used on a temporary basis, the **principal assumes the role**, they become that role which represents a set of permissions
- when the role is assumed, short-lived temporary credentials are created which are then used to access resources

>[!note]
>The service used to assume a role, and generate the credentials is AWS Security Token Service (STS)
>
>The action used is `sts:AssumeRole`

Roles have two types of policies attached to them:
- **trust policies** - these dictate what identities can assume the role
	- these can refer to identities within the same AWS account, **in a  different account** or even other identity providers (facebook, google etc)
- permissions policy - the usual policy document that Allows or Denies access to resources

>[!tip]
>Resource permissions policies **can refer to roles** as well as users/groups when granting or denying access

### When to use Roles

A few examples of when roles might be useful:

>[!note] AWS Lambda functions or similat
>**AWS Lambda** by default has no permissions, but we could create a role for the service to **assume** when a function is invoked
>- The trust policy would list the lambda service
>- the permissions policy would allow access to the resources necessary for the function
>  
>  So here, our function is running in a runtime environment that **assumes** the execution role, which generates our credentials which can be used by all the code in the function.
>  This allows us to avoid using **explicit access keys** (which are insecure and might need to be rotated)
>  - it is always better to use a Role for this instead

>[!note] Emergency (Break Glass Situations)
>Roles can provide emergency access in a last resort situation, where usual user permissions are minimised 

>[!note] In existing corporate environments (ID Federation)
>Sometimes, you will have have existing identity providers and you want to use these external identities in AWS accounts
>Because **they cannot be used directly**, you will need to utilise roles
>
>You can allow an external identities to assume roles, and interact with resources via that
>
>This is probably what will be used if there are more that 5000 potential users
>- if there are many external users, using roles via ID federation quickly becomes the best option

>[!note] Web Identity Federation
>Similar to above, if you have an application where users need to access data from an AWS service you can federate access using Roles
>
>Web identities (facebook, twitter, google) can be used to assume a role
>
>>[!error] This often comes up on the exam
>>Due to the scaling of mobile applications, questions will often be asked about how to provide access to millions of users
>>
>>Roles is how

>[!note] Cross account access
>Roles can be used to allow access in seperate AWS accounts
>
>This is the structure used in many organisations that split their larger AWS resources into seperate Organisations and Accounts

