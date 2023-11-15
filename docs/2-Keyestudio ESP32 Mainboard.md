# Keyestudio ESP32 Core board

![](./media/d59fe9d9aced2ab49f5b9c6e59d9afde-1699410391850-1.jpeg)

## Introduction

Keyestudio ESP32 Core board is a Mini development board based on the ESP-WROOM-32 module. The board has brought out most I/O ports to pin headers of 2.54mm pitch. These provide an easy way of connecting peripherals according to your own needs.

When it comes to developing and debugging with the development board, the both side standard pin headers can make your operation more simple and handy.

The ESP-WROOM-32 module is the industry's leading integrated WiFi + Bluetooth solution with less than 10 external components. It integrates antenna switches, RF balun, power amplifiers, low noise amplifiers, filters as well as power management modules. At the same time, it also integrates TSMC's low-power 40nm technology, power performance and RFperformance, making it safe, reliable and easy to expand to a variety of applications.  

## Specifications

- Microcontroller: ESP-WROOM-32 Module

- USB to serial port chip: CP2102-GMR

- Working voltage: DC 5V

- Working current：80mA（Average）

- Current supply：500mA（Minimum）

- Working temperature range : -40°C \~ +85°C

- WiFi mode：Station/SoftAP/SoftAP+Station/P2P

- WiFi protocol：802.11b/g/n/e/i（802.11n，speed up to 150 Mbps

- WiFi frequency range：2.4 GHz \~ 2.5 GHz

- Bluetooth protocol：conform to Bluetooth v4.2 BR/EDR and BLE Standard
- Dimensions：55\*26\*13mm

- Weight：9.3g

## Pin out

![](./media/faad4453ca14a342def16fdc3d46ef79-1699415854186-567.png)

ESP32 has fewer pins than commonly used processors, but it doesn't have any problems reusing multiple functions on pins.  

**Warning**: The pin voltage level of the ESP32 is 3.3V.  If you want to connect the ESP32 to another device with an operating voltage of 5V, you should use a level converter to convert the voltage level.  

**●Power Pins:** The module has two power pins +5V and 3.3V.  You can use these two pins to power other devices and modules. 

![](./media/2a90758b3a2e998d7af545fdbb432f08-1699415856634-569.png)

**● GND Pins**: The module has three grounded pins.

**● Enable pin (EN) :** This pin is used to enable and disable modules. The pin enables module at high level and disables module at low level.  

**● Input/Output pins (GPIO) :** You can use 32 GPIO pins to communicate with LEDs, switches and other input/output devices. You can also pull these pins up or down internally.  

**Note:** Though GPIO6 to GPIO11 pins (SCK/CLK, SDO/SD0, SDI/SD1, SHD/SD2, SWP/SD3 and SCS/CMD pins) are used for SPI communication for the internal module, which are not recommended.  

● **ADC:** You can use the 16 ADC pins on this module to convert analog voltages (the output of some sensors) into digital voltages. Some of these converters are connected to internal amplifiers and which are capable of measuring small voltages with high accuracy.

**● DAC:** ESP32 module has two A/D converters with 8-bit precision.

**● Touch pad:** There are 10 pins on the ESP32 module that are sensitive to capacitance changes.  You can attach these pins to certain PCB’s pads and use them as touch switches. 

**● SPI:** There are two SPI interfaces on the module, which can be used to connect the display screen, SD/microSD memory card module as well as external flash memory, etc.

**● I2C:** SDA and SCL pins are used for I2C communication.  

**● Serial Communication (UART) :** There are two UART serial interfaces on this module, which can be used to transfer up to 5Mbps of information between two devices .  The UART0 also has CTS and RTS control functions. 

**●PWM:** Almost all ESP32 input/output pins can be used for PWM(pulse-width modulation). Using these pins can control the motors, LED lights and color changes for some other sensors（for example: color sensor）, etc.



## Components

![](./media/4e99a4f953b9ede17b5c135232ddb476-1699415860901-571.png)



