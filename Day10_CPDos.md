# TOPIC 
Cache Poisoning Denial Of Service

# OVERVIEW
This type of attack is really simple to understand, where the an attacker sends a request to a legitimate content page
with an malicious header key along with its value.

The cache server recieves it, and since it is the fresh copy, it forwards the request to the origin server.
The origin server on seeing the malicious headers, send an error response back to the cache server.
The cache server thus, stores the error message and returns the user the same error message even when,
the Malicious header is not present.

# TYPES of Attacks
## HTTP Header Oversize (HHO)
This attack is possible because there are no restrictions on HTTP request header's size.
FOr this attack to work, the size of the header must be larger for the origin server to reject it, but at the same
time smaller enough for the cache server to pass through.

The origin server, sends an error message for the request and this get cache poisoned in the cache server.

## HTTP META CHARACTERS (HMC)
Here, The malicious header would have some special metacharacters like \r or \n which the origin server rejects, and t
the error is store on the cache server and thus getting poisoned.
Characters used :
 - \r
 - \n
 - \a

## HTTP METHOD OVERRIRDE ATTACK
Http methods can be changed or overridden on reaching the origin server or proxies, by different Headers such as :
 - X-HTTP-Method-Overridde
 - X-HTTP-Method
 - X-Method-Override

By overriding the methods like "X-HTTP-Method-Override": PUT, the origin server may throw an error, and this
may get cache poisoned at the cache server.


# MAIN DETECT LOGIC
Find a difference in response, using manipulation of Headers and their values.
Find a unkeyed input, which is not used by the cache to detect the request.
Once the poisoning is identified, then try out XSS and delivering them to the victim by cache poisoning

# TOOLS
## BURP SUITE EXTENSION
Param Miner -> To detect difference in GET request responses, by manipulating headers

# RESOURCES :
## GOLD MINE :
 - https://portswigger.net/research/practical-web-cache-poisoning
## THEORY
 - https://cpdos.org/
