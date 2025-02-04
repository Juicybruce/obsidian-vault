This is a Database as a service product
- a **noSQL** product
	- can handle key/value or Document model
- No managed servers, you get get the DB itself
- Either **manual / automatic** provisioning of performance or **on-demand**
- Extremely fast (SSD based)
- You can even do event-driven data changes

![[Pasted image 20250130142255.webp]]
- every item has to use the same primary key in a DDB table
	- the rest of the data can be whatever you like (many attributes and values) up o 400kb
	- DynamoDB has no rigid schema
- Capacity is measured in read/write speeds


- on-demand backups are like RDS snapshots
	- restoration can be Cross region
- Point-in-time recovery (not on default) will take automatic snapshots out to 35 days old
	- restoration is within 1 second

>[!error] EXAM 
>If you see NoSQL or Key/Value, DynamoDB is likely to be your answer
>If you see relational data, DynamoDB is NOT your answer
>
>You don't have SQL for accessing the data in DynamoDB
>
>Billing is done on the resources of storage, read/writes etc



