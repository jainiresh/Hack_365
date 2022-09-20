# TOPIC
SALESFORCE DEPLOYMENT'S SECURITY MISCONFIGURATIONS

# OVERVIEW
This is the 2nd part, which contains the misconfigurations in the security measures to check out, if a Salesforce
deployment is found out.

# CHECKS
- Ensure to enable HTTP only attribute to make sure that the cookies are protected from attacks such as XSS.
- Apply the release update
- Make sure to enable Field tracking for Custom and standard object, to not miss out the logs of unauthorized changes made in the web application.
- Implement a salesforce role hierarchy, to distribute roles among the users in the salesforce.
- Ensure that the transaction security is in use.
- Ensure that multi-factor authentication is enabled for all the user accounts.
