START
CHECK User login status (Condition)
LOOP (Browsing through product categories):
    SELECT product
    CHECK stock availability (Condition)
    IF stock is available:
        ADD product to cart
    ELSE:
        DISPLAY "Out of Stock"
    PROMPT "Continue shopping?" (IF no, BREAK loop)
LOOP (Viewing and editing the cart):
    VIEW cart items
    OPTION to update quantities or remove items
IF cart_total < $10:
    DISPLAY "Minimum order amount is $10"
    GOTO Viewing and editing the cart
APPLY discount code (IF applicable)
IF cart_total > $40:
    SET shipping_fee = 0 (Condition: free above $40)
ELSE:
    CALCULATE shipping_fee
SELECT payment method (Condition)
CONFIRM order
END
