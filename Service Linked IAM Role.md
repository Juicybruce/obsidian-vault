#aws #programming 

These roles operate very similarly to normal roles but have a few specific features:
- They are linked to a specific **service**
- Their permissions sets are often **predefined by the service**
- The service might create these themselves

A key difference is that these roles **cannot be deleted** until it is no longer required

>[!tip] Role Seperation
>Using these service linked roles allows you to give people the ability **not to assume a role, but give it to a service that will need certain permissions**
>
>If a identity has the `iam:ListRoles` and `iam:PassRole` permissions, instead of using **their** identity when utilising a service, they can instead pass a service-linked role for the service to use.
>
>For example:
>**Cloud Formation** would usually use the identity and permissions of the caller (for CF and all other services), but the caller could instead **pass a service role** to CF for it to use, which might have greater access for the orchestrating of stacks etc



More information can be found [here](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create-service-linked-role.html)