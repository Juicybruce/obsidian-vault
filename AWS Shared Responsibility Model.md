This is the understanding that between us and AWS, we are responsible for a portion of the stack we are operating on, and AWS is responsible for the rest

A illustration of general responsibility models is below:
![[Pasted image 20241219094654.webp]]

AWS has this model to make clear what is up to the customer to maintain responsibility over.
- AWS manages security **of** the cloud
	- This is all their infrastructure, regions, AZs, compute and storage and the software to manage all that
- We manage security **in** the cloud
	- We manage everything from the OS upwards
	- traffic protection, client or server encryption
	- platform, applications and any access and identity management
	- any and all customer data

This might not be on the exam, but it will help to clarify other concepts if this is kept in mind 