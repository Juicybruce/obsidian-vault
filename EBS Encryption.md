By default, the data on a block storage device is written exactly how the OS outputs it
- we can configure this data to be encrypted by KMS at rest

![[Pasted image 20250123121933.webp]]
- when a volume is created, the EC2 host decrypts the DEK key and stores in memory
- The only plain text data is in memory 
- The encrypted DEK is stored with the data 

>[!error] Exam Hints
>- Accounts can be set to encrypt EBS volumes by default
>	- Either with default key or choose a KMS key
>- Each volume uses this key to create a **unique DEK for each volume**
>	- All snaps and volumes from those snaps **use this same** DEK
>- You cannot change the volume to be not encrypted
>- the OS is **unaware** of the encryption, it always just sees plaintext. The encryption is done outside the OS



