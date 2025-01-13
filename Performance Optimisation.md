#aws 

### Multi-part Upload

The most common way to add a file to s3 is using a single PUT upload. This has a couple of issues:
- This utilises a single stream of data, so quite fragile
- if the stream fails, the uploads fails and requires a full restart
- Single streams might run much slower than the two points are capable of
- 5GB is the limit to a single stream

The solution is **Multi-part uploads**
- you break the blob up into seperate parts (you can only do this for blobs larger than 100MB)
- You can split the upload into up to **10,000** parts (ranging from 5MB to 5GB)
- last part can be smaller than 5MB
- Each of these parts and streams can be restarted if necessary without interrupting the rest
- The transfer rates are **much higher**

### S3 Accelerated Transfer

Data transfer from s3 to users might take slow or inefficient routes across the public internet

The eligibility for this requires:
- the bucket name cannot contain periods
- the bucket name must be DNS compatible

Once switched on, user requests will **avoid** the public network and will go to the closest and best performing **AWS Edge Location** and use the AWS network instead
- because this network is designed to connect the various regions, the resulting traffic is much improved in speed and latency

The performance gains INCREASE the worse the initial performance, eg, if you are going from Europe to Australia, the benefits are quite high, vs just Japan to Aus