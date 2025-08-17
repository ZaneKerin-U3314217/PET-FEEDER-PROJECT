1. **START SYSTEM**

2. **Check `Tray_Weight`.**  
   1. If `Tray_Weight` > `LEFTOVERS_BUFFER`, check `Current_Time`:  
      - If `Current_Time` is less than 20 minutes after any `FEEDING_TIME`, proceed to step 3.  
      - Otherwise, call `Alert_Food_Unconsumed` and **STOP SYSTEM**.  
   2. Otherwise, proceed to step 3.

3. **Check `Current_Time` against all `FEEDING_TIMES`:**  
   - If `Current_Time` does not match any entry in `FEEDING_TIMES`, proceed to step 6.  
   - Otherwise, proceed to step 4.

4. **Check `Stored_Food` relative to `MEAL_AMOUNT` and `Tray_Weight`:**  
   1. If `Stored_Food` < (`MEAL_AMOUNT` − `Tray_Weight`), call `Alert_Insufficient_Food` and **STOP SYSTEM**.  
   2. Otherwise, proceed to step 5.

5. **Dispense Food**  
   - Begin `Dispense_Food` until `Tray_Weight` equals `MEAL_AMOUNT`, then stop `Dispense_Food`.  
   - Proceed to step 6.

6. **End-of-Work Check**  
   - If `Current_Time` is after `WORK_END_TIME`, **STOP SYSTEM**.  
   - Otherwise, wait 1 minute and return to step 2.
