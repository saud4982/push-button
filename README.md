🚀 Servo Motor Control Using Push-Button and Arduino
📖 Project Overview
This project demonstrates how to control a servo motor using a push-button and an Arduino Uno. When the button is pressed, the servo motor rotates to a certain angle (e.g., 90°). When the button is released, it returns to the original position (e.g., 0°). This setup is commonly used in automation systems, robotics, and interactive devices.

🔧 Components Required
1 × Arduino Uno (or compatible board)

1 × SG90 Servo Motor

1 × Push-button

1 × 10kΩ Resistor (for pull-down)

Jumper wires

Breadboard

USB cable / external power source

🔌 Circuit Diagram
✅ Servo Motor Connections:
Servo Wire	Arduino Pin
GND (Brown/Black)	GND
VCC (Red)	5V
Signal (Orange)	D9

✅ Push-button Connections:
Button Pin	Arduino Pin
One side	D2
Other side	GND
Pull-down resistor	Between D2 and GND (10kΩ)

💻 Arduino Code
cpp
Copy
Edit
#include <Servo.h>

Servo myServo;
const int buttonPin = 2;
bool buttonState = false;

void setup() {
  pinMode(buttonPin, INPUT);
  myServo.attach(9);
  myServo.write(0); // Start at 0 degrees
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {
    myServo.write(90); // Move to 90 degrees
  } else {
    myServo.write(0); // Move back to 0 degrees
  }

  delay(100); // Basic debounce
}
🧠 How It Works
When the button is not pressed, the servo stays at 0°.

When the button is pressed, the servo rotates to 90°.

Once released, it returns to 0°.

A 10kΩ pull-down resistor ensures the input pin stays LOW when the button is not pressed.

📦 Potential Improvements
Add a second button to control reverse rotation

Use interrupts for more efficient input handling

Add an LCD to show servo position

Use a potentiometer for manual angle control

📸 Project Demo (Optional)
Add photos or videos of your working project here.# push-button
