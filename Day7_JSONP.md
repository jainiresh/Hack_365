# TOPIC
## JSON PADDING ATTACKS


## Overview
JSONP => JSON with Padding, they are nothing but JSON data, but along with a function.
The usage of JSONP's are decreasing, but still a large number of websites are using it, but many are replacing it 
with JSONP.

## Understanding
According, to Same Origin Policy (SOP), a JSON data from one site/domain, cannot be read or accessed by another domain
or website.
For the data to be shared or read from a cross site, there are methods.
This can normally be implemented using 2 ways :
- Cross Origin Resource Sharing Policy
- JSON with Padding

In JSON with padding, the normal JSON data are enclosed within a function.
Therefore, they are read from a cross site, using the script function like a javascript.
SO, when the function itself is read, the JSON data inside the function as variables or constants are also read.

## FINDING JSONP
Finding JSONP, may be a bit easier task, as they could easily be found on the HTTP history.
 - One can give a good surf on the history and pickup the JSONP types.
 - Try changing the ?format=json files to ?format=jsonp
 - Try finding endpoints that contains paths such as ?callback=...

# ATTACKING
Create a html page, and using the script tag, and also defining the function before using the script tag, can fetch the
data.
If you are blocked or your access is denied, then you can try removing the Referrer header.

## SECURITY RISK
Using JSONP , similar to the CORS attack, we can steal sensitive informations from the user logged in.
If the JSONP contains user specific sensitive information, it may lead to a security risk.

## Reference Links
https://infosecwriteups.com/exploiting-jsonp-and-bypassing-referer-check-2d6e40dfa24
https://www.sjoerdlangkemper.nl/2019/01/02/jsonp/  -> Learn here
https://securitycafe.ro/2017/01/18/practical-jsonp-injection/

# LABS
Try out using this link on your own :
https://demo.sjoerdlangkemper.nl/jsonp.php

# REPORTS
https://hackerone.com/reports/10373
