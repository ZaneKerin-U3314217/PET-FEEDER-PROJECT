## Step 4: Implement the Solution (Word Coding)

System Logic:

1. **START SYSTEM**  

2. **Check Tray_Weight.**
    1. If Tray_Weight is greater than LEFTOVERS_BUFFER, check Current_Time.
        - If Current_Time is less than 20 minutes after a FEEDING_TIMES, then proceed to step 3).
        - Otherwise, send Alert_Food_Unconsumed then **STOP SYSTEM**.
    2. Otherwise, proceed to step 3).  

3. **Check if Current_Time and compare it to all FEEDING_TIMES.**
   1. If Current_Time does not match any entries in FEEDING_TIMES, wait for 1 minute and return to step 2).
   2. Otherwise, proceed to step 4).  

4. **Check Stored_Food and compare it to MEAL_AMOUNT and Tray_Weight.**
    1. If Stored_Food is less than MEAL_AMOUNT - Tray_Weight, then begin Alert_Insufficient_Food and **STOP SYSTEM.**
    2. Otherwise, proceed to step 4).  

5. **Begin Dispense_Food until Tray_Weight equals MEAL_AMOUNT, then stop Dispense_Food.**  

6. **Check if Current_Time is after WORK_END_TIME.**
    1. If it is, **STOP SYSTEM.**
    2. Otherwise, wait 1 minute and return to step 2).
