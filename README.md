# 🕒 Dual Time Display (Digital + Analog) using ESP32  

This project is a **Dual Time Display System** using an **ESP32 and an OLED screen (SSD1306)**. It displays **two different time zones** in both **digital** and **analog clock** formats. The ESP32 synchronizes time using an **NTP (Network Time Protocol) server**, ensuring accurate and real-time updates.  

## 📌 Features  
✔️ Displays **two different time zones** on an OLED screen.  
✔️ Shows **both digital and analog clock formats**.  
✔️ Uses **Wi-Fi and NTP server** for accurate time synchronization.  
✔️ Compact, efficient, and low-power solution.  
✔️ Smoothly updates time with a real-time animation effect.  

## 🔧 Hardware Requirements  
- **ESP32** microcontroller  
- **OLED Display (SSD1306, 128x64)**  
- **Jumper wires**  
- **5V power supply**  

## 🛠️ Setup Instructions  

### Step 1: Connect the OLED Display  
Connect the **SSD1306 OLED** to the ESP32 using I2C:  

| OLED Pin | ESP32 Pin |
|----------|----------|
| VCC      | 3.3V     |
| GND      | GND      |
| SCL      | GPIO 22  |
| SDA      | GPIO 21  |

### Step 2: Install Arduino IDE  
- Download & install **Arduino IDE** from [here](https://www.arduino.cc/en/software).  

### Step 3: Add ESP32 Board to Arduino IDE  
1. Open **Arduino IDE**  
2. Go to **File -> Preferences** (Shortcut: `Ctrl + ,`)  
3. Copy and paste this URL into **Additional Board Manager URLs**: "https://espressif.github.io/arduino-esp32/package_esp32_index.json"
4. Click **OK**, then install **ESP32 Board** from the Board Manager.  

### Step 4: Install Required Libraries  
Install the following libraries from the **Library Manager**:  
- **WiFi** (for ESP32 Wi-Fi connection)  
- **NTPClient** (for fetching time from NTP servers)  
- **Adafruit_GFX** (for graphics support)  
- **Adafruit_SSD1306** (for OLED display)  

### Step 5: Configure Wi-Fi and Time Zones  
1. Open the **Arduino sketch**.  
2. Enter your **Wi-Fi SSID and Password**.  
3. Set the **time zones** in the code:  
```cpp
const long gmtOffset1 = 3600 * 5.5;  // Time Zone 1 (GMT+5:30 for IST)
const long gmtOffset2 = 3600 * -4;   // Time Zone 2 (GMT-4 for EST)
