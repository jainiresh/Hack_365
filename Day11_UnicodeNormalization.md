# TOPIC 
Unicode Normalization

# Overview
Normalization => The process of converting characters to a standard form.
Punycoding => Process of converting Unicode to ASCII.

# TYPES OF EQUIVALENCE BETWEEN CHARACTERS
## Compatibility equivalence
Here two characters are said to be equivalent, even though they may appear different compared to each other.
## Canonical Equivalence
Here two characters are said to be equivalent by canonical terms, they look the same, but their unicodes may be different
in a case.

# SOLUTION
Unicode normalization is the solution for both the types of, equivalence.

 - Decomposition :
Breaking up the special character to  => Normal Character + The special symbol attached with it

 - Composition :
Combining the two unicodes that make up the single character to a single unicode.

Combining these two we get four conversions as a result :

# FORMS
## FORM D
Canonical Decomposition
(C with Cedilla) -> C
NFD

## FORM C 
Canonical Decomposition followed by Canonical Composition
(C with Cedilla) -> C -> (C with Cedilla)
NFC

## FORM KD
Compatibility decompostion
(cursive H symbol) -> H
NFKD

## FORM KC
Compatibility decomposition followed by canonical composition
(Cursive H symbol) -> H -> (H with Cedilla)

# VULNERABILITY
SQL injection can be a great use case for these kindof attacks, lets consider an input is sanitized and are normalized
before entering into a backend database.
If we know the type of normalization used in the backend system to compare usernames or passwords from the input table,
then we can find out the unicode character for ('), and add it to the input, so the backend compiler, converts
it to an apostraphe('), which may cause SQLi.

## url encoding Unicodes
use javascript's enocodeURI() function

# REAL TIME SCENARIO
If an input converts all the '>' and '<' symbols to &lt; and &gt; and are then normalized, we can find a unicode characcter
and inject it, such that

- The unicode is not connverted to any special symbols as they are not containing any special characters
- after the first step, normalization is done, and the unicode can be used to covert as a "<" or"">" in plain text

# DETECTION
An unniversal single payload can be used to detect an application's input performs normalization or NOt.
## STEPS
 - Identify a reflection on the input
 - Submit a string containing the Kelvin symbol (K), as Special%e2%%84%aa
 - If the string SpecialK is returned, then some form of Normaliztion unicode is done
 - Using ref table we can bypass the inputs.


# REPORT REFERENCES
https://engineering.atspotify.com/2013/06/creative-usernames/

# STUDY MATERIAL
https://appcheck-ng.com/unicode-normalization-vulnerabilities-the-special-k-polyglot
