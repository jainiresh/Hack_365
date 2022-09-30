# TOPIC
CRLF (Carriage Return Line Feed) Injection

# OVERVIEW
They are special characters
 - Carriage Return (\r)
 - Line Feed (\n)
They are not malicious characters, but can be used for malicious intent.
They are characters which are normally used on the end of a Line of the Request made by the client to the server,
but can be tricked by placing them in the input.

# ATTACK VECTORS
## XSS - Cross Site Scripting
- Assume the application is vulnerable to CRLF Injection and allows an attacker to inject an arbitrary Request Header which is reflected in response as well. 
Ex: www.magma.com/tech/somepage%0d%0aContent-Length:%200%0d%0a%0d%0aHTTP/1.1%20200%20OK%0d%0aContent-Type:%20text/html%0d%0aContent-Length:%2025%0d%0a%0d%0a%3Cscript%3Ealert(1)%3C/script%3E 

- This may result into a Cross-Site Scriptin

## INJECTING ARBITARY COOKIES
- Similar method to the previous one can be used to set arbitary cookies in the application, which could lead to 
unexpected behaviours.

## HTTP RESPONSE SPLITTING
- The special characters, can be used to trick the server to think that it is an Line's end, and then we can add a
HTTP Request Header to trick the server to think it  a new Request and Get response for it Too !

- https://book.hacktricks.xyz/pentesting-web/crlf-0d-0a#an-example-of-http-response-splitting-leading-to-xss

## LOG POISONING
- An attacker can input fake log entries and try to mess up the logs by injecting various CRLF sequences. 
- Example: https://book.hacktricks.xyz/pentesting-web/crlf-0d-0a#an-example-of-crlf-injection-in-a-log-file

## WEB CACHE POISONING
- This attack can also be used to add arbitrary headers and cause cache posining. Let's discuss this more during Web Cache Poisoning Series.


# TOOL USED TO FIND CRLF INJECTION
- https://github.com/dwisiswant0/crlfuzz

# REPORTS
a. https://hackerone.com/reports/858650
b. https://hackerone.com/reports/237357
c. https://hackerone.com/reports/217058
d. https://hackerone.com/reports/245485
e. https://hackerone.com/reports/590020
f. https://hackerone.com/reports/332708
g. https://hackerone.com/reports/53843
h. https://hackerone.com/reports/52042
i. https://hackerone.com/reports/446271

# REFERENCES AND READS
a. https://book.hacktricks.xyz/pentesting-web/crlf-0d-0a
b. https://medium.com/cyberverse/crlf-injection-playbook-472c67f1cb46
c. https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/CRLF%20Injection
d. https://medium.com/bugbountywriteup/bugbounty-exploiting-crlf-injection-can-lands-into-a-nice-bounty-159525a9cb62
