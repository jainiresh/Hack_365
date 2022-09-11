# TOPIC
Session Puzzling Attack

# OVERVIEW
An attack by the attacker which can be used, to access authorized pages of the victim by the attacker, using
session token generated on unauthorized pages.

# UNDERSTANDING
The attacker navigates to the Forgot password page (/forgot_pass), and requests for a password reset using the
victim's email.

The application gives a session identifier since the victim's email is provided.

This session token may be used to access authorized pages like /myprofile page of the victim.

# TESTING
Always check for session identifiers generated on lower privilieged or unauthorized pages, and test them to access
higher privileged or authorized pages.

# REMEDY
Session tokens generated must be used only to a single consistent page.

# RESOURCES
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/06-Session_Management_Testing/08-Testing_for_Session_Puzzling
https://dzone.com/articles/using-session-puzzling-to-bypass-two-factor-authen
https://medium.com/bugbountywriteup/hunting-session-overloading-d2ec860c49c0
https://code.google.com/archive/p/puzzlemall/downloads
https://medium.com/@maheshlsingh8412/session-puzzling-attack-bypassing-authentication-29f4ff2fd4f5
https://deepsec.net/docs/Slides/2013/DeepSec_2013_Shay_Chen_-_The_Boomerang_Effect_-_Using_Session_Puzzling_To_Attack_Apps_From_The_Backend.pdf


