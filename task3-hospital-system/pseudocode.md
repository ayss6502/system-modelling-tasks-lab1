START
PROMPT patient for Identity verification (ID number)
IF ID is valid:
    DISPLAY Action Selection Menu:
        1. Make Appointment
        2. View Test Results
    IF Choice == 1 (Appointment Module):
        SELECT Clinic from list
        SELECT Doctor from list
        LOOP until a slot is chosen:
            DISPLAY available time slots
        CONFIRM appointment
        SEND SMS notification
    ELSE IF Choice == 2 (Test Results Module):
        CHECK if tests exist for the patient
        IF tests exist:
            CHECK if results are ready
            IF ready:
                DISPLAY results
                OFFER option to download as PDF
            ELSE:
                DISPLAY "Your results are not ready yet."
        ELSE:
            DISPLAY "No records found for recent tests."
    LOOP:
        PROMPT "Would you like to perform another action?"
        IF response is NO:
            BREAK LOOP and EXIT
ELSE:
    DISPLAY "Invalid ID"
END
