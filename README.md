# Remaining: Timewarrior extension for management of working hours

This extension is aimed to enhance the reports provided by timewarrior, calculating the amount of hours worked during the month and comparing them with the total of hours that should be spent. Days off are managed using the exclusion option in the config file.

</br>

> ⚠ If you hit any problems or want to request a feature, please create an [issue on the repo](https://github.com/lmoyasans/timewarrior_remaining_extension).

</br>

---

## Base functionality
Extension is executed as `timew remaining`. This will display a calendar with '-' for the week days not belonging to that month and 0 or some number for the rest. Days off are not specifically displayed in the calendar but considered in the background.

In the right part, the calendar displays also the remaining hours per week. Negative numbers mean less hours than expected and positive number are extra hours.

### Constants / Config file
**Remaining** depends on the working hours specified by the user. This should be indicated prior to the execution of the extension as a constant in the configuration file. The constant can be changed by modifying the timewarrior.cfg file or by using the timew config command:
`remaining.hours_per_day = HOURS` or `timew config remaining.hours_per_day HOURS`.

---

## Integration with calculatePast: historical report of past months
**CalculatePast** is made to provide **Remaining** support with past months, taking into account their remaining or extra hours. Also, it can help visualize the complete hour report from the past months if the verbose mode is selected.

To execute it, enter `timew calculatePast` in the terminal

### Constants / Config file
Before using the calculatePast subextension, the user should define the start_date, so it can calculate work time from the start of the contract or period desired. This can be set modifying the timewarrior config file adding `remaining.start_date = YYYY-MM-DD` or using `timew config remaining.start_date YYYY-MM-DD`.

If the user wants to see the calendar of all the past months of the period define, the verbose mode should be enabled as `remaining.verbose = yes` or `timew config remaining.verbose yes`. Otherwise, the remaining.verbose should be set to `remaining.verbose=no`.

During the execution, the extension will add a a new line to the configuration files (`remaining.past_hours = HOURS`) with the remaining /extra hours from past months. This will be used automatically with the remaining main extension to calculate the new totals.


