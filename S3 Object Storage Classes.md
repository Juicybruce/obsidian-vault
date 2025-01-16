#aws 

#### **S3 Standard**
- Data is replicated across at least 3 AZs
- 99.999999999% durability
- MD5 checksums and Cyclic Redundency Checks (CRCs) are used to detect and fix corruption

>[!note] HTTP Response
>S3 will respond with a 200 status if your object has been **stored durably**

Billing:
![[Pasted image 20250116134849.webp|472]]
- you don't get discounts but you don't get penalised for access usage

Retrieval 
- millisecond 'first byte' latency when data is requested
- objects **can** be made publicly available

>[!error] Exam note
>Standard should be your option for frequently accessed data which is important and non-replaceable
>
>This should be your **default**, you should only really change for very specific reasons

#### S3 Standard Infrequent Access (IA)

This is **mostly the same as standard**  with cheaper storage, except:
- there is an **added retrieval fee** per GB
- You are billed for a minimum time and size per object, no matter how large or long, you are billed for 30 days and 128Kb per object
  
>[!error] Exam note
>Standard-IA should be your option for **long-lived data**, where **access is infrequent** but the data is still data which is **important and non-replaceable**


#### S3 One-Zone-IA

This is similar to Standard-IA  with cheaper storage except for:
- **data is stored in one AZ** instead of being replicated across 3
- still as durable, but only if the AZ doesn't go down
  
>[!error] Exam note
>One-Zone-IA should be your option for **long-lived data**, where **access is infrequent** but the data is still data which is **non-critical and replaceable**


#### S3 Glacier - Instant Retrieval 

This one is very similar to Standard IA (3 AZ's replication) with cheaper storage, but:
- access costs are even higher, though you can still access you data immediately 
- minimums time billed goes up to 90 days

#### S3 Glacier - Flexible

This one is very similar to Standard IA (3 AZ's replication) with cheaper storage, but:
- The objects are **cold**, they are not **immediately available** and cannot be made **publicly available**
	- if you want them, a retrieval process has to be invoked at different costs and retrieval times:
		- Expedited (expensive, 1-5mins)
		- Standard (regular, 3-5hours)
		- bulk (cheaper, 5-12 hours)
- This means our first byte latency is **minutes** not **milliseconds**
- Minimum object billing 40kb size 90day time

#### Glacier Deep Archive

Where the Glacier - Flexible the object are **cold**, here they are **frozen**
- objects are billed at 40KB size and 180day minimum
- retrieval is like the other glacier types but:
	- standard is 12 hours
	- bulk is up to 48 hours
- first byte latency is **hours or days**

#### S3 Intelligent-Tiering

This allows objects to be stored in 5 different tiers, decided **per object**:
![[Pasted image 20250116142721.webp]]
- the objects are monitored for their use, and moved between the tiers depending on their usage
- There are management and automation costs 

>[!error] Exam note
>Intelligent-Tiering should be your option for **long-lived data**, where **access patterns are changing or unknown**