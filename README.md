# Bus Tracking System (GPS + GSM Based)

A real-time Vehicle/Bus Tracking System built using Arduino, GPS, and GSM modules.
This system retrieves live location coordinates (latitude and longitude) and sends them via SMS to a remote user upon request.

The system is designed to provide location-based tracking services for transportation monitoring and fleet management.

---

## Project Overview

The Bus Tracking System enables remote users to track a vehicle's real-time location using:

* GPS (Global Positioning System) for detecting coordinates
* GSM/GPRS module for sending SMS alerts
* LCD display for system status monitoring
* Arduino microcontroller for control logic

When a user sends the command **"Track Vehicle"**, the system fetches the latest GPS data and sends the current location via SMS.

---

## Key Features

* Real-time GPS location tracking
* SMS-based vehicle location response
* LCD display for live system status
* GSM network communication using AT commands
* Automatic module initialization
* Location-based tracking functionality

---

## System Working

1. The system initializes the LCD, GSM, and GPS modules.
2. GSM module connects to the mobile network using AT commands.
3. GPS module reads NMEA `$GPGGA` sentence data.
4. Latitude and Longitude values are extracted.
5. When the system detects the message **"Track Vehicle"**:

   * It fetches current GPS coordinates.
   * Sends the location details via SMS.
6. LCD displays system states such as initialization, GPS ready, and message sent.

---

## Hardware Components

* Arduino Uno (or compatible board)
* GPS Module (e.g., Neo-6M)
* GSM Module (SIM800 / SIM900)
* 16x2 LCD Display
* Active SIM card
* Jumper wires and power supply

---

## Pin Configuration

### LCD Connections

| LCD Pin | Arduino Pin |
| ------- | ----------- |
| RS      | 7           |
| EN      | 6           |
| D4      | 5           |
| D5      | 4           |
| D6      | 3           |
| D7      | 2           |

### GPS Module

| GPS Pin | Arduino Pin |
| ------- | ----------- |
| RX      | 10          |
| TX      | 11          |

---

## Technologies Used

* Embedded C (Arduino)
* GPS (Global Positioning System)
* GSM / GPRS (General Packet Radio Service)
* LiquidCrystal Library
* SoftwareSerial Library

---

## Code Highlights

### GSM Initialization

The system uses AT commands such as:

* `AT`
* `ATE0`
* `AT+CPIN?`
* `AT+CMGF=1`
* `AT+CMGS`

### GPS Data Extraction

* Reads `$GPGGA` NMEA sentence
* Parses comma-separated values
* Extracts latitude and longitude fields
* Displays coordinates on LCD
* Sends coordinates via SMS

---

## SMS Format

```
Vehicle Tracking Alert:
Your Vehicle Current Location is:
Latitude: <value>
Longitude: <value>
Please take some action soon.
Thank you
```

---

## Applications

* Public bus monitoring
* Fleet management systems
* Logistics and delivery tracking
* Emergency vehicle tracking
* Location-based mobile services

---

## Future Enhancements

* Google Maps link generation in SMS
* Web dashboard for live tracking
* Cloud database integration
* IoT-based monitoring using MQTT
* Real-time analytics for fleet optimization

---

## Learning Outcomes

This project demonstrates:

* Embedded systems programming
* GPS NMEA data parsing
* GSM AT command communication
* Serial communication handling
* Real-time tracking system design
* Implementation of location-based services

---

## License

This project is developed for academic and educational purposes.

---
