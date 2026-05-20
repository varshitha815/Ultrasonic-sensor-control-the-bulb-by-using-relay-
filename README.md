# Ultrasonic-sensor-control-the-bulb-by-using-relay-
Here is a simple explanation of how to control a bulb using an IR sensor (and relay) with an Arduino/ESP32.

COMPOUNDS REQUIRED 

Arduino UNO or ESP32
IR sensor module
Relay module
Bulb
Jumper wires

WORKING PRINCIPLE 

The IR sensor detects an object or hand.
When an object comes near the sensor, the sensor output changes.
The Arduino reads this signal.
The Arduino turns the relay ON or OFF.
The relay controls the bulb.

 
CODE

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
