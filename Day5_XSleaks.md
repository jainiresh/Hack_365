# TOPIC
## XS - LEAKS

Cross site leaks

They use small middleware logics or small bits of info to get chained up to a sensitive information.

# Methodology

Generally its an YES or NO information derival.
Lets assume there is an api, giving info about an user.
If the user's info comes out with a 200 response status, then the user info exists, else it doesnt with an 404 error response.

SImilarly, the angle of the questions asked can be changed to reply with an YES or NO question, so that the information about the user will be gathered soon.

# ATTACKS 

```
1) Using the query paramter, modifying it depending on the attacker's motive, and he could get sensitive info.
2) Based on error events or successful events, we can get senistive info about its presence or absence.
3) Window.length => provides info about the page.
4) If the user is navigated to anywhere else, we can collect info from that.
5) User ID or any kind of ID exposed, could be noted down and used in the future.
6) If the web page has cache, cache probing can be done
7) Using Cross Origin Read Blocking and Resource Policy to the adv.
8) Timing based attacks.

Try searching for ?query=b it could be a miss, then try ?query=ba , try doing so and we could get a hit, when we get ?query=bal.

```

# UNDERSTANDING:

Consider twitter's private tweets, only specific user can access the tweets.
Now as an attacker, we can send a link to the specific user, and make him search for the query provided by the attacker's choice of words.

Since the request is sent from the victim's browser, depending on the state change for presence and absence of the query, the attacker can see the delay in timing or the state change, and guess the presence of the word or not.


# REPORTS
```
https://hackerone.com/reports/491473
```

# REFERENCES
```
https://www.imperva.com/blog/facebook-privacy-bug/
```


cd C
