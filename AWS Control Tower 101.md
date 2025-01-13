>[!error] This will likely be on the exam

This service uses many other AWS services to **orchestrate** the setup of multi-account environments
- in many ways this is AWS Organisations, but super-charged

The architecture is something like this:
![[Pasted image 20250109103620.webp]]
- within the **management account** we have
	- **control tower**, providing orchestration
	- **organisations** providing the structure
	- **Identity Center** which allows SSO or federated access
- When created, Organisations will automatically create two OUs:
	- Foundational OU, contain two default accounts:
		- Audit Account - this provides overview on your whole control tower setup
		- Log Archive account - contains CloudTrails and AWS Config for isolated and read-only logged
	- Custom OU (defaults to 'Sandbox') - this uses **account factory** to generate accounts as necessary using pre-defined templates. This is all done with CloudFormation under the hood
- **Guard rails** are implemented to **prevent and detect** drift away from the normal governance structure 

### Landing Zone

This is intended to allow anyone to set up a **well-architected environment**

There is a **home region** that is set

>[!note] The Landing Zone uses many other services to provide functionality
>- Security/Foundational OU uses services within to provide highly secure and robust logging and auditing
>- Sandbox OU to provide a less rigid testing environment
>- Identity Center allows SSO and Identity Federation
>- CloudWatch and SNS to monitor and notify about changes or drift in the organisation
>- End user provisioning of accounts via Service Catalog

### Guard rails

These are essentially sets of rules to guide multi-account governance

They are either Mandatory, Strongly Recommended, or Elective

They are either:
- Preventative - these will stop you from doing something (if enforced)
- Detective - these are compliance checks, that will check whether your resources match AWS Config rules (these are registered as **clear**  or **in violation**)

### Account Factory

This allows automated provisioning of accounts by cloud admin OR end users with appropriate permissions

This means you can set up a truly self-service account provisioning system, as the people who provision these account can name users that will then have **admin permissions** over the AWS account being created

>[!note] The other features
>- You can apply standard configuration to both accounts and networking within it
>- You can close or repurpose accounts automatically
>- You can tightly integrate the factory with **Software Development Life Cycle** tools or processes
