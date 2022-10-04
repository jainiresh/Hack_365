# TOPIC 
COOKIE BASED AUTHENTICATION VULNERABILITIES

# OVERVIEW
- Cookies had become an integral part of a stateless architecture, of a web application.
- They are the primary keys or the identifiers of an user or a common identifier for a group of users or things.
- However, nowadays Cookie based authentications are replaced by token based Authentications.

# VULNS

## XSS
- If a cookie parameter is reflected on to the application, then changing the parametr to a XSS payload, would result
in a XSS.

## INSUFFICIENT SESSION MANAGEMENT
### SESSIONS DOESN'T EXPIRE
 - On Server side only
 - Both on client and server side
 - LONG SESSION EXPIRY
### SESSIONS DONT'T EXPIRE ON PASSWORD RESET / CHANGE
 - If an account is compromised, the first legible thing an user would do, is to change his account password
 - If the session tokens doesn't expire, the attacker could revert back the change in password, and could chnage acc.
to his own.

### CONCURRENT SESSION/ PARALLEL LOGIN
 - The application allows multiple sessions and logins

## SESSION FIXATION
 - The attacker tricks the user to use a Session Identifier known to the attacker.
 - READ : 
```
https://secureteam.co.uk/articles/web-application-security-articles/understanding-session-fixation-attacks/
```
## PRIVIILEGE ESCALATION
### HORIZONTAL
- Assuming cookies value gives them access to a particular organization
- Changing these values sensibly, could give you access to other organizations.

### VERTICAL
- Assuming cookies value to determine the role of the user "User".
- Altering the values could escalate the role of the users.

## IDOR
- Assuming the cookie value contains parameters such as "user_id", changing them could give you details about the different user id.

## MISSING COOKIE SECURITY CREDENTIALS
- Missing HTTP Only Flag
- Missing Secure Flag
- Missing same site flag

## GUESSABLE / WEAK COOKIE
- Check the randomness of cookies, by making the application issue mulitple cookies and analyzing them.

## FILE INCLUSION
- If the cookies are used to define Server Side attributes, try to include a file in the server
- READ : https://medium.com/@tehmezovismayil/cookie-based-php-local-file-inclusion-bug-bounty-553f8b38d4dc

## SESSION PUZZLING
- Using the public page cookies to authenticate the sensitve pages too !
- READ: https://github.com/jainiresh/Hack_365/blob/master/Day16_SessionPuzzling.md

## PADDING ORACLE ATTACKS
- READ: https://book.hacktricks.xyz/pentesting-web/hacking-with-cookies#advanced-cookies-attacks

## CBC-MAC/ECB Encryption
- READ:  https://book.hacktricks.xyz/pentesting-web/hacking-with-cookies#advanced-cookies-attacks

## AUTH BYPASS - COOKIES NOT GETTING VALIDATED
- Try accessing some protected resource by removing cookies
- Try accessing sensitive resources by using GET requests

## SQLI
- READ: https://resources.infosecinstitute.com/topic/cookie-based-sql-injection/

## DOS
- Forcing the server to process cookies larger than the restricted cookie size.
- READ: https://blog.innerht.ml/tag/cookie-bomb/

## PARAMETER POLLUTION
- Trying out parametr pollution in the cookies instead of the URL like Cookie value :
```
userid=attacker&userid=victim
```

## MASS ASSIGNMENT
- Similar to the parameter pollutions, however here multiple user_ids are added in the same field.

## ARBITARY COOKIE INJECTION
- Try injecting arbitary cookies using techniques such as CRLF injections, which could lead to vertical privilege escalation sometimes.

## COOKIE LENGTH VIOLATION
- Could cause Buffer Overflows, as cookies are places which could lack length checks on the server side.
- READ: https://docs.imperva.com/bundle/on-premises-knowledgebase-reference-guide/page/cookie_value_length_violation.htm

## INSECURE DESERIALIZATION
- If cookies are using serialization, try to deserialize them and change them sensibly
- READ: https://portswigger.net/web-security/deserialization/exploiting

## SESSION DONATION
- An attacker, would give out his session to trick the user he is working on his own account, but actually he works on the attackers'.
- READ: https://book.hacktricks.xyz/pentesting-web/hacking-with-cookies#session-donation

## SENSITIVE DATA STORED IN COOKIES
- Check for PII information of users stored on cookies
- Information like
 - Email
 - Phone number
 - Address
 - Mobile number
 - Pincode, etc.,.

# REFERNCES AND GOOD READS
a. https://book.hacktricks.xyz/pentesting-web/hacking-with-cookies
b. https://docs.imperva.com/bundle/on-premises-knowledgebase-reference-guide/page/cookie_value_length_violation.htm
c. https://portswigger.net/web-security/deserialization/exploiting
d. https://blog.innerht.ml/tag/cookie-bomb/
e. https://resources.infosecinstitute.com/topic/cookie-based-sql-injection/
f. https://github.com/harsh-bothra/learn365/blob/main/days/day17.md
g. https://medium.com/@tehmezovismayil/cookie-based-php-local-file-inclusion-bug-bounty-553f8b38d4dc
h. https://secureteam.co.uk/articles/web-application-security-articles/understanding-session-fixation-attacks/
