# TOPIC
Bypassing Aws policies

# OVERVIEW
## AWS
- THey are a cloud service provided based out of Seattle, WA
- Makes up about 60% of the market
- Follows a typical IaaS service model
	- Shared security model
	- Owner takes care of hardware
	- Customer takes care of the data

## SERVICES
 - s3 buckets (storage)
 - lambda (code in the cloud)
 - Ec2 (Acts as host for OS)
 - RDS (DBs in the cloud)

## PENTESTING
### initial Access : Key compromise
 - Key left out in the open lead to the cloud
	- Github
	- Gist
	- Social Engg.
	- LFi/RFI
 - Once compromised, keys can be used to authenticate the environment.

### PUBLIC BUCKET BLOCKS
 - Allows anyone to access to your resources
 - Sensitive data could be stored in the public buckets by mistake

## BYPASSING S3 BUCKET POLICIES
- Attacker attempts to grab objects from bucket
- Bucket policy does not allow GET method, but do allow PUT policy
- Attacker modifies and allows new Bucket policies with the ARN of the target bucket
- Attacker PUTS new policy on the bucket
- Attacker is able to exfiltrate data from the bucket

## DEMO
Included in the video, whose link is provided below in the REFERNCES section

# REFERENCES
https://www.youtube.com/watch?v=OyEXjSxRB90
