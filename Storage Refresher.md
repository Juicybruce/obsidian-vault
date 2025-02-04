Direct storage is connected to the Instance Host, called **instance store**
- this storage can quite easily be lost if the instance moves host or there is a hardware of AZ failure

- The alternative is **network attached storage**, which is seperate from the instance itself (in Elastic Block Store)

There is a division between **ephemeral** and **persistent storage**. EBS is the latter, Instance Store is the former

**Block storage**
- volume is presented to the OS as a collection of blocks. **Mountable** and **bootable**
- Usually an OS will put a file system on top of this
- This is often provided by EBS

File Storage
- Presented as a file share that has structure. Mountable but **not bootable**

Object storage
- collection of objects with metadata
- flat and unstructured, not mountable and not bootable

Performance:
![[Pasted image 20250123094454.webp]]
- IO - block size 
- IOPS  - the speed at which a block can be copied in or out (how many blocks per second)
- throughput - the total speed of the storage (combined from the other 2)

