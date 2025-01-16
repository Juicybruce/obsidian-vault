This is a group of related features that can be enabled for **new buckets**
- versioning is enabled as well, neither this or object lock itself can then be **turned off**
- the architecture is Write-Once-Read-Many (WORM) - this means NO deletes and NO Overwrites

There are two ways it manages retention:
- **retention periods** 
- l**egal holds**
theses are two different things, you can have **both, one or neither**

Broad illustration:

![[Pasted image 20250116163157.webp]]
#### Retention Period

You specify a period in days or years

the two modes:
- Compliance - No changes AT ALL to the object version or the retention settings **even by the account root user**, until the expiry is over
	- VERY STRICT
- Governance - special permissions (`s3:BypassGovernanceRetention`) can be granted to allows lock settings to be changed
	- prevents accidental deletion, or enforce a less strict governance requirement

>[!error] It is VERY important to note the difference between Compliance and Governance modes

#### Legal Hold

You don't set a period, you just set a hold to be On or Off as a binary
- while ON you cannot delete or change object versions
