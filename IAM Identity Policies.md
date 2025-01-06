#aws #programming #learning 

Policies are used constantly, they are a **set of security statements that either *grant* or *deny* access** to services to identities that are using that policy

Identities can have multiple policies, so AWS will review each one when a resource access is requested by an **authenticated identity** (ie, an identity that has been proven)

Policies are written in JSON, here is an example:
![[Pasted image 20250106112449.webp|504]]

You can see that there are a number of **statements within the policy**, each one will have certain fields:
- SID - an optional identifier for the statement
- Effect - the explicit Allow or Deny for the interaction
- Action - the array of actions the statement applies to (in the form ``<service>:<action>``, eg `s3:getItem`)
- Resource - same as actions but for resources

Both actions and resources can be wild carded with `*`

>[!tip]
>It is important to note that each interaction with AWS will regard two things: the **action** being performed, and the **resource** being targeted.
>
>AWS will only assess policy statements that match both.

>[!note]
>**Allows and Deny statements may overlap**, either with a broad statement conflicting with a narrow one or vice versa. Parsing these is important for the exam
>
>Luckily there are some priority rules to help, in order of :
>1. Explicit Deny - this overrules everything, no action will be allowed if there is an explicit deny statement for it
>2. Explicit Allows - these will apply always **except in the case of explicit deny**
>3. Implicit Deny - the default for all access is an implied deny, if there is no explicit rule, the action will be denied
>
>This priority list can tell you how an action/resource combo will resolve.
>
>>[!tip]
>>The way AWS handles the **many policies** each user will have attached, either directly, via a group, or on the resource itself is to gather them all together and assess all the statements at once.
>>
>>The above xDENY - xALLOW - iDENY rule applies is **all cases**

You can add policies to users in two ways:
- **Inline policies**  - attach the JSON policy to each user directly (each policy is an individual policy)
- **managed policies** - make the policy and attach that object to the user 
	- these are not individual, they are a singular policy that are managed as one, reducing overhead

Inline policies are used for special or exceptional cases where and ALLOW or DENY is needed

Managed policies can be created by the customer, but AWS does have their own set of managed policies too that you can use