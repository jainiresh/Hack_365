# TOPIC
Common Business Logic Issues 3 (Wrap)

# OVERVIEW
This is the final part of the series, CBLI.

# EXPLOITS
## PARAMETER TAMPERING
- Try to tamper the parameters, of critical fields like payments and test the reflections on the server and the
website
- Add unwanted and unnecessary fields on places that are critical, using HTTP parameter pollution and Mass assignment.
- Try out Response Manipulation to bypass 2FA (try this out! I really had got a bug in this)

## APP IMPLEMENTATION LOGIC EXPLOIT
- If an app accepts only json input, try changing it into an XML input, if the app accepts it, then XXE and XML based attacks
can be tried out.
- If an app is using DELETE method to delete something without a proper CSRF protection, try changing it into a GET or POST
method, and add an additional parameter like ?method=delete
- If an user id is passed on to a request, then try bypassing method based restriction using X-Method-Override.
- If you see an UUID, try mapping with similar things such as 1, 2, and 3.
- Try the HEAD method to bypass the authentication restrictions.

## DENIAL OF SERVICE SITUATION EXPLOITS
- Resource exhaustion, try consuming some resources infinitely.
- Try locking out accounts, by brute forcing or some other logic access.
- Try to kickout some other users, or ban from the application.
- App level DOS, by abusing certain features on the application.

# CONCLUSION
Briefly speaking, Application's business logic issues literally has no bottom to it.
There may be infinite number of logic issues, that varies from application to application.
My best advice is to stick on to an application for a longer period of time, and get to know the working of the application
from scratch to the highest knowledge.

Then try to find issues in them.

