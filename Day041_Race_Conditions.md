# TOPIC
RACE CONDITIONS

# OVERVIEW
- They are an interesting conditions, which occur when limited resources are processed parallely.
- They are often found at places which tends to process the resource only once.

## EXAMPLE
An account gets to invite only 10 users, but the race condition allows for even more.

# ATTACK VECTORS
## BUSINESS LOGIC ABUSE
 - Logic issues such as Discount Tokens, Invites can be abused with Race Conditions
 - An attacker parallely opens 100 s of threads, and tries to send multiple requests simultaneously.
 - If the application is vulnerable, the user would be able to successfully exploit them.

## RACE CONDITIONS IN OAUTH 2
### READ
	- https://book.hacktricks.xyz/pentesting-web/race-condition#oauth2-eternal-persistence


# TOOLS USED
- Burp Suite's Intruder
- Burp Turbo's Intruder Plugin

# REFERENCES AND GOOD READS
a. https://medium.com/@pravinponnusamy/race-condition-vulnerability-found-in-bug-bounty-program-573260454c43
b. https://hackerone.com/reports/759247
c. https://book.hacktricks.xyz/pentesting-web/race-condition#oauth2-eternal-persistence	
