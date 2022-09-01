# TOPIC
## XSSI => Cross Site Script inclusion

# Overview
XSSI is not XSS, they are different.
Here the JS paylod, that is embedded in the attacker's controlled page, are included in the victim's page to trigger an action.

# Goals
To generally steal data, bypassing the SOP.
To steal authentication tokens
Mainly sensitive informations that are dynamically stored in the JS files.

# Methodology
- First step, is to find out whether the sensitive informations are dynamically passed into the JS files.
- Second step, try out with both auth and un-auth users, to find the difference.
- Use DynamicJS Burp Plugin, to find out the difference between them.
- The attacker page contains a script tag, and the source of the script tag is the vulnerable page's javascript location.
- SInce this is requested by the victim, the auth details included in the JS files are accessed through the attacker.
- The attacker, in his controlled script tag, can include functions to override the vuln page's js functions and also write his own functions to dump the data or alert them, this is possible because the script tag considers all the functions written and loaded from the external file as single JS file.

- The javascript functions themselves can be overriden by the attacker, using Array.prototype before methods like slice.



# Differences Between XSSI
## and CSRF
Although both are kindof similar, and originate from a different domain (attacker controlled), CSRF is intended as a state changing action, whereas XSSI are intended to leak sensitive data files.

## and XSS
Here, XSS is used to inject malicious code to the victim's page => Here victim is the user
IN, XSSI the victim's code is injected into the malicious page => Here victim is the page ( as it allows XSSI )

# References:
```
https://www.scip.ch/en/?labs.20160414
```

# LABS
Link :
```
https://google-gruyere.appspot.com/part3
```

# EXPLOIT CODE :
```

<html>

<body>

	<h1>Leaks</h1>
	<script>
		function _feed(data){
			alert(data['cheddar']);
		}
	</script>
	<script src="https://google-gruyere.appspot.com/433818199877552549341129461204308268453/feed.gtl"></script>
</body>
</html>
```

