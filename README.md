# Remaining: Timewarrior extension for management of working hours
## Base functionality
### Constants / Config file
Remaining works depending on the working hours specified by the user. This should be indicated prior to the execution of the extension as a constant in the configuration file. The constant can be changed by modifying the timewarrior.cfg file or by using the timew config command.
'''
remaining.hours_per_day = HOURS
'''
or 
'''
timew config remaining.hours_per_day HOURS
'''
## Integration with calculatePast: historical report of past months
### Constants / Config file
