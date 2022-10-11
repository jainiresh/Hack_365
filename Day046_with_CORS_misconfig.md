# TOPIC
CORS misconfiguration

# OVERVIEW
- First thing to understand is CORS is not a securiity vulnerability, it is a kind of a feature that allows other 
cross domains to access restricted or sensitive information from the current website.
- Misconfigured CORS policy could lead to unintentional websites trying to access informations, from the domains, and
this is a security vulnerability.

# HEADERS
## ACCESS-CONTROL-ALLOW-ORIGIN
- Include Origin and a subdomain as it's value in the request, and check for this Header in the response.
If this header is not present, then forget CORS.

### VALUES
*
This is a wild card value
Here a normal-website.com would fail to fetch data, from it and With Credentials parameter too  would fail.

REFLECTED
When the websites put in the Origin field in the Request, gets reflected on this Field, then the domain may be vulnerable to CORS.

FIXED
Sometimes the websites whitelist cross domains, and if the attacker's not fall on it, it does not reflect its value.

## ACCESS-CONTROL-ALLOW-CREDENTIALS

This headers is responsible, for taking the cookies of the victim with the request from a cross domain.
If this header is not present, the website may still could be vulnerable to CORS, but may not be impactful.

THis must be set to true, for successfull exploitation.

# EXPLOITS
1. Arbitrary Origin Reflected & Credentials set to True

a. An attacker supplied "Origin" header is reflected in the Response Headers.
b. Access-Control-Allow-Credentials is set to "true"
c. This is the exploitable case and easily be exploited. 


2. Misconfigured Whitelisting

a. Assume that the "origin" header defined by the target allows any domain ending with "harshbothra.tech"
b. As a result of poorly implemented whitelist, an attacker can try providing following domain in the "origin" header like "attacker-harshbothra.tech" and if it reflects successfully, there's an issue with the implemented whitelist.

3. Null Origin 

a. If "Null" is accepted in the "Origin" header and is reflected back, this can be abused by an attacker. 


4. Some other Attack Scenarios with CORS: 

a. Breaking TLS with poorly configured CORS
b. Exploiting XSS via CORS trust relationships
c. Intranets and CORS without credentials

# LABS
- https://portswigger.net/web-security/cors

# GIT HUB TOOLS
- https://github.com/chenjj/CORScanner
- https://github.com/s0md3v/Corsy
- https://github.com/Shivangx01b/CorsMe

# REPORTS
- https://hackerone.com/reports/235200
- https://hackerone.com/reports/426165
- https://hackerone.com/reports/426147
- https://hackerone.com/reports/769058
- https://hackerone.com/reports/896093
- https://hackerone.com/reports/470298
- https://hackerone.com/reports/733017

# REFERENCES
a. https://portswigger.net/web-security/cors
b. https://book.hacktricks.xyz/pentesting-web/cors-bypass#pre-flight-request
c. https://portswigger.net/research/exploiting-cors-misconfigurations-for-bitcoins-and-bounties
d. https://medium.com/bugbountywriteup/think-outside-the-scope-advanced-cors-exploitation-techniques-dad019c68397
e. https://www.corben.io/advanced-cors-techniques/https://github.com/chenjj/CORScanner

