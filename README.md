# IoT-Based Air Monitoring System

## Project Overview

A low-cost IoT-based environmental air monitoring prototype
developed using an STM32F446RE Nucleo board, MQ135/MQ7 gas
sensors and Raspberry Pi 3B.

The STM32 collects sensor data and performs range classification.
The Raspberry Pi acts as an IoT gateway and sends the processed
data to ThingSpeak over Wi-Fi for near real-time monitoring.

## Technologies Used

### Hardware:
- STM32F446RET6 Nucleo Board
- Raspberry Pi 3 Board
- MQ-135 sensor 
- MQ-7 sensor
- Jumper Wires
- D-Link Router

### Software: 
- STM32CubeMX
- Keil IDE
- VNC Viewer
- ThingSpeak
 
## System Architecture

MQ135 / MQ7 → STM32F446RE → GPIO → Raspberry Pi 3B → Wi-Fi → ThingSpeak 

## Key Features

- Analog gas sensor interfacing
- ADC-based sensor acquisition
- Three-level sensor range classification
- STM32-to-Raspberry Pi GPIO communication
- Raspberry Pi gateway implementation
- ThingSpeak cloud integration
- Near real-time data visualization

## Skills Demonstrated

- STM32F401RE microcontroller
- Embedded C
- Proteus VSM simulation
- ADC
- UART communication
- Sensor interfacing
- Debugging and testing

## My Contribution

- Designed the overall IoT system architecture
- Selected the STM32F446RE, Raspberry Pi 3B, MQ135 and MQ7
- Developed Embedded C firmware for STM32
- Implemented ADC-based sensor reading
- Implemented sensor range classification
- Developed Raspberry Pi Python GPIO interface
- Integrated the system with ThingSpeak
- Configured remote Raspberry Pi access using VNC
- Performed hardware testing and debugging / Debugged hardware/firmware interaction.

## Engineering Challenges

### Challenge 1 — Noisy low-cost sensor output

The MQ135 and MQ7 sensors produce noisy analog output and do
not directly provide reliable PPM values.

### Solution

Implemented an 8-bit ADC-based three-band classification approach
to provide indicative pollution severity levels.

### Challenge 2 — Limited communication pins

The STM32 needed to communicate the classified sensor status
to the Raspberry Pi using limited GPIO resources.

### Solution

Used two digital GPIO signals per sensor to encode the
three classification bands.

## Limitations

The current prototype provides indicative pollution severity
levels rather than calibrated PPM measurements.

The MQ135/MQ7 output is classified into predefined ranges.
Future work will include proper sensor calibration and
PPM conversion.

## Results

The system successfully transmitted sensor readings from the
STM32 through the Raspberry Pi gateway to ThingSpeak.

The ThingSpeak dashboard displayed the sensor data as live
field charts at approximately 15-second intervals.
