# Ultrasonic-sensor-control-the-bulb-by-using-relay-
Here is a simple explanation of how to control a bulb using an IR sensor (and relay) with an Arduino/ESP32.
Components Required
Arduino UNO or ESP32
IR sensor module
Relay module
Bulb
Jumper wires
Working Principle
The IR sensor detects an object or hand.
When an object comes near the sensor, the sensor output changes.
The Arduino reads this signal.
The Arduino turns the relay ON or OFF.
The relay controls the bulb.
Circuit Connections
IR Sensor
IR Sensor
Arduino
VCC
5V
GND
GND
OUT
D2
Relay Module
Relay
Arduino
VCC
5V
GND
GND
IN
D8
Arduino Code
C++
int irSensor = 2;     // IR sensor connected to pin 2
int relayPin = 8;     // Relay connected to pin 8

void setup() {
  pinMode(irSensor, INPUT);   // IR sensor as input
  pinMode(relayPin, OUTPUT);  // Relay as output

  digitalWrite(relayPin, LOW); // Bulb OFF initially
}

void loop() {

  int sensorValue = digitalRead(irSensor);

  // If object detected
  if (sensorValue == LOW) {

    digitalWrite(relayPin, HIGH); // Turn bulb ON
  }
  else {

    digitalWrite(relayPin, LOW); // Turn bulb OFF
  }
}
Code Explanation
1. Define Pins
C++
int irSensor = 2;
int relayPin = 8;
irSensor stores the IR sensor pin number.
relayPin stores the relay pin number.
2. Setup Function
C++
void setup()
This runs only once when the Arduino starts.
C++
pinMode(irSensor, INPUT);
Sets IR sensor pin as input.
C++
pinMode(relayPin, OUTPUT);
Sets relay pin as output.
C++
digitalWrite(relayPin, LOW);
Keeps bulb OFF initially.
3. Loop Function
C++
void loop()
Runs continuously.
C++
int sensorValue = digitalRead(irSensor);
Reads the IR sensor value.
4. Object Detection
C++
if (sensorValue == LOW)
IR sensor gives LOW when an object is detected.
C++
digitalWrite(relayPin, HIGH);
Relay turns ON.
Bulb glows.
5. No Object Detected
C++
digitalWrite(relayPin, LOW);
Relay turns OFF.
Bulb turns OFF.
Flow of Operation
Plain text
Hand/Object Near IR Sensor
        ↓
IR Sensor Detects Object
        ↓
Arduino Reads Signal
        ↓
Relay Turns ON
        ↓
Bulb Glows
Applications
Automatic room lights
Touchless switch system
Smart home automation
Energy saving systems
If you want, I can also provide:
Circuit diagram image
ESP32 version code
Ultrasonic sensor version
Project explanation for viva/project report
GitHub project structure