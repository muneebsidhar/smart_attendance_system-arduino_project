# 🎓 Smart Attendance System (Arduino + RFID)

A contactless attendance system built with an **Arduino Uno** and an **RC522 RFID module**. A student scans their RFID card, the system checks the card's unique ID, shows the student's name and ID on a 16×2 LCD, and confirms with a buzzer and LED. Unknown cards are rejected with an error message.

---

## 📖 Overview

Manual attendance takes time and is easy to get wrong or fake. This project makes attendance marking automatic: each RFID card carries a unique ID, so only authorized cards are accepted, and marking attendance takes only a few seconds. It is suitable for classrooms, offices and other places where many people mark attendance every day.

---

## 🎯 Aim

- Mark attendance in seconds and reduce errors compared to manual methods
- Keep the process easy and contactless
- Prevent fake attendance by using unique card IDs
- Stay expandable for future features such as data storage or mobile alerts

---

## ✅ Objectives

- Detect student presence using an RFID card scanned by the RC522 module
- Read the card's unique ID and send it to the Arduino for verification
- Display the student's name and ID on a 16×2 LCD when a valid card is detected
- Give a sound alert with a buzzer and light an LED when attendance is marked
- Show an error / invalid card message on the LCD when an unknown card is scanned

---

## ✨ Features

- Contactless attendance with RFID cards or tags
- Student name and ID shown on a 16×2 LCD
- Buzzer and LED confirmation on a successful scan
- Rejects unknown or invalid cards with an error message
- Fast and accurate marking, suitable for schools and colleges
- Easy to connect to the Arduino through the module's male header pins
- Can be extended to store records on a computer

---

## 🧰 Hardware Required

| No. | Component | Description |
| :-: | --------- | ----------- |
| 1 | Arduino board | Arduino UNO R3 development board |
| 2 | RFID module | RC522 RFID module |
| 3 | RFID cards / tags | Unique ID cards for students |
| 4 | LCD display | JHD162A 16×2 LCD |
| 5 | Buzzer | Active buzzer for alert sound |
| 6 | LED | Indicator LED for successful scan |
| 7 | Jumper wires | Connecting wires for the circuit |
| 8 | Breadboard | For easy connections and testing |
| 9 | Power supply | DC adapter for the Arduino |

## 💻 Software Required

- Arduino IDE

---

## 📡 About the RC522 RFID Module

| Property | Detail |
| -------- | ------ |
| Chip | MFRC522 |
| Frequency | 13.56 MHz |
| Interface | SPI |
| Reading distance | About 2–5 cm |
| Module voltage | 3.3 V |
| Capabilities | Reads and writes RFID cards and tags |
| Indicators | Power LED (module is on) and I/O LED (blinks when a card is detected) |

**Header pins:** SDA (SS), SCK, MOSI, MISO, IRQ (optional), GND, RST, 3.3V

The MFRC522 chip needs a 27.12 MHz crystal oscillator for a stable clock, which the module already includes. The antenna is a copper coil printed on the PCB, so no external antenna is needed.

> ⚠️ The RC522 module runs on **3.3 V**. Connect its power pin to the Arduino's **3.3V** pin, not 5V.

---

## 🔌 Circuit Connections

Add your wiring table here once finalized, for example:

| Component pin | Arduino pin |
| ------------- | ----------- |
| RC522 SDA (SS) | `<pin>` |
| RC522 SCK | `<pin>` |
| RC522 MOSI | `<pin>` |
| RC522 MISO | `<pin>` |
| RC522 RST | `<pin>` |
| RC522 3.3V / GND | 3.3V / GND |
| LCD (RS, E, D4–D7) | `<pins>` |
| Buzzer | `<pin>` |
| LED | `<pin>` |

You can also add a circuit diagram or photo of your setup here.

---

## ⚙️ How It Works

1. The student brings their RFID card close to the RC522 reader.
2. The reader detects the card and reads its unique ID.
3. The Arduino compares the ID with the list of authorized cards.
4. **Valid card:** the LCD shows the student's name and ID, the buzzer sounds and the LED turns on.
5. **Unknown card:** the LCD shows an error / invalid card message.

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   ```
2. Open the `.ino` sketch in the **Arduino IDE**.
3. Install the required libraries from **Sketch → Include Library → Manage Libraries**:
   - `MFRC522` (for the RC522 module)
   - `LiquidCrystal` (included with the Arduino IDE)
4. Wire the components as shown in the circuit connections section.
5. Select **Arduino Uno** under **Tools → Board** and choose the correct port.
6. Upload the sketch.
7. Add your students' card IDs and names in the sketch, then scan a card to test.

---

## ⚠️ Limitations

- Works only with RFID cards
- Needs a power supply to work
- Reads one card at a time
- Cannot verify that the card holder is physically the student (a card can be used by someone else)

---

## 🔮 Future Improvements

- Save attendance records to a computer (for example CSV or database)
- Add a real-time clock to record date and time
- Send mobile alerts or notifications
- Add fingerprint or other verification to stop proxy attendance

---

## 👤 Author

Muneeb Ur Rehman Sidhar
Computer Science, University of Engineering and Technology (UET), Taxila

---

