# TOPIC
GRAPHQL Attacks

# OVERVIEW
In this section there will be a discussion of GRAPHQL attacks, and their common vulnerabilities.

# VULNERABILITIES
## INFORMATION DISCLOSURE VIA ERROR MESSAGES
- Unexpected inputs could give you error messages
- Malformed inputs could give you the same
- Unshaped queries and try out all kinds of malformations to see if the app responds an error message with the query.

## DOS
- Due to a improper configuration on the maximum limit of graph query depth, there is a possible Denail Of Service attack.
- Nest a  query to unlimited depth, and send it to the grahpql end point to see how the server reacts.

## IDORs
- Finding these are similar to the normal API hunting for IDORs.

## BURP EXTENSIONS 
- InQL
- GraphQL Raider

# LABS
https://github.com/dolevf/Damn-Vulnerable-GraphQL-Application

# REPORTS AND REFERENCES
https://infosecwriteups.com/graphql-idor-leads-to-information-disclosure-175eb560170d
https://infosecwriteups.com/graphql-idor-leads-to-information-disclosure-175eb560170d
