REGULAR EXPRESSION DENIAL OF SERVICE 

Regex => The pattern mostly used in javascript to check for proper input sytnax.
When an attacker learns the logic of the REGEX and crafts a specific input that makes the valid checking process of the string long and slow,
which gradually leads to Denial Of Service attack.

Search for REGEX patterns in Source codes of inputs and validators.
Not all REGEX are vulnerable to such kind of attacks, but specific EVIL regex are vulnerable.

Like :
 - If a repetition is grouped
 - Inside the repeated group : 
    - Alterations with repetitoins
    - Repetitions
    
    
    
Root cause : 
Backtracking.. As to prove a particular input not valid, the regex generates all possible ways to prove its possible and
only if none is possible, they are deemed as not valid.

SO for very large inputs, there is a chance of Denial Of Service.

HackerOne reports read :
 - https://hackerone.com/reports/1023899
