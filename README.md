# microcontrollers-101

Project Overview

This project uses the AVR64DD32 microcontroller to control two LEDs (RIGHT_EYE and LEFT_EYE) that blink simultaneously every second, creating a simple owl eyes effect. The project was generated using MPLAB Code Configurator (MCC) with the Melody framework.
Hardware Requirements

Microcontroller: AVR64DD32
LEDs: 2x LEDs (for left and right eyes)
Resistors: 2x current-limiting resistors (typically 220Ω - 1kΩ depending on LED specifications)
Power Supply: 3.3V or 5V (depending on your setup)
Breadboard/PCB: For connections

Pin Configuration

The project uses two GPIO pins configured as outputs:

RIGHT_EYE - Controls the right eye LED
LEFT_EYE - Controls the left eye LED

Note: Specific pin assignments are defined in the MCC-generated configuration files.

Software Requirements

MPLAB X IDE (for development)
XC8 Compiler v3.00 or later
MPLAB Code Configurator (MCC) v5.5.1 or later

Project Structure

owl-eyes-avr64dd32/
├── main.c                           # Main application code
├── compile_flags.txt                # Compiler flags for development
├── mcc-manifest-generated-success.yml # MCC configuration manifest
├── mcc-manifest-autosave.yml        # MCC autosave manifest
├── mcc_generated_files/             # MCC generated system files
└── README.md                        # This file

How It Works
The main application runs in a simple infinite loop:

Turn ON both LEDs (RIGHT_EYE and LEFT_EYE)
Wait 1000ms (1 second)
Turn OFF both LEDs
Wait 1000ms (1 second)
Repeat the cycle

The system operates at 4MHz (F_CPU = 4000000UL) and uses the _delay_ms() function for timing.

Circuit Diagram

AVR64DD32
    |
    ├── RIGHT_EYE_PIN ──[220Ω]──── LED1 ──── GND
    |
    └── LEFT_EYE_PIN  ──[220Ω]──── LED2 ──── GND
    
Building and Flashing

Open the project in MPLAB X IDE
Build the project (Build → Build Project)
Connect your AVR64DD32 to a compatible programmer/debugger
Program the device (Run → Run Project)

Configuration
The project uses MCC (MPLAB Code Configurator) with the following modules:

AVR 8-bit core
Configuration bits
Pin manager
Clock controller
Interrupt manager

To modify pin assignments or add features:

Open MCC in MPLAB X
Modify the pin configuration in Pin Manager
Regenerate the code
Build and program

Customization Ideas

Blink Pattern: Modify the delay values for different blink speeds
Asymmetric Blinking: Add different delays for each eye
Fade Effect: Use PWM to create a fade in/out effect
Random Blinking: Add random delays to make it more lifelike
Additional LEDs: Add more LEDs for a more complex owl face

License
This project is based on Microchip's generated code templates and follows their licensing terms. Please refer to the license header in the source files for specific terms.
Contributing
Feel free to fork this project and submit pull requests for improvements or additional features!

Troubleshooting

LEDs not blinking: Check pin connections and current-limiting resistors
Build errors: Ensure XC8 compiler is properly installed and configured
Programming issues: Verify programmer connection and device selection

