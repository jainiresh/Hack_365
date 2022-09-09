# TOPIC
Web Socket Vulnerabilities

# OVERVIEW
As we know we have been learning about WEB SOCKET vulnerabilities,

# ATTACK SURFACES

## CONNECTION BASED ATTACKS 
- Usage of ws:// instead of wss:// (same scenario where HTTP is used instead of HTTPS)
	- By sending data through the SSL/TLS, the wss prevents the Man In THe Middle Attacks
- Trying to intercept the sensitive datas sending throught the ws protocol of other users, and creating a POC of
Man in the middle attack.

- If wss:// is used, try degrading it to ws:// and try the same scenario of request.

## CROSS SITE SCRIPTING ATTACKS
- Always check reflections on the page, based on your data.
- Include Blind XSS and test them.
- Check for input validation and try to bypass them using special characters

## SERVER SIDE INJECTIONS
- Check for all the Web Socket based parameters for potential Injection platform
- Fuzz the parameters for additional information and fingerprinting.

## ORIGINS BYPASS
- If there is no Access-Control-Allow-Origin headers on HTTP requests and responses, for CORS, we can always check
if we can connect through the socket connections from an evil / Malicious site.

# LABS
https://portswigger.net/web-security/websockets

# REPORTS BASED ON WEB SOCKETS
- https://hackerone.com/reports/178990
- https://hackerone.com/reports/409850
- https://hackerone.com/reports/395729
- https://hackerone.com/reports/163464
- https://github.com/github/securitylab/issues/65
- https://hackerone.com/reports/512065
- https://hackerone.com/reports/1023669
- https://hackerone.com/reports/86283

