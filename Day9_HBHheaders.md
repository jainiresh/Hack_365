#TOPIC
Hop by Hop request Headers

## TYPES
 - End to End headers
 - Hop By Hop headers

End to End headers :
 - Stored by cache.
 - Every request from cache, attaches the headers along with it.

Hop by Hop headers :
 - Single transport level connection
 - Not stored by caches

THe end to end headers are expected to be in the request, till the end.
THe hop by hop headers, are only used among the proxy servers.
And are added and removed my proxies.

GET /api/users/profile HTTP/1.1
Host: vulnerable-website.com
Cookie: sessionid=...
Connection: close, Cookie

This may provide unexpected results, as the cookie header may be dropped.

# AUTH BYPASS
If an application relies on a Header and Value in the request as a measure to check authentication, then abusing Hop
by Hop headers can be tried.

# FINGERPRINTING
Hit and trial of removing and adding request headers in requests, could fingerprint the details of the website, accurately.

# FINDING VULNERABILITIES:

Take an enpoint which requires a Header to give a particular response, it must provide a different response if
the Header is not present.
Eg : Cookie Header, an auth endpoint, with the Cookie header, gives 200 status and details of the user, and if 
its not present, then a diff status like 404, may be present.

This is a perfect spot to check for the vulnerability.
Give the authenticated req  a fire, with the cookie header like normal, except add the Cookie key to the connecition
value like
Connection : Close, Cookie

This may involve proxy servers or middlewares removing the Cookie headers to remove the Cookie headers completely,
and give the status where the Cookies were not present.

# ABUSINGS
## X-Forwared-For
The client Origin Ips are sent to the next proxy servers, as the values of the headers X-Forwarded-For:xxx.xxx.xxx.xxx
By adding, X-Forwarded-For to the Connection : close will sometimes make the X-Forwarded-For header by the intermediate
proxy servers, so the end server may not know the origin IP and may give out the results.

## DoS cache poisoning

## WAF BYPASS
Sometimes, WAF validates a request on presence of a request header, and dont on absence of it.

