# TOPIC
DOMAIN HIJACKING BLOG


# WHAT IS DOMAIN HIJACKING ?

Domaing hijacking is a kind of an attack, whereby an attacker impersonates an domain registar by impersonating him, after social engineerin his critical details
This can lead to hijacking of the authority to direct the traffic of the main domain to the desired path of the attacker.


# DOMAIN TRASFER PROCESS

- Lets call the existing domain owner as OWNER, and the person to whom the domain is getting transferred to as SECONDER.

+ OWNER disables WHOIS/domain privacy on his domain, so that the SECONDER can verify his identity.
+ OWNER disables all kind of transfer prevent protections, before the transfer.
+ OWNER gets an Authentication code
	- This step depends on the type of domain that is dealt with.
	- For the type of nominet-controlled domains such as (.uk, .co.uk, .me.uk ) the OWNER who wishes to transfer the domain from one OWNER
to another SECONDER, needs to set a IPS (Internet Provider Security) flag on the domain to be transferred. This flag is called the registrar flag.
	- At the time of transfer the OWNER must update the registrar flag to reflect the SECONDER's tag.

+ The SECONDER requests transfer to the new registrar
+ The previous owner OWNER, now receives an mail regarding the transfer, and on approval the domain would be sucessfully transferred.

# EXPLOITING GANDI BASED DOMAINS TRANSFER TO TAKEOVER

https://www.cyberis.com/article/domain-hijacking-logic-error-gandi-and-route-53-vulnerability
