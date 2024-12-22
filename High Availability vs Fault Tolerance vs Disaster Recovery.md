![[Pasted image 20241219102408.webp]]
### High Availability

The general definition is that an HA system aims to **ensure** an agreed level of performance (usually measured in **uptime**) for a **higher than normal period**

- there is a common misunderstanding that HA means that it will **never fail** or that customers will **never experience downtime**. This is not the case

It is important to note that HA systems might haave disruption to the end user (while resources are swapped out automatically after failure for example), but this does not matter. What matters is the overall performance of the system

![[Pasted image 20241219095858.webp]]

### Fault Tolerance

This is similar to HA, but not identical. The general definition of a system that has FA is one that **continues to operate properly** in the event of the **failure of some** of its **components**

These systems are designed to **eliminate** user disruption in cases where HA is not enough. Under HA, a failure could be very quickly resolved, but any interruption will cause a disruption to users or systems particularly sensitive to it. 

Example of this would be added redundancy to a system (like in an **active/active** configuration), so that if many components fail, their copies are still running and working for users.

Implementing FT is much more expensive, as you first need to implement HA, then design the system to cope with the eventual failures without any hiccups to service.

As a systems architect you need to understand what the client needs, as they might not have a good understanding of what these terms mean
- Pursuing FT when HA is all that is needed is wasting a lot of money

### Disaster Recovery

A set of tools, policies and procedures to **enable the recovery** or continuation of **vital systems** **following a natural or human-induced disaster**

This is split into two parts:
- Pre-planning
	- This needs to be exhaustive, as you want to reduce the amount of decision making made in a disaster scenario
- DR Process itself

These systems are designed to keep the **valuable or non-replaceable** elements of your systems safe

These policies should be tested and refined regularly
