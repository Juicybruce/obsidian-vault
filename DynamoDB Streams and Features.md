A DynamoDB stream is a time ordered list of changes to the data in the table, like a log
- 24 hour rolling window that records INSERTS, UPDATES and DELETES

![[Pasted image 20250130144536.webp]]
- the view types will change **what gets recorded** in the stream log

**Triggers**

So these are event driven database architectures that can be implemented in a severless way

In AWS we use streams and **lambda**, where the function is the action that occurs in response to the **event**
- the event itself contains the data that got changed

![[Pasted image 20250130144823.webp]]