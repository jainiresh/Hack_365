# TOPIC
SECURE CODE REVIEW

# OVER VIEW
- This is the first line of security on defense, for developers.

## WHAT IS CODE SECURITY REVIEW ?
It is not only the duty of a bug researcher or a bug hunter to find out the vulns or threats that a code could produce,
But it is most important for a developer to review the code for vulnerability production.

This is a specialized task to review an application's source code.

## WHY CODE REVIEW ?
- First level of defense
- Identify security issues and vulns
- Almost 75% remediations happen at code reviews level
- Manula review along with automation

## DEVELOPER USE
- It familiriases the developers with the code.
- Helps developers in saving time in the future.
- Identifying the entry and exit points in the code.

# CODE SECURITY REVIEW APPROACH :
1) Automated Scan (using SAST - Static Application Security Testing)
2) Conduct a manual review on the reported issues by the SAST tools, and additional manual information.
3) Apply the fixes, and perform a revalidation.

# REMEDIATION :

## SQL INJECTION
- Using parameterized queries
- Data whitelisting

## xxE ATTACK
- Encode xml specific control characters (&, ', ", <, >, <space>)
- Disable DTD or Doctype entities to prevent XXE.

## COMMAND INJECTION
- Avoid inserting user inputs to commands executed by the OS
- Perform strict input validation and sanitization
- Different frameworks allows different set of inputs and commands to execute.

## XSS
- Regex validation of values obtained from requests / APIs / Databases
- Escaping malicious characters from user inputs
- Output encoding before webpage display.
- HTTP headers added for addn. security
	- X-XSS-Protection
	- Content Security Policy

## SESSION FIXATION - BROKEN AUTHENTICATION
- Session identifiers re-generated and re-issued after every login
- Uniqueness of Session ID and validating Session ID for every incoming request
- INvalidate session after user logout both on client and the server side
- User http security header attributes for cookies and random generators for 128/256 bit long session IDs.

## UNRESTRICTED FILE UPLOAD
- Validating file name and upload
- Magic byte of the file must be validated
- Enforcing an upper limit of the file size
- Frequency of file uploads must be validated
- Upload of files must be scanned for malwares, or viruses before stored in the Database.



# REFERENCES
https://www.youtube.com/watch?v=0hczZ9wrYAU
