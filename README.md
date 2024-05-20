# Automatic Garage Door Opener

## Overview

This project is an automatic garage door opener that uses an ultrasonic sensor to detect the presence of a car and control a stepper motor to open or close the garage door. Additionally, an LCD display provides status messages, and a buzzer alerts the user when the door is opening or closing.

## Components

- Arduino board (e.g., Uno, Mega)
- Ultrasonic sensor (HC-SR04)
- Stepper motor and driver
- LCD display with I2C interface
- Buzzer
- Breadboard and jumper wires

## Circuit Diagram

1. **Ultrasonic Sensor (HC-SR04)**
   - VCC to 5V
   - GND to GND
   - TRIG to digital pin 7
   - ECHO to digital pin 8

2. **Stepper Motor**
   - Connect the stepper motor to the driver according to the driver and motor specifications.
   - IN1 to digital pin 10
   - IN2 to digital pin 11
   - IN3 to digital pin 12
   - IN4 to digital pin 13

3. **LCD Display with I2C Interface**
   - VCC to 5V
   - GND to GND
   - SDA to A4
   - SCL to A5

4. **Buzzer**
   - Positive terminal to digital pin 2
   - Negative terminal to GND

## Code Explanation

### Libraries

- `Wire.h`: For I2C communication.
- `NewPing.h`: For ultrasonic sensor functionality.
- `AccelStepper.h`: For controlling the stepper motor.
- `LiquidCrystal_I2C.h`: For controlling the LCD display.

### Variables and Objects

- `buzzerPin`: Pin for the buzzer.
- `stepper`: Stepper motor control object.
- `lcd`: LCD display control object.
- `sonar`: Ultrasonic sensor control object.
- `distance`: Variable to store the measured distance from the sensor.
- `threshold`: Distance threshold for detecting a car.
- `closeState`, `openState`: Boolean flags to track the state of the garage door.

### Setup

In the `setup()` function:
- The LCD is initialized, and a welcome message is displayed.
- The buzzer pin is set as OUTPUT.
- Serial communication is initialized for debugging.
- The stepper motor's speed and acceleration are configured.

### Loop

In the `loop()` function:
- The distance from the ultrasonic sensor is measured.
- If the distance is greater than the threshold and the door is not already closed:
  - The stepper motor closes the door, the buzzer sounds, and the LCD displays "Goodbye."
- If the distance is less than or equal to the threshold and the door is not already open:
  - The stepper motor opens the door, the buzzer sounds, and the LCD displays "Welcome Back."
- Status messages are updated on the LCD based on the door state.

## Usage Instructions

1. Assemble the circuit as per the circuit diagram.
2. Upload the provided code to the Arduino board.
3. Open the Serial Monitor from the Arduino IDE (Tools -> Serial Monitor) to view debug messages.
4. Power the system and place an object (e.g., a car) in front of the ultrasonic sensor to test the automatic door opening and closing.

## Example Output

- When an object is detected within the threshold distance, the LCD displays "Welcome Back," and the stepper motor opens the door.
- When no object is detected within the threshold distance, the LCD displays "Goodbye," and the stepper motor closes the door.

Enjoy the convenience of an automated garage door opener and explore further enhancements to the system!

---

This README format provides clear instructions and explanations, helping users understand and replicate your project. If you have another project, please provide its code and a brief description, and I'll create a similar README for it.
