# TOPIC
Detecting complex code patterns with semantic grep

# TOOL USED
semgrep
```
https://github.com/returntocorp/semgrep
```
#USE AND EXPLANATION
The code that we type in, on the computer is not a string, but a TREE.
They are called as the Abstract Syntax Tree.

Basically, it is a tool used to search for specific patterns or words in a code.
You can search for a function call with any arguments like this : <func_name>(...)

Similarly, this supports a lot of languages except a few like RoR, etc.,.

 - finding exec()
 - finding unsafe.Pointer() or unsafe.$FUNC(...)
 - searching for file injection routes in python like
```
@app.route("/get/file/<filename>")
def get_file(filename):
	print("getting file", filename)
	return send_file(filename, as_attachment=True)
```
a source code's part, all these could be searched using the syntax like

```
@app.route("...")
def $FUNC($FN):
	...
        return flask.send_file($FN, ...)

```
 - finding setting cookies

# USING YAML MULTI-PATTERN FILTER

We have certain rules where there is an id parameter,
and then the patterns.

eg :
```
rules:
- id: flask-secure-cookie
	patterns:
	 - pattern-not: flask.response.set_cookie(..., httponly=True, secure=True, ...)
	 - pattern: flask.response.set_cookie(...)
	message: hey cookies arehard, talk with security issues
```

there are more examples and uses to semGrep, that you can learn by listening to the talk.
Link below on REFERENCES.

# REFERENCES :
https://www.youtube.com/watch?v=IFRp2Y3cqOw&list=PLruly0ngXhPGvyl-gOp4d_TvIiedloX1l
