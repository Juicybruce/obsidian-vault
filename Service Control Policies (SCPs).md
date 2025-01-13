These are policies that allow control over the access accounts have within organisations

These are JSON documents can be attached to the organisation root, OUs or to member accounts directly
- they obey the hierarchy of the organisation, ie, if you attach them to an OU, they apply to everything within it (other OUs and accounts)

>[!error] Management account
>This account is **special**, SCPs cannot be effected by any policies attached to it 

These policies are serving as **account permission boundaries**, limiting what accounts themselves are allowed to do:
- while account **root users** cannot be restricted within their accounts, SCPs allow restrictions on the account themselves, resulting in the same thing

>[!note] SCPs are a permission **boundary**
>They define the **limits of what accounts can do**, they don't **grant** permissions to AWS resources
>
>Anything **allowed** either implicitly or explicitly is **allowing that account to grant access to identities within the account to access that resource**
>
>![[Pasted image 20250109095642.webp]]



SCPs function either by:
- **Deny** list (default by the `FullAWSAccess` policy) - everything is allowed, except for explicit restrictions
	- This is lower overhead, as you don't need to constantly update policies to reflect newly added services etc
- **Allow** List (implemented by removing the `FullAWSAccess` policy and allowing the implicit Deny to take priority) - This would require explicit allow statements
	- Lots more overhead and easier to accidentally block required services