# TOPIC
DEPENDENCY CONFUSION ATTACK

# OVERVIEW
This is one of the most critical vulnerability, but difficult and rare to spot.
It arises when a web application uses a package which is not publicly available in the public registry for the packages.
It could also arise if the public package is not yet claimed by the owner.

# EXPLANATION
Web application, and mainly their open sourced projects tend to import packages from public registries (pip, npmjs, etc.,.).
Problems may arise if these packages are not claimed by their owners, or it is not publicly available in the public registry.

# EXPLOIT
An attacker could upload a new package in the public directory, with the same name as that of used by the company's 
vuln package.
Soon enough, the malicious package becomes home for the website's package import, and the attacker could get internal
server's ping.

# TOOLS
https://github.com/visma-prodsec/confused

This tool when fed with package.json or requirement.txt, it scans for all those packages on their availability on 
their respective public registries

# REFERENCE
https://redhuntlabs.com/blog/dependency-confusion-attack-what-why-and-how.html
https://blog.doyensec.com/2022/07/21/dependency-confusion.html
