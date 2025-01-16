this feauure lets you configure event notifcaitons on a bucket

When enabled, events will be generated from things happening in a bucket:
- these can be sent to SNS, SQS or Lambda
- can happen when an object is **created**, **deleted**, **restored from glacier** or **replication starts, finishes fails etc**

We configure an Event Notification Config:
![[Pasted image 20250116151736.webp]]
- The target resource needs to allow s3 principal access