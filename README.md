# Fire Fighting Bot

## Overview
This Arduino project is designed to detect fire and control a water pump. Additionally, it allows for controlling the movement of a robot via serial communication. The robot can move in various directions and speeds based on received serial commands.

## Components Required
- Arduino Board
- Motor Driver (e.g., L298N)
- DC Motors
- Water Pump
- Flame Sensor
- Jumper Wires
- Power Supply
- Breadboard

## Pin Configuration
- Motor Driver ENA: Pin 5
- Motor Driver IN1: Pin 6
- Motor Driver IN2: Pin 7
- Motor Driver IN3: Pin 8
- Motor Driver IN4: Pin 9
- Motor Driver ENB: Pin 10
- Water Pump: Pin 13
- Flame Sensor: Analog Pin A0

## Sensor Calibration
- Minimum sensor reading: 50
- Maximum sensor reading: 1024

## Serial Commands
- `S`: Stop
- `B`: Move Backward
- `F`: Move Forward
- `R`: Turn Right
- `L`: Turn Left
- `J`: Backward Right
- `H`: Backward Left
- `I`: Forward Right
- `G`: Forward Left
- `1` to `9` and `q`: Set Speed (from slowest to fastest)

## Functions
- `left()`: Turns the robot left.
- `right()`: Turns the robot right.
- `forward()`: Moves the robot forward.
- `backward()`: Moves the robot backward.
- `forward_left()`: Moves the robot forward and left.
- `forward_right()`: Moves the robot forward and right.
- `back_left()`: Moves the robot backward and left.
- `back_right()`: Moves the robot backward and right.
- `stopy()`: Stops the robot.

## Installation and Setup
1. **Wiring**: Connect the components according to the pin configuration.
2. **Upload Code**: Upload the provided code to the Arduino board using the Arduino IDE.
3. **Serial Monitor**: Open the Serial Monitor in the Arduino IDE to send commands and observe sensor readings.

## Usage
1. **Fire Detection**: The flame sensor reads values from analog pin A0. The water pump is activated if fire is detected within a certain range.
   - Close Fire: The sensor reading is mapped to a range value of 0.
   - Distant Fire: The sensor reading is mapped to a range value of 1.
   - No Fire: The sensor reading is mapped to a range value of 2.
2. **Robot Control**: Use the serial monitor to send commands to control the robot's movement and speed.

## Code Explanation
- **Setup Function**: Initializes the serial communication, sets pin modes for the motor driver and pump.
- **Loop Function**: Continuously reads the flame sensor value, maps it to a range, and activates the pump accordingly. It also checks for incoming serial commands to control the robot's movements.
- **Movement Functions**: Define the motor control logic for various movements (left, right, forward, backward, etc.).
- **Speed Control**: Adjusts the speed of the motors based on received commands.


## Notes
- Ensure the power supply is adequate for both the motors and the water pump.
- Calibrate the flame sensor as per your requirements by adjusting the `sensorMin` and `sensorMax` values.
- Use the serial monitor to debug and verify the functionality of the system.

## License
This project is open-source and can be modified and distributed under the terms of the MIT license. Feel free to improve and adapt it to your needs.
