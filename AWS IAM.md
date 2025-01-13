
The root user is fully trusted and **cannot** be restricted in any way

In real life you generally want to give only the **least privilege necessary** to do whatever tasks that user needs to do

Each account has its own IAM instance, but IAM is a **globally** resilient service. Each IAM is fully trusted within the account and can do almost anything, so each user can be given similar trust (or some of it)

IAM has three identity concepts: 
- **Users** - represent humans or applications that need some level of access
- **Groups**  - collections of relates users (eg: developers, HR etc)
- **Roles** - used by services or by external users to **assume** a certain level of privilege. Generally this will be used when access is required by an uncertain number of entities (you make the role, then allow any EC2 to use it for instance)

**Policies** are created to define the allowing or denying of access when *attached to one of the previous*

General points
- IAM is free but there are limits
- IAM is global (globally resilient and uses a global database)
- Can only control (via policies) identities within its account, it **does not allow control over exernal accounts or users**
- IAM allows identity federation and MFA 