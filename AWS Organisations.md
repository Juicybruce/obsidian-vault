This is a way of organising and structuring **many AWS accounts**

Usually each account would have its own set of users, payment details etc, but this allows you to consolidate all of this

The process for creating and adding accounts to an organisation:
1. You use an account to create the organisation; this account become the **management (master) account**
2. You then invite other accounts into the organisation
3. these invites are accepted by the other accounts

>[!tip]
>it is important to realise that while an account is used to **make** the organisation, organisations do **not exist within accounts**, they are a overlying structure

You can create accounts directly within an organisation, which **bypasses the invite/accept** process

#### Organisational Structure

Containers can be created within organisations that help organise member accounts

These containers are arrayed hierarchically with an **organisation root** container at the top

**Organisation Root** can contain member/master accounts but can also contain **Organisational Units**

Organisational Units can themselves contain member/master accounts, but can also contain other OUs
- this allows complex nesting 

#### Consolidated Billing

Member accounts can pass through their billing details to be handled by the master account (also known in this context as the payer account)

**Reservations** (pre-booking services) and **volume discounts** can apply at the organisational level

#### User Logins

The **best practice** for organisations is to have 1 account that has all the **IAM users** (that can be accessed via **federated access**) then have roles those users can assume in all the other accounts:

![[Pasted image 20250108132154.webp]]

