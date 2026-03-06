```START
SET balance = 1000, daily_limit = 5000, attempts = 0
INSERT card
LOOP WHILE attempts < 3:
    PROMPT for PIN
    IF PIN is correct:
        BREAK LOOP
    ELSE:
        INCREMENT attempts
        DISPLAY "Incorrect PIN"
IF attempts == 3:
    DISPLAY "Card blocked"
    EXIT
DISPLAY balance
PROMPT for withdrawal_amount
IF withdrawal_amount > balance:
    DISPLAY "Insufficient balance"
ELSE IF withdrawal_amount % 20 != 0:
    DISPLAY "Amount must be a multiple of 20TL"
ELSE IF withdrawal_amount > daily_limit:
    DISPLAY "Daily limit exceeded"
ELSE:
    SUBTRACT withdrawal_amount FROM balance
    DISPENSE cash
    PRINT receipt
PROMPT "Perform another transaction?"
IF yes:
    GOTO balance display
ELSE:
    EXIT
END
```
