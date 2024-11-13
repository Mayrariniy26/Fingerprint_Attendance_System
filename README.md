# SMART ATTENDANCE SYSTEM USING FINGERPRINT RECOGNITION

## System Architecture

The Fingerprint Attendance System is designed for secure, efficient attendance tracking by capturing and verifying fingerprints. The system integrates an AS608 fingerprint sensor, microcontroller, and LCD display for real-time user feedback, ensuring secure data storage and accurate attendance logs.

![System Architecture](https://github.com/user-attachments/assets/ab92a1d6-c05d-40b8-879e-0952b64b1d52)

## System Design

### Hardware Components
- **Arduino UNO Board**
- **AS608 Fingerprint Sensor**
- **DS3231/DS1307 RTC Module**
- **16x2 LCD Display with I2C Module**
- **Bluetooth Module HC-05**
- **5V Buzzer**
- **LED Indicators (Green and Blue)**
- **Breadboard, Jump Wires, and Resistors (100-Ohm)**

### Software Components
- **Arduino IDE** for programming and deployment
- **Adafruit Fingerprint Sensor Library** for fingerprint handling
- **LiquidCrystal I2C Library** for LCD integration

## AS608 Fingerprint Sensor

![AS608 Sensor](https://github.com/user-attachments/assets/f3474d17-97d0-4e4d-8206-19994609311e)

The AS608 Fingerprint sensor, based on the AS608 chip, captures fingerprints and sends data to the microcontroller via serial communication. It supports storage of up to 255 fingerprint IDs, making it ideal for attendance systems. The sensor is compatible with Arduino, ESP8266, and ESP32 development boards, offering both fingerprint comparison (1:1) and fingerprint search (1:N) matching modes for precise identification.

#### Specifications
- **Operation Voltage:** 3.3V
- **Interface:** TTL Serial, adjustable baud rate (9600 to 57600; default 57600)
- **Rated Current:** ~120mA
- **Fingerprint Imaging Time:** <1.0 second
- **Storage Capacity:** 255 templates
- **Template File Size:** 512 bytes
- **False Acceptance Rate:** <0.001% (Security level 3)
- **False Reject Rate:** <1.0% (Security level 3)
- **Temperature Range:** -20°C to +50°C
- **Sensing Window Size:** 16x18 mm
- **Dimensions:** 45.1x20.3x18.6 mm

## The I2C (Inter-Integrated Circuit) Module

The I2C module simplifies wiring by allowing communication between multiple devices using only two wires: SDA (Serial Data) and SCL (Serial Clock). It’s ideal for connecting peripherals like LCDs and RTC modules, making it suitable for this attendance system’s low-speed communication needs.

![I2C Module](https://github.com/user-attachments/assets/28f3e77c-fe6c-4d3f-86f9-f95775ff598e)

#### Advantages of I2C
- Reduced wiring with only two lines for data and clock signals.
- Support for addressing, allowing multiple devices on the same bus.
- Simplifies code and usage with numerous Arduino libraries for peripherals.

## Connections

![Connection Diagram](https://github.com/user-attachments/assets/7f5e7986-c888-438d-9975-30ab56c3ca69)

### Key Connections
1. **AS608 Fingerprint Sensor**  
   - VCC: Connect to Arduino 5V  
   - TX/RX: Configured for serial communication with Arduino  

2. **LCD 16x2 Display with I2C Module**  
   - VCC/GND: Connect to Arduino 5V and GND  
   - SDA/SCL: Connect to Arduino A4 (SDA) and A5 (SCL)

3. **RTC Module**  
   - SDA/SCL: Connect to Arduino A4 (SDA) and A5 (SCL), shared with the LCD

4. **Buzzer and LEDs**  
   - **Buzzer:** Positive to digital pin (e.g., pin 5), Negative to GND (add resistor if needed)
   - **Green and Blue LEDs:** Positive to digital pins (e.g., pin 4 for green, pin 6 for blue), Negative through resistors to GND

## Next Steps

1. **Install Libraries**  
   - Open the Arduino IDE, go to *Manage Libraries*, and install the **Adafruit Fingerprint Sensor Library** and **LiquidCrystal I2C Library**.

2. **Enroll Fingerprints**  
   - Open the "Enroll" example in the Adafruit library to register fingerprints. The serial monitor will guide ID entry and fingerprint capture.

3. **Upload Code and Test**  
   - Compile and upload the code to the Arduino. Connect the board to your computer via USB and ensure the fingerprint sensor status is visible on the LCD. Once configured, place a finger on the sensor to check for recognition.

## Troubleshooting

- Check wiring connections and verify sensor placement.
- Ensure the **Fingerprint** and **I2C** libraries are installed.
- Re-enter fingerprint ID if unrecognized.

![Additional System Image](https://github.com/user-attachments/assets/eefede18-81e9-41cb-b5c6-5bc5516a9dad)

## Future Enhancements
Incorporating WiFi could improve data transfer over the Bluetooth module currently used, enhancing system scalability and network range.

## Additional Interface
This project includes a React web application that connects via Bluetooth API to retrieve IDs, though transitioning to WiFi for data sharing is a more efficient option.

![React Interface](https://github.com/user-attachments/assets/f7f36445-83c6-48e9-a6a2-0841956baf50)

---

This file can be added directly as `README.md` in your GitHub repository. It includes all relevant details about the project and is formatted for easy readability on GitHub. Let me know if you need further help!
