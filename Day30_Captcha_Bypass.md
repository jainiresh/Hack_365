# TOPIC 
CAPTCH BYPASS TECHNIQUES

# OVERVIEW
## WHAT IS A CAPTCHA ?
- It is a "C"ompletely "Automated" "P"ublic "T"uring test to tell "C"omputers and "H"umans "A"part.
- It is basically a security measure to prevent the automated bots, to access instead of a human.
- It is used to prevent any kind of digital entry from a remote space.

## USE ?
- Used to prevent automated attempts to break in to the application or a particular feature.
- Used to prevent brute force attacks on any part of the application or the whole.


# CAPTCHA BYPASS TECHNIQUES
## SERVER SIDE MISCONFIGURATION ON VALIDATING
- Some applications accept CAPTCH from the client side, but they dont validate it on the server side.
- This may lead to an easy bypass and hence brute force attacks can be carried out.

## MISSING CAPTCHA FIELD INTEGRITY CHECKS
- There are multiple situations relatable to this one.
- Certain applications check only the length of the captcha value, not it's content.
- Certain applications check for the presence of the captch parameters, but not it's value.
- Simply sending an empty captcha parameter, or an arbitary value with the same length as the normal captch values, 
  could do the job.

## HTTP VERB MANIPULATION
- Try changing the verb of the HTTP request (POST -> GET, or GET -> POST).

## REUSABLE CAPTCHA
- Just check if the same captcha can be used for multiple number of times.
- Sometimes, when we capture the request, and untill letting the captcha go, we can reuse the captcha any number of times.

## USING HTTP REQUEST HEADERS
- Try using different HTTP request headers like, X-Forwarded-For:, X-Original-Ip: to bypass the captcha

## OTHER TECHNIQUES :
- OCR enabled bots, Human Based captcha solving techniques can be used or automated to solve captchas.

## CONVERTING JSON TO NORMAL REQUEST
- COnverting Json to normal request, could grant you a captcha bypass.

# RESOURCES
a. https://book.hacktricks.xyz/pentesting-web/captcha-bypass ( a good website )
b. https://medium.com/@honeyakshat999/captcha-bypass-techniques-f768521516b2
c. https://cobalt.io/vulnerability-wiki/v2-authentication/captcha-bypass-x-forwarded-for
d. https://medium.com/bugbountywriteup/bypassing-captcha-like-a-boss-d0edcc3a1c1
e. https://www.codementor.io/@harshittyagi/solving-captcha-with-web-automation-10v3rnvrf9
f. https://www.blackhat.com/docs/asia-16/materials/asia-16-Sivakorn-Im-Not-a-Human-Breaking-the-Google-reCAPTCHA-wp.pdf
g. https://www.iosrjournals.org/iosr-jce/papers/Vol22-issue3/Series-4/D2203042329.pdf
