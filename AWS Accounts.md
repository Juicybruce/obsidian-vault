Easy to get accounts mixed up with users inside those accounts, but important to **understand** what they are and what they **provide**

- They are **containers** for identities (users etc) and resources (services etc)
- need **unique email addresses** and payment details
	- **Root user** will be created with the email address provided, every account has one and will be the *first identity within it*
	- be **very careful with the root user** as it has FULL ACCESS
	- best pratice is to use the root user for initial setup, add an admin user, then never use it again except in emergencies

Other identities can be created in IAM (as well as grouped) and can be given full or limited access to the account.

Accounts are very good at isolating any possible damage to within the account.

By default, all access is **DENIED**, access needs to be given explicitly