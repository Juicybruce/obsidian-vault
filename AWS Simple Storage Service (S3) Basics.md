This is a **global service platform**, with your data being held in a specific **region**

Default a **public service** (though buckets are private by default), unlimited data storage and can be access by multiple users at once

Highly scalable from next to nothing to millions of objects, economical and can be access via various means

##### Objects in S3

All elements in an s3 are **objects**, which are made up of:
- **Key**, similar to a file name, this uniquely identifies an object a bucket
- **Value**, which is the actual data of the object being stored. This can range from **0 bytes to 5 terabytes**
- Other attributes include **Version ID, Metadata, Access Control** and **subresources**

##### Buckets in S3

Buckets are created in a **region**

This means that your data exists in that region and will **never be replicated elsewhere** unless you configure it to
- This is important for **data sovereignty** 
- Any data loss is also confined to that region

Bucket names are **globally unique**, no two buckets **anywhere** can share a name
- names must also be 3-63 characters
- start with lowercase letter or number
- can't be formatted like an IP address

Buckets have a flat structure, there is no directory system.  The UI or a listing might present a bucket as a filesystem but that is **logical only**
- same with file types

General limits include:
- 100 bucket soft limit
- 1000 bucket hard limit per account


##### Patterns and Anti-Patterns

S3 stores **objects** not **files or blocks**
- S3 is only suitable for when you are storing media or other objects that are individually and specifically accessed, you can't access and browse it like a **file system** or mount it to use as block storage

S3 is great for:
- Large Scale data storage
- distribution 
- uploads
- offloading storage away from compute storage 

It should be the default thought for **input or output** from other AWS services

