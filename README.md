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


---

## 3. Pseduocode

...

```

MODULE main()
    DECLARE Integer total_cardio = 0
    DECLARE Integer total_strength = 0
    DECLARE integer total_active = 0
    DECLARE string main_choice = ""
    DECLARE String sub_choice = ""
    DECLARE Real Duration = 0.0
    DECLARE String activity_name = ""

    print("==========================================")
    print("        PERSONAL FITNESS TRACKER            ")
    print("==========================================")

    WHILE true
        // Step 1: Main menu & Input Validation
        DISPLAY "---MAIN MENU---"
        DISPLAY "1. Log Cardio Workout"
        DISPLAY "2. Log Strength Workout"
        DISPLAY "3. View Activity Summary"
        DISPLAY "4. Exit"
        DISPLAY "Enter your choice (1-4):"
        INPUT main_choice

        WHILE main_choice != 1 AND main_choice != 2 AND main_choice != 3 AND main_choice != 4
          DISPLAY "Invalid. Choice must be 1, 2, 3, or 4. Try Again:"
          INPUT main_choice
        END WHILE

        // Step 2: Route Submenu and Actions
        IF main_choice = 1
        DISPLAY "--- CARDIO MENU ---"
        DISPLAY "1. Running / Jogging"
        DISPLAY "2. Cycling"
        DISPLAY "3. Swimming:"
        DISPLAY "Enter cardio activity (1-3):"
        INPUT sub_choice

        WHILE sub_choice != 1 AND sub_choice != 2 AND sub_choice != 3
          DISPLAY "Invalid. Please enter 1, 2, or 3. Try Again!"
          INPUT sub_choice
        END WHILE

        IF sub_choice == 1 THEN
          activity_name = "Running/Jogging"
        ELSE sub_choice == 2 THEN
          activity_name = "Cycling"
        ELSE
          activity_name = "Swimming"
        END IF

        DISPLAY "Enter Duration in minutes."
        INPUT Duration
        WHILE Duration < 0
            DISPLAY "Invalid. Please enter a value >= 0:"
            INPUT Duration
        END WHILE

        total_cardio = total_cardio + Duration
        DISPLAY "Successfully added ", Duration, "minutes for ", activity_name, "."

        ELSE IF main_choice == 2 THEN
            DISPLAY "---STRENGTH MENU---"
            DISPLAY "1. Log Cardio Workout"
            DISPLAY "2. Log Strength Workout"
            DISPLAY "3. View Activity Summary"
            DISPLAY "4. Exit"
            DISPLAY "Enter your choice (1-4):"

        WHILE sub_choice != 1 AND sub_choice != 2 AND sub_choice != 3
          DISPLAY "Invalid. Please enter 1, 2, or 3. Try Again!"
          INPUT sub_choice
        END WHILE

        IF sub_choice == 1 THEN
          activity_name = "Upper Body"
        ELSE sub_choice == 2 THEN
          activity_name = "Lower Body"
        ELSE
          activity_name = "Core & Flexibility"
        END IF

        DISPLAY "Enter Duration in minutes."
        INPUT Duration
        WHILE Duration < 0
            DISPLAY "Invalid. Please enter a value >= 0:"
            INPUT Duration
        END WHILE

        total_strength = total_strength + Duration
        DISPLAY "Successfully added ", Duration, "minutes for ", activity_name, "."

       ELSE IF main_choice == 3 THEN
            total_active = total_cardio + total_strength
            DISPLAY "=========================================="
            DISPLAY "ACTIVITY SUMMARY"             
            DISPLAY "=========================================="
            DISPLAY "Total Cardio:", total_cardio
            DISPLAY "Total Strength:", total_strength
            DISPLAY "Total Active:", total_active
            IF total_active >= 120 THEN
                DISPLAY "Status: Goal achieved! You exceeded 120 weekly active minutes."
            ELSE IF total_active > 0 THEN
                DISPLAY "Status: Keep Going! ", (120 - total_active), " more minutes needed to hit your weekly target!"
            ELSE
                DISPLAY "Status: No workouts logged yet..."
            END IF
            DISPLAY "=========================================="



    ```
