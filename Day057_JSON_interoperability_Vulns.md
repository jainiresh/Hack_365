# TOPIC
JSON INTEROPERABILITY VULNERABILITIES

# OVERVIEW
On February 25, 2021 
Bishopfox released their research on JSON interoperability vulnerabilities.
This topic is about their research, and a big shoutout to them

# MAJOR SECURITY ISSUES

## Inconsistent Duplicate Key precedence
Sample :
obj = {"test": 1, "test": 2}
obj["test"] = 1 or 2 ???

This is about the JSON parsers handling duplicate values for the same key.
Some JSON parsers, handle them based on the first value assigned to the key, and some handle the second one.
These type of variations in parsers could possibly cause IDORs or LOGIC issues, when working on an application.

## Key collision: Character truncation and Comments
Okay now, LETS assume our parsers are immune to duplicate keys.
No matter how many duplicate key value pairs we inject on our keys, and the position of our duplicates, they all 
get reflected the same.

###Key Collision : character truncation
It is a technique, which can be leveraged by an attacker to store duplicate values
or allow them to be processed instead of the real one.

Example :
a normal body : 

{
"superAdmin":false
}

Here, a duplicate keyvalue pair first or last will be ignored, since the same key names are not accepted.
Therefore, the attacker could send a payload like,

{
"superAdmin":false,
"superAdmin\ud888":true
}

Some JSON parsers truncate the Unicode in the keys and store this as "superAdmin":true, thus bypassing the control placed
on the super admin parameters.

Try to include truncating characters on the key value pairs you send to the backend APIs.

###Key Collision : comment support
The Official JSON parsers do not have the ability to encode comments into their values, and process them asnormal comments.
Example :

{
"test":100,
"extra":/*,
"test":50,
"extra2":*/
}

The above JSON when parsed with GoLang's GoJay Library would result in execution of the comments such as

"test":100,
 extra:""

Whereas,
Java's JSON-iterator library would result in

"extra":"/*"
"extra2":"*/"
"test"50

## JSON SERIALIZATION QUIRKS
There are open problems till date on JSON serialization and deserialization.
Example :

"obj" = {
	"test"=1,
	"test"=2
}

OUTPUT :
for obj["test"] = 1
for obj.toString() = {"test":2}

## FLOAT AND INTEGER REPRESENTATIONS
Large numbers are often represented as MAX_INT or 0, which can cause business issues.

Adding the price of a product to => 
{
"productPrice":99999999999999
}

this may result in productPrice = 0.

## PERMISSIVE PARSING AND ONE-OFF BUGS

### TRAILING GARBAGE
These are often used to bypass CORS and perform CSRF attacks.
The hacker change the Content-Type to application/x-form-urlencoded , which are allowed in CORS.

A trailing garbage like a "=" sign, would help transmitting JSON to CORS websites.
like:

Content-Type: application/x-www-form-urlencoded

{"test":1}=

Services and Parsers that disregard Content-Type headers and process all the JSON key values are prone to this attacks.

# LABS
https://github.com/BishopFox/json-interop-vuln-labs

# REFERNCES
https://labs.bishopfox.com/tech-blog/an-exploration-of-json-interoperability-vulnerabilities
