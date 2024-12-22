AWS global infrastructure is divided into:
- Regions
	- loose geographical area that has a full deployment of all AWS services
	- A regional service will be interacted with within that region (an EC2 exists within a regional data center)
- Edge locations
	- smaller locations that have some services to allow lower latency for customers

All of this is connected for very high speed networking AWS has built

Services are either **regional** or **global**

Regions are **fault isolated** so a failure in one wont effect another. They are also governed by the **governance** of where they are located and the data wont move between regions

Availability Zones are additional isolations with each region, giving fault tolerance to more local outages if your services are multi-AZ deployed



