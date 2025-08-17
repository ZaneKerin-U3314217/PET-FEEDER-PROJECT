# Background: Automated Pet Feeder System

_A local animal shelter is looking for a low-cost, programmable automated pet feeder that can:_

- _Dispense food for cats and dogs at scheduled times._
- _Monitor whether food has been consumed or the amount of food that has been consumed._
- _Alert staff if there’s an issue (e.g., no food dispensed, food not eaten)._

_They want a solution that could eventually be implemented using low-cost components (like a servo motor and sensors), but your task is to design and simulate the logic and behaviour of the system first._

## Step 1: Understand and Define the Problem (Analyse)

#### System Requirements

- Must be able to dispense food.
- The system must only dispense food at specified times.
- Must be able to detect the current time of day.
- Must be able to detect the current amount of food that has been dispensed/in the feeding tray
- Must be able to alert staff of issues with feeding (such as failure to dispense from lack of food or food being left uneaten)
- The feeder must be able to keep track of how much food it currently has stored, to evaluate whether it can successfully dispense food at a given interval.
- The feeder must be able to detect if food has not or is not being eaten.
- Must be constructed with low cost components.

#### Assumptions

- We will assume that only one kind of pet food is being used in each feeder.
- We will assume Feeding Times are at 9:00 AM and 6:30 PM.
- We will assume that the maximum food storage is 100g.
- We will assume that 35g is the amount of food which should be dispensed at each meal.
- The pet shelter’s employees will be correctly informed on the usage and implementation of the feeder systems and will know correct protocol for refilling them with food.
- The design of the feeding tray’s scales for measuring dispensed food will not be placed in a position that Cats or Dogs are likely to step on and accidentally trip its measurements.

**Goal:** Design a low-cost, automated pet-feeding system which can dispense food at scheduled times, monitor whether food has been consumed appropriately and alert staff if there are any issues using simple components.

**Key Questions:**

- How much leftover food should indicate that a pet did not eat their food?
- How often should we check whether food has been eaten or not?
- Which cases should alert staff of an error?
- When are the feeding times?
- How often should we check if it’s feeding time?
- How much food should be dispensed at a feeding session?
- How should we check whether we have enough food to dispense for a feeding session?
- When should the system stop running?

#### Inputs

| **Title of Input** | **Description** | **Source** |
| --- | --- | --- |
| Stored Food | The food which will be dispensed for that given day. Requires manual refills from shelter employees at the beginning of each work day. The amount of currently stored food is tracked by the system using a sensor that can detect how full the feeder’s storage is. | Sensor (Weight, grams)<br><br>Food provided by staff. |
| Current Tray Weight | The current weight of the feeding tray, measured by using a weight sensor. This input is used to measure how much food has been dispensed and to verify whether it is being eaten. | Sensor (Weight, grams)<br><br>This input is automatically provided by the weight sensor attached to the feeding tray. |
| Current Time | We will be using a real-time internal clock to determine the time. We will be using the time to figure out whether it is currently a feeding time.<br><br>Additionally, to automatically turn the system off at the end of the day, the Current Time will detect whether it is past the end of the work day and automatically power-off when it is. | Internal Clock (Timecode) |

#### Outputs

| **Title of Output** | **Description** | **Condition / Requirement for output** | **Notes** |
| --- | --- | --- | --- |
| Rotate Servo | Dispenses food from the feeder into the tray via use of the motor. | Requires food to be in the feeder and for the tray to be sufficiently empty. | Used to dispense food for pets. Will continually dispense until the tray weight is equal to the ‘Meal Amount’ constant, which will allow for the conservation of food by keeping leftovers available for consumption and not overfilling the feeding tray. |
| Alert | Alerts staff members at the shelter of an issue with the feeder system via the use of electronic alerts.<br><br>Provides the feeder’s ID for quick identification and the source of the error (currently tracked error cases: ‘insufficient food disposed’ and ‘food not consumed’. | If food has not been successfully dispensed due to insufficient food in or lack of room in the feeding tray (presumably due to lack of consumption).<br><br>Feeder must be hooked up to the electronic alerts system currently present at the shelter. | Must be able to differentiate types of alerts between different error cases. E.g: “Failure to dispense” and “Food not consumed” |

Constants:

- Feeding Times: 9:00 AM (09:00) and 6:30 PM (18:30)
  - Feeding Times constant will be used when querying whether the Current Time is one in which the system must dispense food for pets, if the current time is equal to a feeding time then food will be dispensed.
- Meal Amount will be 35g.
  - This constant will be used to check if the system has enough stored food to successfully feed pets at a meal time. If there is not enough food, the system will alert the staff.
- Leftovers Buffer will be 5g.
  - To minimise instances of false-alarms when detecting if a pet has eaten their meal, we will put a buffer weight of 5g in place. When we query if the pet isn’t eating, we will use this constant as a comparison point; if the weight on the tray is equal to or less than the buffer then the pet has successfully eaten the food.
- End of Work Day is at 10:00 PM (22:00)
  - We will use this constant to automatically power off the automated feeders when employees start locking up the shelter for the night.
