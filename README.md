Smart Trash Bin
This project is an IoT-based smart trash bin system built with ESP32, ultrasonic sensors, a servo motor, and an OLED display. It monitors the trash level inside the bin and automatically opens the lid when someone approaches.

Features
Automatic lid opening: A proximity sensor detects when a person is near and opens the lid via a servo motor.

Trash level measurement: Uses a second ultrasonic sensor to measure how full the trash bin is.

OLED display: Shows the current fill percentage and trash status.

Arduino IoT Cloud integration: Sends the trash fill level and status text to the cloud for remote monitoring.

Serial monitor output: Logs distance and fill level readings for debugging.

Hardware Components
ESP32 development board

Two HC-SR04 ultrasonic sensors

Servo motor (connected to lid)

OLED display (SSD1306 128x64)

Connecting wires and power supply

Pin Configuration
Component	ESP32 Pin
Ultrasonic Sensor 1 TRIG	GPIO 4
Ultrasonic Sensor 1 ECHO	GPIO 5
Ultrasonic Sensor 2 TRIG	GPIO 12
Ultrasonic Sensor 2 ECHO	GPIO 13
Servo Motor	GPIO 18
OLED Display (I2C)	GPIO 21(SDA), GPIO 22(SCL)

How It Works
The first ultrasonic sensor detects if an object (e.g., a hand) is closer than 3 cm and opens the lid by turning the servo motor to 90 degrees. After 3 seconds, the lid closes automatically.

The second ultrasonic sensor measures the distance to the trash level inside the bin.

The distance is mapped to a fill percentage (0-100%), and the status text updates accordingly.

Fill level and status are displayed on the OLED and sent to the Arduino IoT Cloud.

Readings are printed on the serial monitor every 10 seconds.

Usage
Configure your WiFi and Arduino IoT Cloud credentials in the arduino_secrets.h file.

Upload the code to your ESP32 device.

Open the serial monitor to view debug information.

Monitor the trash fill level remotely via the Arduino IoT Cloud dashboard.

Dependencies
ArduinoIoTCloud library

ESP32Servo library

Adafruit GFX and SSD1306 libraries

Install these via the Arduino Library Manager.