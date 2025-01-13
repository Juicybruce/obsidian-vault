#aws #programming 

This is a public service, meaning it can be used from other AWS services or on-premise 

This service is for storing, monitoring and access logging data
- Within AWS, many services have **built-in integrations** to log into CW Logs
- Outside AWS, you can use the **Unified CloudWatch Agent**

**Metric Filters** can be generated based on the logs being ingested

Architecturally, CW Logs is structure like this:
![[Pasted image 20250109100740.webp]]
- **Log events** are registered, then 
- stored in **log streams**, which are ordered sets of log events for a specific source 
- **Log groups** are containers for related **log streams**, 
	- also stores configuration settings such as permissions etc (which will also apply to log streams container within) AND
	- **metric filters** which will be generating **metrics** which can be used to trigger **alarms**