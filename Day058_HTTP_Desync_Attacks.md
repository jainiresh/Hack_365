# TOPIC
HTTP DESYNC ATTACKS

# OVERVIEW

## HTTP REQUEST SMUGGLING
- As we all know, why HTTP request smuggling occurs, in case no, they occur because of the difference in the two server
accounting for Content-Length and Transfer-Encoding.

## FORCING DESYNC
To solve this, a universal normalization came into place that is,
In case if both Transfer-Encoding and Content-Length is placed on a request, then the latter (CL) must be ignored.

You can evade the above security measure, by tricking the front end server to not read the Transfer Encoding header.
SOmetimes sending the Transfer-Encoding header with a space appended before the colon, can be not read by the front end server
as Transfer Encoding, but the Back end could read it as TE and thus HTTP REQ SMUGGLE is possible.

# EXPLOITS

- Paths like /admin are blocked by the external users, therefore we can smuggle requests like "/admin HTTP/1.1".
- x-Forwarded-For: 127.0.0.1 are rewritten by the front end servers, therefore the smuggled requests can include the 
Header to access local host.

The other exploits are referred in the link in the REFERENCES.

# REFERENCES
https://www.youtube.com/watch?v=_A04msdplXs&t=11s
