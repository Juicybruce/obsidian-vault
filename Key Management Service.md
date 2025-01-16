This is common service used by many services when they are doing any encryption

>[!error] Due to its common nature, you need to know it for exams

Regional and Public service

Generally tasked with creating, storing and managing encryption keys (symmetric and asymmetric) and can perform **cryptographic operations** with those keys

>[!error] Key concepts
>- KMS Keys are region locked and may never leave (but can be 'multi-region keys')
>- Keys can be **customer** or **AWS managed** Keys
>- Rotation happens automatically with AWS managed keys, but can be configured on customer managed keys
>- Aliases can be created for keys (also region specific )

>[!tip] 
>These keys never leave the service, they are always contained within and used from KMS

>[!error] Implements an american standard:
>**FIPS 140-2 (Level 2)** overall
>
>Memorise this, it will likely be on the exam

### KMS Keys 

These keys are logical and have ID's, dates, policy, description & state

These keys can only be used to encrypt or decrypt 4kB of data, they are really only intended to be used on very small scales like this

Usage of these keys is illustrated below:
![[Pasted image 20250116115627.webp]]
- note that the keys **never leaves KMS**, and are **never stored in plain text** 
- each operation has **seperate permissions**

### Data Encryption Key (DEKs)

These are created using KMS keys, and are used to encrypt data larger than 4kB

it is **very important to note**, KMS does not store these keys. They are created by and linked to a KMS key, then sent to you and discarded by KMS
- you do the cryptographic operations yourself

The proposed architecture is as follows:
![[Pasted image 20250116115929.webp]]

- KMS doesn't do any tracking or encryption key management for the DEK
- when you want to decrypt, you simply use KMS to decrypt the DEK, then use the DEK to decrypt the data
	- This is how other services do it


### Key Policy and Security

Key polices are a type resource policy and are often configured with a level of 'account trust' (an allow for the key itself for the account)

Identity polices are often quite granular, with encrypt and decrypt being different actions
- You might find that high security environments wants users to have one but not the other

