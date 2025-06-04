# UnoD1R32-ApplicationShield

## 🚀 Overview
![Main Preview](assets/img/main.png)

**UNO-D1-R32-ApplicationShield** is an open-source firmware project based on **ESP-IDF**, designed to run on the **UNO D1 R32 Board Module** (ESP32) with the **ARMmbed Application Shield**. This project demonstrates the ESP32’s capabilities with practical examples using GPIO, ADC, PWM, I2C, SPI, and UART for embedded applications.

## 🎯 Purpose
- 🔌 **GPIO Control**: Read/write digital pins and generate PWM signals using LEDC.
- ⏱️ **Timer Management**: Use hardware/software timers to detect button presses.
- ⚡ **Interrupt Handling**: React to button or GPIO events using interrupts.
- 💬 **UART Communication**: Exchange data with a PC via UART for debugging or control.
- 🌡️ **Sensor Interaction**: Use I2C/SPI to read sensors and control external devices.
- 🔄 **ADC Utilization**: Read analog input values such as potentiometer voltage.

## 📝 Features

| Feature                | Description                                               |
|------------------------|-----------------------------------------------------------|
| 💡 GPIO + PWM          | Use `gpio` and `ledc` drivers for digital and PWM control.|
| ⏲️ Timer Support       | Use `esp_timer` or hardware timers for time-based events. |
| ⚠️ GPIO Interrupts     | Use `gpio_install_isr_service` for handling input events. |
| 💻 UART Communication  | Full duplex serial with `uart_driver_install()`.          |
| 🌡️ I2C Sensors         | Read LM75 temp sensor, MMA7660 accelerometer via I2C.     |
| 📺 SPI LCD             | Display sensor or system data using SPI LCD.              |
| 🎚️ ADC Readings       | Use `adc1_get_raw()` with calibration for accurate values. |

## 🔌 Application Shield Schematics
<img src="assets/img/app_shield_sch.png" alt="ApplicationShield Schematic" height="auto" width="50%">

## 🧭 UNO D1 R32 Pinout
<img src="assets/img/uno_d1_r32_sch.png" alt="UNO D1 R32 Pinout" height="auto" width="50%">

## 🎛️ Example Applications

### 1. **PWM via LED**
Utilize **PWM (Pulse Width Modulation)** to control the brightness of an LED. By adjusting the duty cycle, the LED can be dimmed or brightened, allowing for various visual effects. This is particularly useful for applications such as light dimming or motor speed control.

### 2. **GPIO Input via Joystick**
Use the **GPIO** to read the logical levels from the joystick. The program update outputs such as LEDs based on the current status of the joystick buttons.

### 3. **ADC Potentiometer Reading**  
Use the **ADC (Analog-to-Digital Converter)** to read values from a potentiometer. These values can then be used to control parameters such as the brightness of an LED through **PWM (Pulse-Width Modulation)**, allowing the LED intensity to vary according to the potentiometer’s position.

### 4. **PWM via Speaker**
Utilize **PWM (Pulse Width Modulation)** to generate sounds via a speaker. By varying the **frequency**, not the duty cycle, different tones can be produced. The duty cycle remains constant while frequency changes create distinct audible notes. This method is commonly used for sound generation and simple audio signals."

### 5. **Serial Communication**
Establish **serial communication** between the UnoD1R32 and a PC for data exchange. This can be used for debugging, sending sensor readings, or receiving commands from the computer.

### 6. **I2C Temperature Reading**
Use the **I2C protocol** to communicate with temperature sensors such as the LM75. This data can then be used for environmental monitoring or to trigger actions based on temperature thresholds.

### 7. **SPI LCD Control**
Use the **SPI protocol** to control an LCD display. This application could display system status, sensor readings, or any other relevant information on a small screen.

## 📁 Code Structure
```bash
uno-d1-r32-appshield/
├── main/
│ ├── main.c # Main firmware entry point
│ ├── gpio_ctrl.c # GPIO and PWM control logic
│ ├── adc_ctrl.c # Analog input handling
│ ├── timer_ctrl.c # Software/hardware timer handling
│ ├── uart_comm.c # UART interface
│ ├── i2c_ctrl.c # I2C communication
│ ├── spi_display.c # LCD SPI control
│ └── include/ # Header files
├── components/ # Optional external libs
├── assets/ # Images, config files, schematics
├── CMakeLists.txt
└── README.md
```

## 🌟 License
This project is open-source. You are free to use, modify, and contribute.
