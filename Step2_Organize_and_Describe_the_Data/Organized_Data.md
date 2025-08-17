## Step 2: Organise and Describe the Data

#### System Parameters

| **Parameter** | **Type** | **Example Value** |
| --- | --- | --- |
| Current Time | Variable | 15:42 |
| Currently Stored Food | Variable | 08:00, 18:30 |

| **Variable Name** | **Description** | **Type** | **Units** | **Notes** |
| --- | --- | --- | --- | --- |
| Current_Time | Current Time | Input | Timecode (00:00) | Value registered in 24hr time. Tracked via internal real-time clock. |
| Stored_Food | Current Food Storage | Input | Grams | Via weight censor in food container. Used to determine how much food is |
| Tray_Weight | Current weight of the tray | Input | Grams | Via weight censor under food tray, used to determine the amount of food left in the feeding tray |
| Alert_Unconsumed | Alert for unconsumed food via Buzzer/Speaker | Output | ON/OFF | Buzzer and Speaker.<br><br>Triggers if detected tray weight is over the Leftovers Buffer value when querying if the pet has not eaten. |
| Alert_Insufficient_Food | Alert for insufficient food via Buzzer/Speaker | Output | ON/OFF | Buzzer and speaker.<br><br>Triggers if detected food storage is insufficient to complete dispersal. |
| Dispense_Food | Servo Motor Control for dispensing food | Output | ON/OFF | Controlled via relay or transistor, servo motor used to dispense food for pets. |
| FEEDING_TIMES | Feeding Times | Constant | Timecodes:<br><br>08:00, 18:30 | Times which food will be dispensed for pets. |
| MEAL_AMOUNT | Dispensed food amount. | Constant | Weight (grams):<br><br>35g | The amount of food that will be dispensed for a pet at a feeding time. |
| LEFTOVERS_BUFFER | Buffer for tray leftovers weight | Constant | Weight (grams):<br><br>5g | A minimum threshold which is used to prevent false-positives when detecting if a pet has eaten or not. |
| WORK_END_TIME | End of work day | Constant | Timecode:<br><br>22:00 | Time in which the system will automatically power down. |

Some additional notes:

- The system will operate on 1-minute intervals. If the current time is determined to not be a feeding time, the system will wait 1 minute before querying again.

To prevent false positives for pets not eating food, when checking if a pet has not eaten food, the system will check if the current time is within 20 minutes of a feeding time when determining if the tray is too heavy. This will give the pet time to eat before the system starts detecting if the food has been eaten or not.
