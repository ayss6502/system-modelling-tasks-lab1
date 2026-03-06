START
IF system_active == TRUE:
    LOOP (Continuous Monitoring):
        READ Motion sensor data
        READ Door/Window sensor data
        
        IF motion detected OR door/window opened (Condition):
            ACTIVATE Camera (Condition)
            
            IF homeowner_at_home == TRUE (False Alarm Check):
                DISPLAY "Activity detected. System waiting for manual override."
            ELSE:
                DETERMINE alarm level:
                    - Level 1 (Low): Notification only
                    - Level 2 (Medium): Siren + Notification
                    - Level 3 (High): Siren + Emergency Services
                SEND notifications (SMS + App + Email)
                
        WAIT for specified interval
        RE-CHECK sensors
        
        IF user_resets_alarm OR system_continues:
            CONTINUE LOOP
ELSE:
    DISPLAY "System is offline."
END
