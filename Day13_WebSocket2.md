# TOPIC 
Web Socket Vulnerabilities Part 2

# OVERVIEW
Testing for IDORs
Denial Of Service

# TESTING
For IDORs, find all kinds of features and try out to find a IDOR in them.
Look out for UUIDs or SIDs in the fields of the request messages.

# IDOR example
- Consider a situation where an attacker and a Victim A are chatting with each other using web socket communication.
- The attacker would have an unique SID.
- If we change the SID of the attacker, to an SID of another victim, then a vulnerable website would send the
message from the Victim B instead of the attacker, to victim A.

# DENIAL OF SERVICE
The web socket allows any number of connections to be made with the server, which leads to over usage of the server
and may lead to Denial Of Service.

 - Try out sending multiple connection requests in a very short time, and this may lead to a lag in the application.

# ATTACKS

## UNSANITIZED INPUT FIELDS
There may be unsanitized input fields, which can be used to send crafted inputs, that execute on the server.

## MANIPULATING CONNECTIONS WITH THE SERVER
Some times, the server may resist your connection, when it catches you sending crafted or attack vectors.
You can try to reconnect to the server for more testing, by providing a spoof IP or  X-Forwarded-For: header.
An improper implementation will get you through.

## CSRF WEB SOCKET ACTIONS
Improper implementations of websockets, allows an attacker to send a cross domain request to the server, on
behalf of an victim.


