SOIL-MOISTURE-DETECTOR-SYSTEM 
This is a system  that detects the moisture content of the soil, it tells how dry or wet the soil is. It can be deployed by farmers to detect how much water content the soil needs.
it measures the water content in soil and helps monitor irrigation needs. This project is ideal for **smart agriculture**, **gardening**, and **automated plant watering systems**.  


 Overview  
This system uses a **soil moisture sensor** to detect the moisture level in the soil and an **Arduino microcontroller** to process the readings. Depending on the setup, the system can:  

- Display moisture levels on the serial monitor.  
- Trigger a buzzer to alert when soil is dry.  
- Automatically switch on a **water pump/relay module** for irrigation.  

 Components Used  
ESP32 (or compatible board)  
- Soil Moisture Sensor  
  BUZZER A(for soil dry alert) 
- Jumper wires, breadboard, power supply.

- Code
- // Soil Moisture Detector System
// Simple version with LED alert

int sensorPin = A0;   // Soil moisture sensor connected to A0
int sensorValue = 0;  
int ledPin = 13;      // LED on pin 13

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  sensorValue = analogRead(sensorPin);
  Serial.print("Soil Moisture Value: ");
  Serial.println(sensorValue);

  // Adjust threshold depending on your soil/sensor
  if (sensorValue < 500) {  
    Serial.println("Soil is Dry - Water Needed!");
    digitalWrite(ledPin, HIGH);  // LED ON
  } else {
    Serial.println("Soil is Moist - No Water Needed.");
    digitalWrite(ledPin, LOW);   // LED OFF
  }

  delay(1000); // wait 1 second
}
