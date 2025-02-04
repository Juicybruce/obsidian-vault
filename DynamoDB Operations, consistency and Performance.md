![[Pasted image 20250130142915.webp]]

**Operations**

**Query** this is one way to retrieve data:
![[Pasted image 20250130143240.webp]]
- you have to always query a single partition key
- you are more efficient when you use fewer queries, because you cosume capacity at a minimum cap

Scan moves through the table and returns the items for a particular attribute that matches
![[Pasted image 20250130143612.webp]]
- capacity is used for every item **scanned**, whether or not the item is returned


![[Pasted image 20250130144045.webp]]
- eventually consistent reads are half price because any of the nodes can be read at any time
- strongly consistent reads are always accurate because it reads only from the leader node, but they are full-priced

- Depending on the application, you could used eventual, but some applications cannot risk stale data

