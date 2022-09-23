# TOPIC
Common Buisness Logic Issues 2

# OVERVIEW
These are some of the often bugful places, which are analysed

# EXPLOITS
## PREMIUM FEATURE EXPLOITS 
- Try to abuse the premium feature with a little play around with the requests, by changing the values.
- Purchase a premium feature, and then cancel it and get a refund, and try checking if the feature is still in use.
- Try Burp Suite's Match and Replace tool, to replace the true false value of a premium bug, to check whether an
user is a premium user or not.
- Always check cookies or local storage to see if any variables are present which are concerned to the premium user accounts.

## REFUND EXPLOITS
- Check for different currency that allows for a more pay than expected, issue.
- Try race conditions on refunds, to get multiple refunds for a cancellation of a premium feature.
- Try getting refund, and check if the feature is still accessible.

## CART/WISHLIST EXPLOITS
- Add a product in negative quantity with other products in positive quantity to balance the amount.
- Add a product more than the available quantity.
- Check moving of cart items, from some other's cart to urs, or vice versa, or deleting the same

## THREAD COMMENT EXPLOIT
- Check for unlimited comments
- Suppose a user can comment only once, try race conditions for two comments.
- Try posting comments impersonating some other user

## VERIFED USER EXPLOIT
- Check for parameters that can be changed to make us, a verified user.

