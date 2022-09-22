# TOPIC
COMMON BUSINESS LOGIC ISSUES - PART 1

# TESTING FIELDS

## REVIEW FUNCTIONALITIES
- There are high chances that you find a bug, in a review functionality.
- Try, whether you can post like some other users.
- Try, to implement an CSRF attack.
- Try, to rate using an abnormal number in case if the review system is numeric.
- Try, to review as an verified user.
- Try, to post multiple posts, in case you are not allowed.
- Try, to find file upload vulnerabiilites.
- Try, to find RACE CONDITIONS

## COUPON CODE FUNCTIONALITY
- Check for reusable codes
- Try, to check for RACE conditions for unique coupon codes
- Try, to check for HTTP parameter pollution to send multiple codes, when the app tends to accept only one code.
- Try, to check for MASS assignment.
- Try to find missing input sanitization of the input fields.
- Try adding discount or the coupon code on products, that are not intended for.

## DELIVERY CHARGE ABUSE
- Try, to fix a negative number as the delivery charge so that the final price amount could reduce.
- Try, to tamper with the request to get a free delivery.

## CURRENCY ARBITRAGE
Try, to pay in a type of currency and refund in another type (USD -> EU), it is possible to gain more amount

