# TOPIC
HACKING AWS CLOUD

# OVERVIEW
## FINGERPRINTING
This is the initial stage of Hacking AWS, and it involves gathering a lot of information about the Aws Cloud.
Some of the juicy information of Cloud are :
 - AWS account Ids
 - ARNs
 - IP addresses
 - Role names
 - Other AWS related infos.

## LOGIN URLS
AWS provides a number of different types of login urls for its users to login to the AWS console.

IAM USER SIGN IN LINK (name) => https://name.signin.aws.amazon.com/console
IAM USER SIGN IN LINK (account ID) => https://accountid.signin.aws.amazon.com/console
AWS SSO Start page : https://name.awsapps.com/start

## PUBLIC CODE REPOS
Public code repositories belonging to the target organisation could contain artifacts related to AWS accounts such as ARNs (Amazon Resource Names). Gitleaks is a tool which comes extremely useful in such situations. In fact, OpenDevSecops official Gitleaks Docker Build contains prebuilt configuration files that can be used to enumerate AWS resources. Here is an example:

```
docker run opendevsecops/gitleaks --config=/run/configs/aws-enum.toml --github-org=target --exclude-forks -v

NOTE: Gitleaks is great but it is a memory hog. Sounds like something that could be automated with pownjs in the future.
```
You can use recon from the pown toolkit to quickly find github account you would like to target.
 Here is an example how this could work:

```
pown recon t githublistmembers <target>
pown recon t githublistrepos <target|member>
```
## WEB SEARCH ENGINES
### DORKS
- "arn:aws" target
- ".amazonaws.com" target
- "arn:aws" target site:trello.com   [For more targeted results in trello board]
- target inurl:/_plugin/kibana site:es.amazonaws.com

## pown RECON
pown recon t zoomeyescrapesearchresults target

# REFERENCES
https://github.com/opendevsecops/guide-aws-hacking
