START
PROMPT for Student ID and Password
IF Login Successful:
    DISPLAY available course list
    LOOP (Registration Process):
        SELECT a course to Add or Drop
        IF Action == "Add":
            CHECK course capacity (Quota)
            CHECK prerequisite course completion
            CHECK schedule conflicts with already added courses
            CHECK total credits (Current Credits + New Course <= 35)
            
            IF all conditions are met:
                ADD course to registration list
                UPDATE current total credits
            ELSE:
                DISPLAY specific error message (e.g., "Quota Full" or "Conflict")
        ELSE IF Action == "Drop":
            REMOVE course from registration list
            UPDATE current total credits
        
        PROMPT "Are you finished with changes?"
        IF yes:
            BREAK LOOP
    
    IF Student GPA < 2.5:
        SEND registration to Advisor for approval
        DISPLAY "Pending Advisor Approval"
    ELSE:
        DISPLAY registration summary
        CONFIRM and Finalize registration
ELSE:
    DISPLAY "Login Failed"
END
