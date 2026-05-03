\# **LED Toggle Controller with OLED Feedback**



This project uses an Arduino (or similar microcontroller) to control three LEDs (Green, Red, Yellow) using three physical push buttons. Unlike a momentary switch, this code implements \*\*toggle logic\*\*: press once to turn the LED on, press again to turn it off. The status of the LEDs is displayed in real-time on an I2C OLED screen.



\## Features

\- \*\*Toggle Logic\*\*: LEDs stay on after the button is released.

\- \*\*Debouncing\*\*: Software-level debouncing to prevent accidental double-triggers.

\- \*\*OLED Interface\*\*: Real-time status updates on a 128x64 SSD1306 display.

\- \*\*Edge Detection\*\*: Detects the exact moment a button is pressed to change states.



\## Components Required

\- 1x Arduino (Uno, Nano, or ESP32)

\- 1x SSD1306 I2C OLED Display (128x64)

\- 3x LEDs (Green, Red, Yellow)

\- 3x Push Buttons

\- 3x 220Ω Resistors (for LEDs)

\- Jumper wires and Breadboard



\## Wiring Diagram



| Component | Pin | Note |

| :--- | :--- | :--- |

| \*\*Green LED\*\* | Pin 4 | Connect through 220Ω resistor |

| \*\*Red LED\*\* | Pin 10 | Connect through 220Ω resistor |

| \*\*Yellow LED\*\*| Pin 2 | Connect through 220Ω resistor |

| \*\*Green Button\*\*| Pin 6 | To 5V (if using INPUT\_PULLDOWN) |

| \*\*Red Button\*\* | Pin 9 | To 5V (if using INPUT\_PULLDOWN) |

| \*\*Yellow Button\*\*| Pin 7 | To 5V (if using INPUT\_PULLDOWN) |

| \*\*OLED SDA\*\* | SDA (A4) | I2C Data |

| \*\*OLED SCL\*\* | SCL (A5) | I2C Clock |



\## Installation

1\. Install the following libraries via the Arduino Library Manager:

&#x20;  - `Adafruit GFX Library`

&#x20;  - `Adafruit SSD1306`

2\. Copy the code provided in the main file.

3\. Upload to your board.



\## Logic Explanation

The program tracks the `lastButtonState` for each button. It only toggles the LED `state` (true/false) when it detects a transition from `LOW` to `HIGH`. This ensures that holding the button down doesn't cause the light to flicker.

