# TOPIC
SMTP -> Simple Mail Transfer Protocol

# OVERVIEW
- If we ever find a SMTP open port, then the next sensible thing to be done is to check for an SMTP open relay attack.
- It is a mail server through which we can send outbound emails
- SMTP service is often found on PORT 25, 465, and 587.

# TESTING
## USING METASPLOIT
- run msfconsole
- use auxillary/scanner/smtp/smtp_relay
- show options
- set required options
- run
The output, will show you if the port is vulnerable to an OPEN RELAY attack or not.

## MANUAL EXPLOIT
- Assume that the port is vulnerable
- Do the following :
	- telnet <server_ip> 25
	- HELO target.com
	- HELO magma.gg
	- MAIL FROM: admin@target.com
	- RCPT TO: magma@magma.gg
	- DATA
	This is my email from Open Relay

## Using Nmap NSE
 - nmap -sV --script smtp-open-relay -v <target>

## SHODAN DORKS TO FIND SMTP OPEN PORTS
 - port:25
 - "smtp"

#  References & Good Reads
a. https://www.blackhillsinfosec.com/how-to-test-for-open-mail-relays/
b. https://www.rapid7.com/db/modules/auxiliary/scanner/smtp/smtp_relay/

