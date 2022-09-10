# TOPIC
Web Cache Deception Attack

# REQUIREMENTS
This attack is only possible when the cache control directives are misconfigured and can be leveraged to get hold 
of sensitive informations.

# OVERVIEW
This attack requires User interaction and Path confusion.
Flexible URL rewriting plays the significant role in this attack.

## PATH CONFUSION ATTACKS
Some webservers have the URL flexible rewriting kind of allows, such that the following two urls would be considered
as https://magma.com/admin
 - https://magma.com/admin
 - https://magma.com/admin/test-min.css

# UNDERSTANDING
Consider a sensitive endpoint, for eg : https://bank.com/accounts
Now add a static file like test.css or test.jpg etc., and if on adding this again the same page ``` https://bank.com/accounts ```
is displayed then, the page might be cached.

Now on another computer or on a totally different session, navigate to the url "https://bank.com/accounts/test.jpg",
this may give out the user (victim's) profile page.

# REPORTS
https://hackerone.com/reports/397508
https://hackerone.com/reports/1271944  => RECENT report(atleast at the time of making this file), 800$
https://hackerone.com/reports/593712


