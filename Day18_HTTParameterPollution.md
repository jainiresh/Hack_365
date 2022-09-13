# TOPIC
HTTP parameter pollution

# OVERVIEW
They are a sort of an attack, where The passed HTTP parameters are polluted, by including duplicate parameters with
different values, or similar kind of attacks.
These kind of actions can produce unexpected results, by the application or server

# ACHIEVEMENTS
WAF can be bypassed
Authentication Bypass can be done
Filter BYpass
Business logic abuse 

# TESTING
Try to copy the existing parameters, with a different value like from=123&from=789
Change  the existing values like : https://ramco.co/abc?to=1 => https://ramco.co/xyz?to=1

# REFERENCES
https://www.acunetix.com/blog/whitepaper-http-parameter-pollution/
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/07-Input_Validation_Testing/04-Testing_for_HTTP_Parameter_Pollution
https://logicbomb-1.medium.com/bugbounty-compromising-user-account-how-i-was-able-to-compromise-user-account-via-http-4288068b901f
https://shahjerry33.medium.com/http-parameter-pollution-its-contaminated-85edc0805654
https://www.ikkisoft.com/stuff/HPParticle.pdf
https://owasp.org/www-pdf-archive/AppsecEU09_CarettoniDiPaola_v0.8.pdf


# REPORTS
https://hackerone.com/reports/105953
https://hackerone.com/reports/298265

