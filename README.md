# 6_automatic_garage_door
Automatic_garage_door

install the necessary libraries 

I used the closedState & opendState flag variables to make sure that the garage door doesn't keep closing/opening every time the ultrasonic detects or not detects an object.

When the ultrasonic detects an object at a minimum threshold value the Arduino sends a command to the stepper motor to open the garage door and the LCD display shows the appropriate message
