# SAML => Security Assertion Markup Language

 - It is the language, that allows the server or the application to authorize the individuals.
 - They use XML
 - Service provider and Identity provider
 
Service provider SAML : 
 - For it to provide Service, it requires user identity authentication.
Identity provider SAML :
 - It provides the identity about who the user is, and sends the data to the service provider about the user, for 
 services

Eg. Identity providers : Microsoft Azure, Active Directory.


A Saml assertion is the XML document that an identity provider sends to a service provider, to authenticate the
respective user.

 - Authncn : This assertion proves the identity of the user.
 - Attr : This assertion provides add. info about d user.
 - Authorziation : Provides whether the user is auth. to avail that particular service
 

SSO => Single sign on
The user logs in only once and that too, only to the identity provider, and for each and every service to be availed from the service provider, the identity provider sends XML data / SAML language to the service provider to authenticate the user.


ATTACKS :

 - The signature is not checked by the service provider, so if we change the username to the victim's username, we can log in easily.
 
 - Signature is checked and verified but only if present, if removed YAY !
 
 - Use comments in username, to be logged in as the admin but on registrtaion, we are treated differently.
 admin email / name id : admin@test.com
 
 Registration attacker :
 ```
 username : "admin <!--Not admin>@test.com" 
 ```
 
 
 Here this is a new username, so on the SAML name id, this comment is ignored and it treats it as admin@test.com
 
 - Due to improper implementation, CSRF can be applied to change the username or password.
 
 - The assertion ID must be unique, and not be used more than once on multiple users.
 
