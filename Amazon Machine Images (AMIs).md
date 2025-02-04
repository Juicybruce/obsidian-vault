These are starting **templates** that apply to the instance when you launch them
- you are always using them when you launch an instance (say from amazon linux)

Some vendors will provide community templates for their OS 
- there is also a paid marketplace for licensed software

AMIs are **regional** and will have unique IDs for each region

AMIs have permissions settings so it can be used publically, by only its creator or by a specific set of accounts

You can create AMIs from a specific instance 

Lifecycle model:
![[Pasted image 20250123125152.webp]]
- you can configure an AMI heavily, adding applications and deep config
- you can then take that config and create a **new AMI**
	- important to note that when you create an AMI, any block storage will be snap shot and a **block device mapping** to reference each block storage
- so now when you launch using that AMI, new EBS volumes will be created and attached to the new instance

>[!error] Exam notes
>- AMIs are in **one region**
>- **AMI baking** is creating a AMI from a fully configured instance and application
>- AMI's cannot be edited, you need to launch an instance, change it then bake a new one from it
>- AMIs can be copied to new regions
>- remember permissions, you can grant access to specific accounts

