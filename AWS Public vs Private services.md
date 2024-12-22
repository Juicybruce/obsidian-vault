This is referring to a network perspective only

Public services are access from **public endpoints**, but there is a distinction between them and the 'public internet'

AWS has a public and private zone, in which the services are divided:
- public zone has a connection to the wider public internet, and will use it as a transit medium
	- public services like s3 are contained here
- the private zone does not by default have any connection to the public internet, and contains private services like VPCs and EC2s
	- You can access or be accessed by the public internet in this zone if configured, but not by default