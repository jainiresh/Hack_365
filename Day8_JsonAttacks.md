# TOPIC
JSON => JavaScript Object Notation

# Overview
They are used nowadays, to transfer data and all the modern works.

# ATTACKS
- Deserialization attacks
Best place to learn :
https://www.blackhat.com/docs/us-17/thursday/us-17-Munoz-Friday-The-13th-JSON-Attacks-wp.pdf

- JSONP attacks

- XXE if the attacks are prone to non sanitization of inputs.
Capture the request using a PROXY.
Change the Content Type to application/xml and insert a XML payload.
U can also use Burp Content Type convertor plugin


- XSS
Try diff payloads, and look out for non validated or unsanitized inputs.

- FILE reads
If JSON is improperly configured to read a file, it can be manipulated to read server side or local files.
{"user":"admin", "path":"/admin.html"} => {"user":"admin", "path":"/../../../../../etc/passwd"}

- Broken Access control and idors

- CSRF
Using fetch and poc for JSON attacks CSRF can be implemented

- Open redirection attacks

- Parameter tampering

- Response manipulation

- Session related attacks




# REFERENCES
http://www.infosecwriters.com/Papers/ASood_ExploitingJSON.pdf
https://owasp.org/www-pdf-archive/Marshaller_Deserialization_Attacks.pdf.pdf
https://www.websecgeeks.com/2015/10/attacking-json-application-pentesting.html
https://medium.com/@koumudi.garikipati/json-based-xss-84089141c136

# NOTABLE POINTS
    a. String Defracturing Attack 
    b. Malicious Hashing & Listing 
    c. Fused Proxy Attack: Domain Crossing
    d. JSON-XML Banner Grabbing
