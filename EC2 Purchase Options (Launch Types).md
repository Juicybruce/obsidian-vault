#### **On Demand** - default
no specific pros or cons
![[Pasted image 20250123125658.webp]]
- clients on this all share the same hosts, allowing AWS to efficient allocate the resources
- instances charge per second while 'running'

#### Spot Pricing

This is AWS selling the spare unused capacity on EC2 hosts at a discount:
![[Pasted image 20250123130139.webp]]
- you can offer more as maximum, but you always only pay the spot price
	- If your maximum goes below the spot price, your EC2s are terminated
- Spot instances will always be terminated at some point, your **workloads must be able to tolerate interruption**

### **Reserved Instances**

This is designed for long-term and known resource consumption
![[Pasted image 20250123130645.webp]]
If you purchase a reservation, you will get a discount for that reservation but you will be billed whether you use it or not
- you can commit to 1 or 3 years and will be billed for the entire time
- you do get partial discount on instances that are **larger** than your reservation
- You can pay **all upfront**, **no upfront** or **partial upfront**

There are now other non-standard reserved instances:

#### **Scheduled reserved instances** 
these are useful for known long term usage, where you don't need something to run constantly
![[Pasted image 20250123131638.webp]]
- you can reserve the capacity to just use those blocks

#### Capacity Reservation

This consists of two components: billing and capacity, and they can be used in conjunction or separately

its important to remember that when filling **capacity**, AWS will prioritise those with **capacity reservation**. 
![[Pasted image 20250123141633.webp]]
- regional reservation gives you a billing discount but no capacity reservation
- Zonal reservations give both, but you are restricted to the one AZ for the benefit
- On-demand capacity reservation bills you for the reserved capacity
- you aren't getting any **billing savings** here, you are just getting the capacity guaranteed

#### **Dedicated** Hosts

Here you pay for the host, the instances running on it is irrelevant
![[Pasted image 20250123131054.webp]]
- some applications are licensed on the number of sockets or cores
	- Host affinity (instances stay on the same host always) also deals with licensing issues

#### Dedicated Instances

This is a sort of middle ground between shared hosts and dedicated hosts
![[Pasted image 20250123131317.webp]]
Your instances run on a host with **no other customers**, but you don't pay for the host itself
- there are several extra fees plus additional running fees
This is mostly just to guarantee no sharing of hardware


### EC2 Savings plan

Here you take an hourly commitment for a 1/3 year term

you can do it for **general compute** (for many services) or specifically EC2

Its basically a minimum spend, which gives you discounts until you have spent that minimum - at that point you begin to spend at the on-demand rate

>[!error] Tip
>This might be a way for a business that is migrating away from EC2 to other compute architectures 