This product logs all API calls or activities within accounts as **CloudTrail Event**

The default (and free) **event history** that is stored is 90 days of these events

>[!error] This service is NOT REALTIME
>
### Events

These are either **management**, **data** or **insight** events

Management events are all operations performed on resources within an account, also known as **control plane operations**
- EG, creating an EC2, terminating and EC2

Data events are information about operations on or in a resource
- EG, s3 uploads or access

>[!note] 
>By default only management events are maintained, as data events are **much** higher volume

### Trails

These will log events within the region which it exists:
- you can create **all region** trails that are managed as a single logical trail, but is actually many seperate trails in each region

You can also configure a trail to pick up **global service events**, so it will consume the logs from their own region **and** the global services

Log information can be stored in s3 as a compressed JSON format if configured

It can also integrate with CloudWatch Logs to additionally use CloudTrail as a source for log streams

>[!tip] Organisational Trails
>A newer feature of CloudTrail is to create these **Organisational Trails**, which allow all events from within all the account in the organisation to be collected as one

![[Pasted image 20250109102044.webp]]

>[!error] CloudTrail Configuration (Important for Exam)
>All configuration is done by making custom trails, if you do not, you only get the defaults:
>- 90 days storage (**no s3 long term storage**)
>- Data events are not registered
>- Global Service Events (from IAM, STS, CloudFront) are not registered