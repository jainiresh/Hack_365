# TOPIC
PASSWORD RESET TOKEN ISSUES

# OVERVIEW
Most of the websites with a login panel page for the users, also have the "forgot-password" link, which sends you a password reset link.
This action has a lot of angles to be vulnerable, and we can check all the angles to make sure the action is done securely.

# TYPES
Certain websites sends us an OTP
Certain websites sends us a Temproary Password
Some websites sends us the password itself
Some sends the link to reset our password.

# TESTING
1) Always check for weak cryptography in password reset token.

```
Some sites manipulate the user's email or personal information that are unique, to create a password reset token, keep an eye on known cryptographic hashes to hash them.
```

2) Check for the reuse of password reset tokens

3) IDOR

One of the most interesting and challenging and high rewarding vulnerability.
Manually browse through the requests made and the redirections made, and by hit and trial methods test all the tokens, by
changing their values, previously used values or completely removing them.

4) Check for non validation of password reset tokens

5) Excessive information like old passwords in JWT based password reset tokens.

# RESOURCES
https://medium.com/bugbountywriteup/weak-cryptography-in-password-reset-to-full-account-takeover-fc61c75b36b9
https://www.youtube.com/watch?v=mLi3qxhLIA0&list=PLYn5_MxRvV-fxPL90I-uebXQzQBXfIaY0&index=10
https://speakerdeck.com/harshbothra/broken-cryptography-and-account-takeovers
