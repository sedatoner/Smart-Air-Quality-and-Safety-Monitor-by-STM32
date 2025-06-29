# 🌫 Smart Air Quality and Safety Monitor (STM32 Based)

This is a small project where I built an air quality monitor using an STM32 microcontroller and an MQ-135 gas sensor. Basically, it checks how clean or dirty the air is and gives visual/audio warnings if things get bad.

It's meant to be simple, practical, and kind of cool to build and show off. 😄

---

##  What It Does

- Reads air quality data (gas levels) from the **MQ-135 sensor**
- Converts the raw data into **PPM (parts per million)** values
- Compares the PPM against some threshold levels I defined
- Tells you whether the air is clean, moderately polluted, or just plain bad
- Sends the info to:
  - An **OLED screen** (so you can see it live)
  - Your **phone via Bluetooth** (for remote monitoring)
- If the air is really bad (high PPM), it:
  - **Turns on a red LED**
  - **Activates a buzzer** to warn you

---

##  What I Used

- **STM32** (F303RE NUCLEO Board)
- **MQ-135** gas sensor
- **OLED display (I2C)**
- **HC-05 Bluetooth module**
- **Buzzer**
- **Red LED**
- A few wires, resistors, and jumper cables

---

## 📊 How It Works (In Simple Terms)

1. MQ-135 gives analog values based on the gases in the air (CO₂, NH₃, smoke, etc.)
2. STM32 reads this value via ADC and converts it into an approximate **PPM value**
3. Depending on the PPM, I categorize the air like this:

| PPM Range     | Status         |
|---------------|----------------|
| 0-450         | Air is clean  |
| 450–470       | A little polluted  |
| 470–500       | Not good      |
| 500+          | Very polluted! Buzzer ON  |

4. This info is shown on the OLED screen and also sent via Bluetooth to a phone (you can use a basic terminal app to read it).
5. If it crosses a dangerous level, buzzer and red LED kick in — kind of like a panic alert.

---

##  How to See It on Your Phone

1. Pair your phone with the **HC-05** Bluetooth module
2. Use any Bluetooth terminal app (like “Serial Bluetooth Terminal” on Android)
3. You'll see live updates like:
PPM: 265 - Air Quality: Good
PPM: 789 - Air Quality: Poor - Warning!


---

##  Future Plans (Maybe)

- Add temperature and humidity data
- Use an app instead of terminal for prettier UI
- Log data to SD card or send it to the cloud (why not?)
- Add a fan that turns on when air is bad

---

##  Final Thoughts

This was a fun and useful project. You get to play with sensors, do some analog-to-digital conversion, and send data around all while making something that can actually help in real life. 😊


