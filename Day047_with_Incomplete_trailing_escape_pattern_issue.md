# TOPIC
INCOMPLETE TRAILING ESCAPE SEQUENCE

# OVERVIEW
This is a specific case, rather than a generic one !
Most of the bugs, occur due to failure in validating the input, that we enter to the server or application.

# EXPLANATION
- This bug occurs, when a user enters the symbol "%" in the input field, and without any issue it gets stored in
the Database (DB).

- There is an error encountered, when the data stored is tried to fetch using the GET api. It reads the "%" symbol
and it fails to parse it completely throwing an "Incomplete trailing escape (%) pattern" error.

- This could lead to a Denial Of Service.

- If this api was a shared one, then all the users using this would get affected !

# EXPLOITING
- Let's assume there is a field for "First name".
- We input a string like "&*$%^ and it gets accepted wihtout any errors, with a message user details updated successfully.
- Now there comes the GET api to fetch the user's first name, which could not parse the string throwing an 500 internal 
server error to the user !

# REFERENCES

- https://www.programmersought.com/article/1312520870/
