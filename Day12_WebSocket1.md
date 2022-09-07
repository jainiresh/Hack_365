# TOPIC
WEB SOCKET VULNERABILITIES

# NOTICE 
The Web socket vulnerabilities are divided into 3 parts.
This part consists of the basic info about web socket vulns.

# WHAT IS A WEB SOCKET ?
They are a network protocol that allows the client and server to enter into a 2 way communication.
The standard HTTP protocol, allows half duplex communication, therefore WEB SOCKETS came into the picture to 
bring forth full duplex communication.


# PROTOCOLS USED
ws://
wss:// (secure shell)
they are similar to HTTP and HTTPS respectively.

# CONNECTING STEPS
1) An initial HTTP request is sent with additional SOCKET headers like
	- Upgrade: Websocket
	- Connection: Upgrade
2) The server accepts it and responds with a 101 switching protocols type of response
3) This enables a websocket connection between the client and the server.

# WORKING WITH WEBSOCKETS
The traditional Burp Suite allows interception of web socket messages, and modifications to it.
There are extensions available, that helps you to tamper the websocket messages flowing through the browser.

# COMMON VULNS
- Denial of service
- Insecure communication
- Missing Access Contols and Auth checks
- Missing input validation in user controled data
- Lack of improper auth
- Tunneling
- Cross site web socket hijacking
- Server side issues
- Out of band issues

# REFERENCE
https://brightsec.com/blog/websocket-security-top-vulnerabilities/
