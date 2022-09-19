# TOPIC
SALESFORCE SECRUITY MISCONFIGURATIONS 1

# OVERVIEW
If we encounter a Salesforce deployment, we must check for the security practices.

# CHECKS
## PASSWORD CHECK
- Ensure the maximum invalid attempts are set to a smaller value
- Ensure a longer lockout period is set
- Check if a complex password policy is set
- Ensure a discrete and reliable secret question answer is set .

## REAL TIME EVENT MONITORING
- Sales force deployments track every actions of the users, from API calls made to the users viewed.
- Ensure all the necessary trackable events are really tracked.

## SETTING LOGIN IP RANGES
Ensure a LOGIN IP ranges are set, from which the users can login which helps in increasing the security from an outer
perspective.

## ENABLING CLICKJACKING PROTECTION
Ensure that clickjacking protections are enabled, and it is not possible to iframe the pages which contains
sensitive informations, and doesn't lead to a sensitive data exposure with clickjacking as it's base.


