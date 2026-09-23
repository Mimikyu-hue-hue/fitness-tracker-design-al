# fitness-tracker-design-al
Fitness tracker pseudocode and flow chart and IPO chart and something else to add more ands to the sentence and in python code and is cool

**Course** ITP 100 Software design and Logic.
**Author** Abdullah Lone
**Deliverable** Algorithm Design (IPO, Flowchart, Pseudocode)

## 1. Problem Description & Scope
** Command line interface to track to track daily cardiovascular and strength duration, validate and make sure its realistic. review their progress towards the 120 minute goal. **  
**Scope**
* Features a main loop with 2 hierarchical submenus (Cardio and strength)    
* Validates menu bounds (Rejects values outside menu options) and duration input (no negative numbers)  
*  Aggerates total minutes in memory during execution and outputs a progress summary  
*  terminates cleanly when the user selects the exit option.  

## 2. IPO Chart (Input - Process - Output)
| Input | Process | Output |
| :--- | | :--- | | :--- | 
| `main_choice` (Integer 1-4) <br>
| `sub_choice` (Integer 1-3) <br>
`duration` (Real / Integer: $\ge 0$) |
1. Initionalize `total_cardio = 0`, ` total_strength = 0`. <br>2. Loop main menu display until user enter `4`. <br> 3. Validate that `main_choice` is between 1-4.<br> 4. if `1` (Cardio) or `2` (strength):<br>&emsp;a.Display the respective submenu.<br>&emsp;b. Validate `sub_choice` between 1-3<br>&emsp;c. Prompt for duration; Loop until `Duration >= 0`.<br>&emsp;d. Map choice to activity name.<br>&emsp;e. Add `Duration` to running total.<br>5. If `3` (Summary):<br>&emsp;a. Calculate `total_active = total_cardio + total_strength`.<br>&emsp;b. Determine goal achivement status ($>= 120 min)<br>&emsp;c. Display formatted summary report.<br>6. If `4` (Exit): Display the exit farewell and terminate. | Invalid input warning messages.<br> Success confirmation of logged minutes  and activity name<br> Formatted Activity Summary<br>&emsp;- Total Cardio Minutes<br>&emsp;- Total Strength Minutes<br>&emsp;- total active minutes<br>&emsp;- Weekly Goal Status Message <br>&emsp;- exit Farewell Message |
