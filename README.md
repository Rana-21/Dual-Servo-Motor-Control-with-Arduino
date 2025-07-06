# Dual-Servo-Motor-Control-with-Arduino
This Arduino project demonstrates how to control two servo motors  using PWM with Arduino Uno. The motors move in opposite directions simultaneously using external power for safety and performance.

Components:
- Arduino Uno  
- 2 × SG90 Servo Motors  
- Breadboard  
- Jumper wires  
- External 5V power supply (batteries or adapter)

Wiring
- **Servo 1 Signal** → Arduino pin 4  
- **Servo 2 Signal** → Arduino pin 5  
- **VCC** (both servos) → 5V from external power  
- **GND** → Connect Arduino GND and power supply GND together

  Code :
  #include <Servo.h>

Servo servo1; 
Servo servo2;  

void setup() {
  servo1.attach(4);  
  servo2.attach(5);  
}

void loop() {
  for (int angle = 0; angle <= 180; angle++) {
    servo1.write(angle);
    servo2.write(180 - angle); 
    delay(15);
  }

  delay(1000);

 
  for (int angle = 180; angle >= 0; angle--) {
    servo1.write(angle);
    servo2.write(180 - angle);
    delay(15);
  }

  delay(1000);
}
