>[!tip] Important Point
>Buckets are not encrypted, **OBJECTS** are

Encryption is done either **client** or **server** side (SSE) for data at rest (most data in transit will be encrypted)
![[Pasted image 20250116121214.webp]]
- with client side - the **CLIENT** will encrypt the data before its sent
- with server side - the objects will be encrypted on the s3 server when it is stored

There are several types of SSE
- SSE with customer-provided keys (SSE-C)
- SSE with Amazon s3-managed keys (SSE-S3) (this is the **default**) 
- SSE with KMS keys (SSE-KMS)

SSE-C:
![[Pasted image 20250116121825.webp|578]]
- the key is never managed by AWS, always discarded after use (this is some trust)
- AWS does the en/decrypt

>[!note]
>Its important to note that this is note the same as client-side encryption where the **client does the cryptographic work**
>
>AWS still receives your data in plain text, then encrypts it

SSE-S3:
![[Pasted image 20250116121959.webp|584]]
- s3 generates a unique key for each object (using AES256)
- s3 has a service managed key you have NO control over, this is used to encrypt the object keys (which are then discard)
- If you require key management or rotation control or any **role separation**, this will not work
  
SSE-KMS
![[Pasted image 20250116122446.webp|597]]
- the archietcure is similar, but the key is within your control
- this allows role separation, with full admins of the s3 bucket might not have access to KMS
	- you need access to the original KMS key to use the DEK to access the object
	- KMS allows very granular permissions for that KEY

>[!error] Key note summary for the exam
>![[Pasted image 20250116122729.webp]]
>
>- client-side - you handle everything, AWS sees nothing (this can be used incombo with SSE)




