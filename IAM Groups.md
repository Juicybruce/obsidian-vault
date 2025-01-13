#aws #programming 

These are **containers** for IAM users, helping with organisation of those users

>[!error]
>You cannot log into groups themselves, they have no credentials. 
>
>This **also means** that groups cannot be referenced as a principal in resource permission policies, **they are not a true identity**
>
>They are **only a way to contain users and organise policies**

A user can be in multiple groups (up to 10)

Groups can have policies attached, which will then apply to any users within the group

>[!error]
>There is a limit to the number of groups - 300. This **can** be increased with a support ticket
>
>There is no limit to the number of users in a group (you can technically have all 5000 users in an organisation in a single group)
>- However, there is no built-in 'all users' group 
