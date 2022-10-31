# TOPIC
STRING FORMAT VULNERABILITIES

# EXPLANATION
Here, the formatting of string in code is weak, therefore this could lead to stack memory or buffer memory be exposed
to the user.

This vulnerability is similar to the SQL injection vuln.
Adding %p into the input, makes the "%p" a string format specifier, and it dumps the memory to it.

More to this can be leared in the link provided in the below REFERENCES section.

# REFERENCES
https://www.youtube.com/watch?v=NnNYgFYcfSE
