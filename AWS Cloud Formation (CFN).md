#### Basics

Cloud Formation is a tool that allows you to create **templates** that CFN then uses to create, update and delete infrastructure on a repeatable basis.

Templates are written in either YAML or JSON declarative files

There are many elements to a template, but a important ones are:
- **resources**, which are the actual services - This is required
- **description**, which is a free text section for describing the template
	- NOTE: if you have a description and a **AWS Template Format Version**, the description MUST immediately follow the format version in the template 
- **Parameters** prompt the user for values to be used
- **Mappings**, these allow the creation of lookup tables
- **Conditions**, to allow for decision making within the template
- **Outputs**, things that are presented when templates are applied

Functionally, CFN templates are a **list of logical resources**, which are then converted into a number of stacks, which then go and create a **physical resource for each logical resource they contain**
- Essentially your templates **define stacks** which contain logical resources
- It is then CFN's job to keep the **logical and physical** resources in sync
- If a stack is changed by applying an update, CFN will take action to make sure those changes are also applied to the physical resources that are represented in the stack

