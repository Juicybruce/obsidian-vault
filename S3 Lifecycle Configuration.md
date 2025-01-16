You can design rules to change objects to improve costs

These are groups of rules that apply actions on buckets or groups of object when conditions are met:
- **transition actions** will transition objects to different s3 storage classes etc
- **expiration actions** will expire or delete objects

You can't use access as a condition, that is for **s3 intelligent tiering**

**Transitions**

This operates much like a waterfall:
![[Pasted image 20250116143632.webp]]
- note that **one zone IA** cannot transition into **glacier instant**
- can only go down, not back up
- smaller objects going from standard to IA, one zone or Intelligent Tiering might cost you more because of the increase to **minimum billing size**
- when using transitions, objects need to be in standard for 30 days before moving it to an IA class

