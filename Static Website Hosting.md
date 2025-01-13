Usually we access s3, we are using the AWS API

Via this option, you can access objects via HTTP, allowing it to be used as a website accessed over the web

Once you enable it, you just need to set **index** and **error** documents
- A website endpoint will be generated once you enable this feature

>[!tip] Custom Domains via Route53
>You can set a custom domain, but your bucket name **matters**. The bucket name and domain name must **match**

Two scenarios where this feature is very useful:
- **offloading** - where you offload many static resources on an otherwise dynamic page (images or other media), and put them on the s3 bucket
	- The media is retrieved from s3, not the compute service, usually much cheaper
- **out-of-band pages** - you can host error pages or other static content to be served out of s3 when the main server might not be able to do so

