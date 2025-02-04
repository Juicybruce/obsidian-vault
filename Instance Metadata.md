This is a service that is provided to ALL instances to access information from within EC2s that they usually wouldn't have access to

>[!error] The address is http://169.254.169.254
>the path is `/latest/meta-data`

The information includes:
- Environment data
- Networking data
- Authentication
- User-data

>[!error] This data is NOT AUTHENTICATED OR ENCRYPTED
>If someone has access to the EC2 cli, they can fetch this metadata
>

