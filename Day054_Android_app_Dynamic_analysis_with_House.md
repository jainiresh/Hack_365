# TOPIC
ANDROID APP DYNAMIC ANALYSIS USING HOUSE

# OVERVIEW

## CHALLENGES
- Root detection implemented
- SSLPinning implemented
- Both together
- Apps crashing after bypass techniques are used
- Encrypted parameters in requests

### ROOT DETECTION
 - Android app checks if a device is rooted or not
 - Most root detection techhniques rely on checking for file on the OS that indicates whether the device has been 
rooted or not
 - Other root detection techs involve checking for the below packages are present or not
	- Supersu.apk
	- Root Cloak
	- Xpose Framework

### SSLPinning
- The Devs implement certificate pinning in order to prevent MITM attacks
- Application in short checks and compares the fingerprint with it and the one provided by the server

## SSL/TLS communication in ANDROID - NOT TOs
- Improper implementation majorly includes developers who replace http:// with -> https://
- This will encrypt the messages sent over the wire, but the application will trust every certificate issued by the server leading
to MITM attack.

# BYPASS TECHNIQUES
They use frida scripts to disable root detectino code

# FRIDA
- Researchers write FRIDA scripts
- Frida provides "--codeshare" option, automatically pulls scripts from frida repo
 - They are a very powerful tool able to inject JS into the service during runtime
 - Learning it is quite difficult, as it has a steep learning curve involving time and TALENT.

# HOUSE
- Mobile analysis platform built on FRIDA
- SImplifies testing process with using FRIDA
- Features :
	- Class enumeration
	- Method enumeration
	- Multiple Function traccing
	- Scripts customization
	- Function interception


# REFERENCES
https://www.youtube.com/watch?v=n7vW-TVtXb0	
