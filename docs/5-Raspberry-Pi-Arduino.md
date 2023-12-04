

# C language (Raspberry Pi) Tutorial

 Development Environment Configuration

RaspberryPi——Arduino Development Environment Configuration：[RaspberryPi——Arduino ](5-1Raspberry-Pi.md)

## Project 01: Hello World

1. Introduction：

For ESP32 beginners, we'll start with some simple things. In this project, you just need an ESP32 mainboard, USB cable and Raspberry Pi to complete“Hello World\!”Project. It is not only a communication test for ESP32 mainboard and Raspberry Pi, but also a primary project for ESP32.

2. Components

| ![img](./media/wps1-16980213780351-1699415557952-1.png) | ![img](./media/wps2-16980213803472-1699415557952-2.jpg) |
| ------------------------------------------------------- | ------------------------------------------------------- |
| ESP32*1                                                 | USB Cable*1                                             |

3. Wiring Diagram

In this project, we will use a USB cable to connect the ESP32 to Raspberry Pi.

![{67F9F052-9212-4964-831D-56391B65396E}](./media/%7B67F9F052-9212-4964-831D-56391B65396E%7D.png)

4. Test Code


```c
//*************************************************************************************
/*

 * Filename    : Hello World
 * Description : Enter the letter R,and the serial port displays"Hello World".
 * Auther      :http//www.keyestudio.com
   */
   char val;// defines variable "val"
   void setup()
   {
   Serial.begin(115200);// sets baudrate to 115200
   }
   void loop()
   {
     if (Serial.available() > 0) {
    val=Serial.read();// reads symbols assigns to "val"
    if(val=='R')// checks input for the letter "R"
    {  // if so,    
     Serial.println("Hello World!");// shows “Hello World !”.
    }
     }
   }
   //*************************************************************************************
```


Before uploading the project code to ESP32，click “Tools”→“Board” and select“ESP32 Wrover Module”.

![](./media/429f419dbd65a43087851e7d000376bf-1699415557952-4.png)

Select the serial port.

![](./media/23a698888c3b02c80ae5c683deae6fe7-1699415557952-5.png)

Click![](./media/b0d41283bf5ae66d2d5ab45db15331ba-1699415557952-6.png)to download the code to ESP32.

![](./media/4a4be2151f5fc1e5b6cb2c2469f95da1-1699415557952-7.png)

**Note:** If uploading the code fails, you can press the Boot button on ESP32 after click![](./media/d09c4a31563f04a42d451e7bc1a5fb8a-1699415557953-8.png), and release the Boot button![](./media/dc77bfcf5851c8f43aab6cbe7cec7920-1699415557953-9.png) after the percentage of uploading progress appears, as shown below:

![](./media/157ee2e7687559d9812d24edec758150-1699415557953-10.png)

The Project code is uploaded successfully！

![](./media/45f79a7c39d425fca25c888d334a2031-1699415557953-11.png)

5. Project result：

After the project code is uploaded successfully, power up with a USB cable and click the icon![](./media/2f6bca56f724e45a855335cb53ae9b4e-1699415557953-12.png)to enter the serial monitor.

Set baud rate to 115200 and type "R" in the text box. Click "Send", and the serial monitor will display "Hello World\!”.

(**Note:** If you enter“R” in the text box and click“Send”, the serial monitor does not print“Hello World\!”, you need to press the RESET
button on the ESP32 main board and repeat the above operation.)

![](./media/9c034e622137bc43457ec0346286bde5-1699415557953-13.png)

## Project 02: Turn On LED

1.Introduction：

In this project, we will show you how to light up the LED. We use the ESP32's digital pin to turn on the LED so that the LED is lit up.

2.Components：

| ![img](./media/wps3-1699415557953-14.png) | ![img](./media/wps4-1699415557953-15.jpg) |
| ----------------------------------------- | ----------------------------------------- |
| ESP32*1                                   | Breadboard*1                              |
| ![img](./media/wps5-1699415557953-16.jpg) | ![img](./media/wps6-1699415557953-17.jpg) |
| Red LED*1                                 | 220Ω Resistor*1                           |
| ![img](./media/wps7-1699415557953-18.jpg) | ![img](./media/wps8-1699415557953-19.jpg) |
| Jumper Wire*2                             | USB Cable*1                               |

3.Component knowledge：

**（1）LED:**

![img](./media/wps5-1699415557953-16.jpg)

The LED is a semiconductor known as “light-emitting diode” ,which is an electronic device made from semiconducting materials(silicon, selenium, germanium, etc.). It has an anode and a cathode, the short lead is cathode, which connects to GND; the long lead is anode, which connects to 3.3V or 5V.

![](./media/f70404aa49540fd7aecae944c7c01f83-1699415557953-20.jpeg)

**（2）Five-color ring resistor**

A resistor is an electronic component in a circuit that restricts or regulates the flow current flow. On the left is the appearance of the resistor and on the right is the symbol for the resistance in the circuit . Its unit is(Ω). 1 mΩ= 1000 kΩ，1kΩ= 1000Ω.

![image-20231108140221117](./media/image-20231108140221117.png)

We can use resistors to protect sensitive components, such as LED. The strength of the resistance is marked on the body of the resistor with an electronic color code. Each color code represents a number, and you can refer to it in a resistance card.

\-Color 1 – 1st Digit.

\-Color 2 – 2nd Digit.

\-Color 3 – 3rd Digit.

\-Color 4 – Multiplier.

\-Color 5 – Tolerance.

![](./media/c3df005312cd9f6d4cdae6abf3cddb83-1699415557953-21.png)

In this kit, we provide three Five-color ring resistor with different resistance values. Take three Five-color ring resistor as an example.

220Ω Resistor\*10

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

10KΩ Resistor\*10

![](./media/246cf3885dc837c458a28123885c9f7b-1699415557953-23.png)

1KΩ Resistor\*10

![](./media/19f5dfc51adfd79b04c3b164529767ed-1699415557953-24.png)

In the same voltage, there will be less current and more resistance. The connection between current(I), voltage(V), and resistance(R) can be expressed by the formula: I=U/R. In the figure below, if the voltage is 3V, the current through R1 is: I = U / R = 3 V / 10 KΩ= 0.0003A= 0.3mA.

![](./media/b3eec552e4dfad361833730698621776-1699415557953-25.png)

Don’t connect a low resistance directly to the two poles of the power supply. as this will cause excessive current to damage the electronic components. Resistors do not have positive and negative poles.

**（3）Bread board**

Breadboards are used to build and test circuits quickly before completing any circuit design. There are many holes in the breadboard that can be inserted into circuit components such as integrated circuits and resistors. A typical breadboard is shown below：

![](./media/612c1381811b2d780d5f6ed6a7ec3701-1699415557953-26.png)

The breadboard has strips of metal , which run underneath the board and connect the holes on the top of the board. The metal strips are laid out as shown below. Note that the top and bottom rows of holes are connected horizontally，while the remaining holes are connected vertically.

![](./media/b45e70b961537035c85878b73d371725-1699415557953-27.png)

The first two rows (top) and the last two rows (bottom) of the breadboard are used for the positive pole (+) and negative pole (-) of the power supply respectively. The conductive layout of the breadboard is shown in the figure below:

![](./media/d5478bd5eac558252cbc235479d979eb-1699415557953-29.png)

When we connect DIP (Dual In-line Packages) components, such as integrated circuits, microcontrollers, chips and so on, we can see that a groove in the middle isolates the middle part, so the top and bottom of the groove is not connected. DIP components can be connected as shown in the following diagram:

![](./media/50caf14e911c4244779e99445c658db6-1699415557953-28.png)

![](./media/9b66ae2199e77fbc99b7b278dac0b567-1699415557953-30.png)

**（4）Power Supply**

In this project, we connected the ESP32 to the Raspberry Pi by using USB cable.

![{67F9F052-9212-4964-831D-56391B65396E}](./media/%7B67F9F052-9212-4964-831D-56391B65396E%7D-1699416006359-1146.png)

4.Wiring diagram：

First, disconnect all power from the ESP32. Then build the circuit according to the wiring diagram. After the circuit is built and verified correct, connect the ESP32 to the Raspberry Pi by using a USB cable.

**Note:** Avoid any possible short circuits (especially connecting 3.3V and GND)\!

**WARNING:** A short circuit can cause high current in your circuit, create excessive component heat and cause permanent damage to your hardware\!

![](./media/0735997593c8858ad6441d8e9867206f-1699415557953-31.png)

Note:

How to connect a LED

![](./media/42ff6f405dfa128593827de5aa03e94b-1699415557953-32.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

5.Project code：

```c
//**********************************************************************
/*
 * Filename    : Turn On LED
 * Description : Make an led on.
 * Auther      : http//www.keyestudio.com
*/
#define LED_BUILTIN 15

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
}
//*************************************************************************************
```


Before uploading the project code to ESP32，click “Tools”→“Board” and select“ESP32 Wrover Module”.

![](./media/fe73bbd726dbe38bb24f9c0d735c90ec-1699415557953-33.png)

Select the serial port.

![](./media/b71d7b72d007d65f0df7b9eb2b46745a-1699415557953-34.png)

Click![](./media/b0d41283bf5ae66d2d5ab45db15331ba-1699415557952-6.png)to download the code to ESP32.

![](./media/c667e2a781af94ea0cc8b67b4af99b58-1699415557953-35.png)

**Note:** If uploading the code fails, you can press the Boot button on ESP32 after click![](./media/d09c4a31563f04a42d451e7bc1a5fb8a-1699415557953-8.png), and release the Boot button![](./media/dc77bfcf5851c8f43aab6cbe7cec7920-1699415557953-9.png) after the percentage of uploading progress appears, as shown below:

![](./media/157ee2e7687559d9812d24edec758150-1699415557953-10.png)

The Project code is uploaded successfully！

![](./media/e6bd4b99e07cab3791c5a84976761abe-1699415557953-36.png)

6.Project result：

After the project code was uploaded successfully, power up with a USB cable and the LED is lit up.

![](./media/77dec960e108229b6d97b4af9a2db902-1699415557953-37.png)

## Project 03：LED Flashing

1.Introduction：

In this project, we will show you the LED flashing effect .We use the ESP32's digital pin to turn on the LED and make it flashing.

2.Components：

| ![img](./media/wps3-1699415557953-14.png) | ![img](./media/wps4-1699415557953-15.jpg) |
| ----------------------------------------- | ----------------------------------------- |
| ESP32*1                                   | Breadboard*1                              |
| ![img](./media/wps5-1699415557953-16.jpg) | ![img](./media/wps6-1699415557953-17.jpg) |
| Red LED*1                                 | 220Ω Resistor*1                           |
| ![img](./media/wps7-1699415557953-18.jpg) | ![img](./media/wps8-1699415557953-19.jpg) |
| Jumper Wire*2                             | USB Cable*1                               |


3.Wiring diagram：

First, disconnect all power from the ESP32. Then build the circuit according to the wiring diagram. After the circuit is built and verified correct, connect the ESP32 to your computer using a USB cable.

**Note:** Avoid any possible short circuits (especially connecting 3.3V and GND)\!

**WARNING:** A short circuit can cause high current in your circuit, create excessive component heat and cause permanent damage to your hardware\!

![](./media/0735997593c8858ad6441d8e9867206f-1699415557953-31.png)

**Note:**

How to connect a LED

![](./media/42ff6f405dfa128593827de5aa03e94b-1699415557953-32.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

4.Test Code

```c
//**********************************************************************
/*
 * Filename    : External LED flashing
 * Description : Make an led blinking.
 * Auther      : http//www.keyestudio.com
*/
#define PIN_LED   15   //define the led pin

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED as an output.
  pinMode(PIN_LED, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(PIN_LED, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(500);                       // wait for 0.5s
  digitalWrite(PIN_LED, LOW);    // turn the LED off by making the voltage LOW
  delay(500);                       // wait for 0.5s
}
//*************************************************************************************
```


Before uploading Project Code to ESP32, please check the configuration of Arduino IDE.

Click "**Tools**" to confirm the board type and port as shown below:

![](./media/ccbd6a42119ea4e07c77ea11c8074981-1699415557953-38.png)

Click![](./media/b0d41283bf5ae66d2d5ab45db15331ba-1699415557952-6.png)to download the project code to ESP32.

![](./media/fb82f9ec41fdb6812ac26be0b693af46-1699415557953-39.png)

**Note:** If uploading the code fails, you can press the Boot button on ESP32 after click![](./media/d09c4a31563f04a42d451e7bc1a5fb8a-1699415557953-8.png), and release the Boot button![](./media/dc77bfcf5851c8f43aab6cbe7cec7920-1699415557953-9.png) after the percentage of uploading progress appears, as shown below:

![](./media/157ee2e7687559d9812d24edec758150-1699415557953-10.png)

The Project code is uploaded successfully！

![](./media/c9387d7e1c8cdab3116fd40b58701c22-1699415557953-40.png)

5.Project result：

After the project code was uploaded successfully, power up with a USB cable and the LED start flashing.

![image-20231023084100991](./media/image-20231023084100991-1699415557953-41.png)

## Project 04: Breathing Led

1.Introduction：

In previous studies, we know that LEDs have on/off state, so how to enter the intermediate state? How to output an intermediate state to make the LED half bright? That's what we're going to learn.

Breathing light, that is, LED is turned from off to on gradually, and gradually from on to off, just like "breathing". So, how to control the brightness of a LED? We will use ESP32’s PWM to achieve this target.

2.Components：

| ![img](./media/wps3-1699415557953-14.png) | ![img](./media/wps4-1699415557953-15.jpg) |
| ----------------------------------------- | ----------------------------------------- |
| ESP32*1                                   | Breadboard*1                              |
| ![img](./media/wps5-1699415557953-16.jpg) | ![img](./media/wps6-1699415557953-17.jpg) |
| Red LED*1                                 | 220Ω Resistor*1                           |
| ![img](./media/wps7-1699415557953-18.jpg) | ![img](./media/wps8-1699415557953-19.jpg) |
| Jumper Wire*2                             | USB Cable*1                               |


2.Component knowledge：

![](./media/6549bdbfd4e7b6b2b341012105d655e8-1699415557953-42.png)

**Analog & Digital**

An Analog Signal is a continuous signal in both time and value. On the contrary, a Digital Signal or discrete time signal is a time series consisting of a sequence of quantities. Most signals in life are analog signals. A familiar example of an Analog Signal would be how the temperature throughout the day is continuously changing and could not suddenly change instantaneously from 0℃ to 10℃. However, Digital Signals can instantaneously change in value. This change is expressed in numbers as 1 and 0 (the basis of binary code). Their differences can more easily be seen when compared when graphed as below.

![](./media/4bdf6127e563b453a1fd8953b4ebb277-1699415557954-43.png)

In practical application, we often use binary as the digital signal, that is a series of 0’s and 1’s. Since a binary signal only has two
values (0 or 1), it has great stability and reliability. Lastly, both analog and digital signals can be converted into the other.

**PWM：**

PWM, Pulse-Width Modulation, is a very effective method for using digital signals to control analog circuits. Common processors cannot directly output analog signals. PWM technology makes it very convenient to achieve this conversion (translation of digital to analog signals).

PWM technology uses digital pins to send certain frequencies of square waves, that is, the output of high levels and low levels, which alternately last for a while. The total time for each set of high levels and low levels is generally fixed, which is called the period (Note: the reciprocal of the period is frequency). The time of high level outputs are generally called “pulse width”, and the duty cycle is the percentage of the ratio of pulse duration, or pulse width (PW) to the total period(T) of the waveform.

The longer the output of high levels last, the longer the duty cycle and the higher the corresponding voltage in the analog signal will be. The following figures show how the analog signal voltages vary between 0V-3V3 (high level is 3V3) corresponding to the pulse width 0%-100%:

![](./media/a439e1bd8a4578b43b7188c821d58594-1699415557954-46.jpeg)

The longer the PWM duty cycle is, the higher the output power will be. Now that we understand this relationship, we can use PWM to control the brightness of an LED or the speed of DC motor and so on. It is evident from the above that PWM is not real analog, and the effective value of the voltage is equivalent to the corresponding analog. so, we can control the output power of the LED and other output modules to achieve different effects.

**ESP32 and PWM:**

On ESP32, the LEDC(PWM) controller has 16 separate channels, each of which can independently control frequency, duty cycle, and even accuracy. Unlike traditional PWM pins, the PWM output pins of ESP32 are configurable, with one or more PWM output pins per channel. The relationship between the maximum

frequency and bit precision is shown in the following formula, where the maximum value of bit is 31.

![](./media/f79af745d3c726ee5ca07932d2ca6d5e-1699415557954-44.png)

For example, generate a PWM with an 8-bit precision (2<sup>8</sup>=256. Values range from 0 to 255) with a maximum frequency of 80,000,000/255 =312,500Hz.）

3.Wiring diagram：

![](./media/0735997593c8858ad6441d8e9867206f-1699415557953-31.png)

**Note:**

How to connect a LED

![](./media/42ff6f405dfa128593827de5aa03e94b-1699415557953-32.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

4.Project code：

The design of this project makes the GP15 output PWM, and the pulse width gradually increases from 0% to 100%, and then gradually decreases from 100% to 0%.

```c
//**********************************************************************
/*
 * Filename    : Breathing Led
 * Description : Make led light fade in and out, just like breathing.
 * Auther      : http//www.keyestudio.com
*/
#define PIN_LED   15   //define the led pin
#define CHN       0   //define the pwm channel
#define FRQ       1000  //define the pwm frequency
#define PWM_BIT   8     //define the pwm precision
void setup() {
  ledcSetup(CHN, FRQ, PWM_BIT); //setup pwm channel
  ledcAttachPin(PIN_LED, CHN);  //attach the led pin to pwm channel
}

void loop() {
  for (int i = 0; i < 255; i++) { //make light fade in
    ledcWrite(CHN, i);
    delay(10);
  }
  for (int i = 255; i > -1; i--) {  //make light fade out
    ledcWrite(CHN, i);
    delay(10);
  }
}
//*************************************************************************************
```


Before uploading Project Code to ESP32, please check the configuration of Arduino IDE.

Click "**Tools**" to confirm the board type and port as shown below:

![](./media/e2b2b9fc156d3dc159cf56bdaac4414a-1699415557954-45.png)

Click![](./media/b0d41283bf5ae66d2d5ab45db15331ba-1699415557952-6.png)to download the project code to ESP32.

![](./media/793dc36a8bf226c8551d56b61ba9b96e-1699415557954-47.png)

**Note:** If uploading the code fails, you can press the Boot button on ESP32 after click![](./media/d09c4a31563f04a42d451e7bc1a5fb8a-1699415557953-8.png), and release the Boot button![](./media/dc77bfcf5851c8f43aab6cbe7cec7920-1699415557953-9.png) after the percentage of uploading progress appears, as shown below:

![](./media/157ee2e7687559d9812d24edec758150-1699415557953-10.png)

The Project code is uploaded successfully！

![](./media/493d055e2090658577b908373858cb6c-1699415557954-48.png)

5.Project result：

After the project code was uploaded successfully, power up with a USB cable and the LED is turned from ON to OFF and then back from OFF to ON gradually like breathing.

![image-20231023084419298](./media/image-20231023084419298-1699415557954-50.png)

## Project 05：Traffic Lights

1.Introduction：

Traffic lights are closely related to people's daily lives, which generally show red, yellow, and green. Everyone should obey the traffic rules, which can avoid many traffic accidents. In this project, we will use ESP32 and some LEDs (red, green and yellow) to simulate the traffic lights.

2.Components：

| ![img](./media/wps1-16980219202347-1699415557954-49.png)  | ![img](./media/wps2-16980219218598-1699415557954-51.jpg)  |                                                           |
| --------------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| ESP32*1                                                   | Bread board*1                                             |                                                           |
| ![img](./media/wps3-1699415557954-52.jpg)                 | ![img](./media/wps4-16980219479959-1699415557954-54.jpg)  | ![img](./media/wps5-169802195049910-1699415557954-53.jpg) |
| Red LED*1                                                 | Yellow LED*1                                              | Green LED*1                                               |
| ![img](./media/wps6-169802195246711-1699415557954-55.jpg) | ![img](./media/wps7-169802195500412-1699415557954-56.jpg) | ![img](./media/wps8-169802195675513-1699415557954-57.jpg) |
| USB Cable*1                                               | 220Ω Resistor*3                                           | Jumper Wires                                              |


3.Wiring diagram：

![](./media/a991f5cc6f8759eca3b9d01f95fe4854-1699415557954-59.png)

**Note:**

How to connect a LED

![](./media/42ff6f405dfa128593827de5aa03e94b-1699415557953-32.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

4.Test Code

```c
//**********************************************************************
/*
 * Filename    : Traffic Lights
 * Description : Simulated traffic lights.
 * Auther      : http//www.keyestudio.com
*/
#define PIN_LED_RED   0   //define the red led pin
#define PIN_LED_YELLOW   2   //define the yellow led pin
#define PIN_LED_GREEN  15   //define the green led pin

void setup() {
  pinMode(PIN_LED_RED, OUTPUT);
  pinMode(PIN_LED_YELLOW, OUTPUT);
  pinMode(PIN_LED_GREEN, OUTPUT);
}

void loop() {
   digitalWrite(PIN_LED_GREEN, HIGH);// turns on the green led
   delay(5000);// delays 5 seconds
   digitalWrite(PIN_LED_GREEN, LOW); // turns off the green led
   for(int i=0;i<3;i++)// flashes 3 times.
{
   delay(500);// delays 0.5 second
   digitalWrite(PIN_LED_YELLOW, HIGH);// turns on the yellow led
   delay(500);// delays 0.5 second
   digitalWrite(PIN_LED_YELLOW, LOW);// turns off the yellow led
} 
   delay(500);// delays 0.5 second
   digitalWrite(PIN_LED_RED, HIGH);// turns on the red led
   delay(5000);// delays 5 second
   digitalWrite(PIN_LED_RED, LOW);// turns off the red led
}
//*************************************************************************************
```



Before uploading Project Code to ESP32, please check the configuration of Arduino IDE.

Click "**Tools**" to confirm the board type and port as shown below:

![](./media/7a86a1f3376ea509d5e65042f26348d2-1699415557954-58.png)

Click![](./media/b0d41283bf5ae66d2d5ab45db15331ba-1699415557952-6.png)to download the project code to ESP32.

![](./media/dcc79b198e2a66b97caf4bd1debb2836-1699415557954-60.png)

**Note:** If uploading the code fails, you can press the Boot button on ESP32 after click![](./media/d09c4a31563f04a42d451e7bc1a5fb8a-1699415557953-8.png), and release the Boot button![](./media/dc77bfcf5851c8f43aab6cbe7cec7920-1699415557953-9.png) after the percentage of uploading progress appears, as shown below:

![](./media/157ee2e7687559d9812d24edec758150-1699415557953-10.png)

The Project code is uploaded successfully！

![](./media/ec349a608a859c34de7a9249ac067eb6-1699415557954-61.png)

5.Project result：

After the project code was uploaded successfully, power up with a USB cable and you'll see are below:

① First, the green light will be on for five seconds and then off; 

② Next, the yellow light blinks three times and then goes off;

③ Then, the red light goes on for five seconds and then goes off;

④ Repeat steps 1 to 3 above.

## Project 06: RGB LED

1.Introduction：

![](./media/94bdff69e438989d8e0934e57f2e5c00-1699415557954-62.png)

RGB is composed of three colors (red, green and blue),which can emit different colors of light by mixing these three basic colors.

In this project, we will introduce the RGB and show you how to use ESP32 to control the RGB to emit different color light .RGB is pretty basic, but it’s also a great way to learn the fundamentals of electronics and coding.

2.Components：

| ![img](./media/wps9-1699415557954-63.png)  | ![img](./media/wps10-1699415557954-64.jpg) |
| ------------------------------------------ | ------------------------------------------ |
| ESP32*1                                    | Breadboard*1                               |
| ![img](./media/wps11-1699415557954-65.jpg) | ![img](./media/wps12-1699415557954-66.jpg) |
| RGB*1                                      | 220Ω Resistor*1                            |
| ![img](./media/wps13-1699415557954-67.jpg) | ![img](./media/wps14-1699415557954-68.jpg) |
| jump wires                                 | USB cable *1                               |


3.Component knowledge：

Most monitors adopt the RGB color standard, and all colors on a computer screen are a mixture of red, green and blue in varying proportions.

![](./media/image-20231108140902265.png)

This RGB LED has 4 pins, each color (red, green, blue) and a common cathode,To change its brightness, we can use the PWM of the ESP32 pins, which can give different duty cycle signals to the RGB to produce different colors of light.

If we use three 10-bit PWM to control the RGB, in theory, we can create 2 <sup>10</sup>\*2<sup>10</sup>\*2<sup>10</sup>=1,073,741,824(1 billion) colors through different combinations.

4.Wiring diagram：

![](./media/f3deb3502985ac8d66e99e4f27b3de1e-1699415557954-70.png)

Notice: The longest pin (common cathode) of the RGB LED is connected to GND.

![](./media/1584356c63bf99934ae0810ee02dced3-1699415557954-71.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

5.Project code：

```c
//**********************************************************************
/*
 * Filename    : RGB LED
 * Description : Use RGBLED to show random color.
 * Auther      : http//www.keyestudio.com
*/
int ledPins[] = {0, 2, 15};    //define red, green, blue led pins
const byte chns[] = {0, 1, 2};        //define the pwm channels
int red, green, blue;
void setup() {
  for (int i = 0; i < 3; i++) {   //setup the pwm channels,1KHz,8bit
    ledcSetup(chns[i], 1000, 8);
    ledcAttachPin(ledPins[i], chns[i]);
  }
}

void loop() {
  red = random(0, 256);
  green = random(0, 256);
  blue = random(0, 256);
  setColor(red, green, blue);
  delay(200);
}

void setColor(byte r, byte g, byte b) {
  ledcWrite(chns[0], 255 - r); //Common anode LED, low level to turn on the led.
  ledcWrite(chns[1], 255 - g);
  ledcWrite(chns[2], 255 - b);
}
//*************************************************************************************
```


6.Project result：

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the RGB LED starts to display random colors.

## Project 07: Flowing Water Light

1.Introduction：

In our daily life, we can see many billboards composed of different colors of LED. They constantly change the light (like water) to attract customers' attention. In this project, we will use ESP32 to control 10 leds to achieve the effect of flowing water.

2.Components：

| ![img](./media/wps1-169802219752214-1699415557954-72.png) | ![img](./media/wps2-169802219916215-1699415557954-73.jpg) |
| --------------------------------------------------------- | --------------------------------------------------------- |
| ESP32*1                                                   | Breadboard*1                                              |
| ![img](./media/wps3-169802221245516-1699415557954-74.jpg) | ![img](./media/wps4-169802221414417-1699415557954-75.jpg) |
| Red LED*1                                                 | 220Ω Resistor*1                                           |
| ![img](./media/wps5-169802222876318-1699415557954-76.jpg) | ![img](./media/wps6-169802223041819-1699415557954-77.jpg) |
| Jumper Wires                                              | USB Cable*1                                               |

3.Wiring diagram:

![](./media/548f889607bdb0ce017c58f323c85dfa-1699415557954-78.png)

**Note:**

How to connect a LED

![](./media/42ff6f405dfa128593827de5aa03e94b-1699415557953-32.png)

How to identify the 220Ω Five-color ring resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

4. Test Code：

This project is designed to make a flowing water lamp. Which are these actions: First turn LED \#1 ON, then turn it OFF. Then turn LED \#2 ON, and then turn it OFF... and repeat the same to all 10 LEDs until the last LED is turns OFF. This process is repeated to achieve the “movements” of flowing water.

```c
//**********************************************************************
/* 
 * Filename    : Flowing Water Light
 * Description : Using ten leds to demonstrate flowing lamp.
 * Auther      : http//www.keyestudio.com
*/
byte ledPins[] = {22, 21, 19, 18, 17, 16, 4, 0, 2, 15};
int ledCounts;

void setup() {
  ledCounts = sizeof(ledPins);
  for (int i = 0; i < ledCounts; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < ledCounts; i++) {
    digitalWrite(ledPins[i], HIGH);
    delay(100);
    digitalWrite(ledPins[i], LOW);
  }
  for (int i = ledCounts - 1; i > -1; i--) {
    digitalWrite(ledPins[i], HIGH);
    delay(100);
    digitalWrite(ledPins[i], LOW);
  }
}
//**********************************************************************
```


4.Project result：

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that 10 LEDs will light up from left to right and then back from right to left.

![](./media/image-20231108140955924.png)

## Project 08：1-Digit Digital Tube

1.Introduction

The 1-Digit 7-Segment display is an device that displays decimal numbers, which is widely used in digital clocks, electronic meters,
basic calculators and other electronic devices that display digital information. In this project, we will use ESP32 to control 1-Digit
7-segment display to display numbers.

2.Components

| ![img](./media/wps1-169802229753220-1699415557954-80.png) | ![img](./media/wps2-169802229907821-1699415557954-81.jpg) |
| --------------------------------------------------------- | --------------------------------------------------------- |
| ESP32*1                                                   | Breadboard*1                                              |
| ![img](./media/wps3-169802231048422-1699415557954-82.jpg) | ![img](./media/wps4-169802231196423-1699415557954-83.jpg) |
| 1-Digit 7-Segment Display*1                               | 220Ω Resistor*8                                           |
| ![img](./media/wps5-169802231885124-1699415557954-84.jpg) | ![img](./media/wps6-169802232034825-1699415557954-85.jpg) |
| Jumper Wires                                              | USB Cable*1                                               |


3.Component Knowledge

![](./media/e44a0f27beec739ee13e68c04865989f-1699415557955-86.png)

**1-Digit 7-Segment Display:** It is a semiconductor light emitting device, and its basic unit is a light-emitting diode (LED). The digital
tube display can be divided into 7-segment display and 8-segment display according to the number of segments.

The 8-segment display has one more LED unit than the 7-segment display(used for decimal point display). Each segment of the 7-segment display is a separate LED. According to the connection mode of the LED unit, the digital tube can be divided into a common anode digital tube and a common cathode digital tube.

In the common cathode 7-segment display, all the cathodes (or negative pole) of the segmented LEDs are connected together, so you should connect the common cathode to GND. If you are about to light up a segmented LED, you can set its associated pin to“HIGH”.

In the common anode 7-segment display, the LED anodes (positive pole) of all segments are connected together, so you should connect the common anode to“+5V”. If you are about to light up a segmented LED, you can set its associated pin to“LOW”.

![](./media/28fd057848fbe0e8c8e3362768e7aa44-1699415557955-87.png)

Each part of the digital tube is composed of an LED. So when you use it, you also need to use a current limiting resistor. Otherwise, the LED will be damaged. In this experiment, we will use an ordinary common cathode one-digit digital tube. As we mentioned above, you should connect the common cathode to GND. If you are about to light up a segmented LED, you can set its associated pin to“HIGH”.

4.Wiring Diagram

Note: The direction of the 7-segment display inserted into the breadboard is consistent with the wiring diagram, with one more point in the lower right corner.

![](./media/631ee0861da60ed02d191de0e0e210d9-1699415557955-88.png)

![](./media/5f01d1eea2bb207f19dee4f437f93bc8-1699415557955-89.png)

5.Test Code

The digital display is divided into 7 segments, and the decimal point display is divided into 1 segment. When certain numbers are displayed, the corresponding segment will be lit. For example, when the number 1 is displayed, segments b and c will be turned on.


```c
//**********************************************************************
/* 
 * Filename    : 1-Digit Digital Tube
 * Description : One Digit Tube displays numbers from 9 to 0.
 * Auther      : http//www.keyestudio.com
*/
// sets the IO PIN for every segment
int a=16; // digital PIN 16 for segment a
int b=4; // digital PIN 4 for segment b
int c=5; // digital PIN 5 for segment c
int d=18; // digital PIN 18 for segment d
int e=19; // digital PIN 19 for segment e
int f=22; // digital PIN 22 for segment f
int g=23; // digital PIN 23 for segment g
int dp=17; // digital PIN 17 for segment dp
void digital_0(void) // displays number 0
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_1(void) // displays number 1
{
digitalWrite(a,LOW);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,LOW);
digitalWrite(e,LOW);
digitalWrite(f,LOW);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_2(void) // displays number 2
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,LOW);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,LOW);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_3(void) // displays number 3
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(f,LOW);
digitalWrite(e,LOW);
digitalWrite(dp,LOW);
digitalWrite(g,HIGH);
}
void digital_4(void) // displays number 4
{
digitalWrite(a,LOW);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,LOW);
digitalWrite(e,LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_5(void) // displays number 5
{
digitalWrite(a,HIGH);
digitalWrite(b,LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_6(void) // displays number 6
{
digitalWrite(a,HIGH);
digitalWrite(b,LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_7(void) // displays number 7
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,LOW);
digitalWrite(e,LOW);
digitalWrite(f,LOW);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_8(void) // displays number 8
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) // displays number 9
{
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void setup()
{
  // initialize digital pin LED as an output.
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(dp, OUTPUT);
}
void loop()
{
while(1)
{
digital_9();// displays number 9
delay(1000); // waits a sencond
digital_8();// displays number 8
delay(1000); // waits a sencond
digital_7();// displays number 7
delay(1000); // waits a sencond
digital_6();// displays number 6
delay(1000); // waits a sencond
digital_5();// displays number 5
delay(1000); // waits a sencond
digital_4();// displays number 4
delay(1000); // waits a sencond
digital_3();// displays number 3
delay(1000); // waits a sencond
digital_2();// displays number 2
delay(1000); // waits a sencond
digital_1();// displays number 1
delay(1000);// waits a sencond
digital_0();// displays number 0
delay(1000);// waits a sencond
}}
//**********************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the 1-Digit 7-Segment display will display numbers from 9 to 0.
## Project 09：4-Digit Digital Tube

1.Introduction

The 4-digit 7-segment display is a very practical display device and it is used for devices such as electronic clocks, score counters and the number of people in the park. Because of the low price, easy to use, more and more projects will use the 4 Digit 7-segment display. In this project, we use ESP32 to control the 4-digit 7-segment display to display digits.

2.Components

| ![img](./media/wps7-1699415557955-90.png)                  | ![img](./media/wps8-169802237314026-1699415557955-91.jpg)  |
| ---------------------------------------------------------- | ---------------------------------------------------------- |
| ESP32*1                                                    | Breadboard*1                                               |
| ![img](./media/wps9-1699415557955-92.jpg)                  | ![img](./media/wps10-169802238564427-1699415557955-93.jpg) |
| 4-digit 7-segment display Module*1                         | 220Ω Resistor*8                                            |
| ![img](./media/wps11-169802239225228-1699415557955-94.jpg) | ![img](./media/wps12-169802239472429-1699415557955-95.jpg) |
| Jumper Wires                                               | USB Cable*1                                                |


3.Component Knowledge

![](./media/ce987bf9a2ab398945c98b34d3f8a003-1699415557955-96.png)

**4-digit 7-segment display：**It is a device with common cathode and anode, its display principle is similar to the 1-Digit digital tube display. Both of them have eight GPIO ports to control the digital tube display, that is 8 leds. However, here is 4-digit, so it needs four GPIO ports to control the bit selection end. Our 4 - digit digital tube is common cathode. 

The following figure shows the pin diagram of the 4-digit digital tube. G1, G2, G3 and G4 are the control pins. 

![](./media/37113fa53213973132086c285d67686b-1699415557955-97.png)

**Schematic Diagram**

![image-20231108141049038](./media/image-20231108141049038.png)

![](./media/ea75d1b7414bf6f8c187fb32fea9bc83-1699415557955-98.png)

4.Wiring Diagram

![](./media/313c429f670cd000b61cd3aeee0fef92-1699415557955-99.png)

5.Test Code

```c
//**********************************************************************
/* 
 * Filename    : 4-Digit Digital Tube
 * Description : Four Digit Tube displays numbers from 0 to 9999.
 * Auther      : http//www.keyestudio.com
*/
#define d_a 18   //Define nixie tube a to pin 18
#define d_b 13
#define d_c 2
#define d_d 16
#define d_e 17
#define d_f 19
#define d_g 0
#define d_dp 4

#define G1 21   //Define the first set of nixtube G1 to pin 21
#define G2 22
#define G3 14
#define G4 15

//Nixie tube 0-F code value
unsigned char num[17][8] =
{
 //a  b  c  d  e  f  g  dp 
  {1, 1, 1, 1, 1, 1, 0, 0},     //0
  {0, 1, 1, 0, 0, 0, 0, 0},     //1
  {1, 1, 0, 1, 1, 0, 1, 0},     //2
  {1, 1, 1, 1, 0, 0, 1, 0},     //3
  {0, 1, 1, 0, 0, 1, 1, 0},     //4
  {1, 0, 1, 1, 0, 1, 1, 0},     //5
  {1, 0, 1, 1, 1, 1, 1, 0},     //6
  {1, 1, 1, 0, 0, 0, 0, 0},     //7
  {1, 1, 1, 1, 1, 1, 1, 0},     //8
  {1, 1, 1, 1, 0, 1, 1, 0},     //9
  {1, 1, 1, 0, 1, 1, 1, 1},     //A
  {1, 1, 1, 1, 1, 1, 1, 1},     //B
  {1, 0, 0, 1, 1, 1, 0, 1},     //C
  {1, 1, 1, 1, 1, 1, 0, 1},     //D
  {1, 0, 0, 1, 1, 1, 1, 1},     //E
  {1, 0, 0, 0, 1, 1, 1, 1},     //F
  {0, 0, 0, 0, 0, 0, 0, 1},     //.
};

void setup()
{
  pinMode(d_a,OUTPUT);    //Set to output pin
  pinMode(d_b,OUTPUT);
  pinMode(d_c,OUTPUT);
  pinMode(d_d,OUTPUT);
  pinMode(d_e,OUTPUT);
  pinMode(d_f,OUTPUT);
  pinMode(d_g,OUTPUT);
  pinMode(d_dp,OUTPUT);
  
  pinMode(G1,OUTPUT);
  pinMode(G2,OUTPUT);
  pinMode(G3,OUTPUT);
  pinMode(G4,OUTPUT);
}

void loop()
{

  //Start counting from 0 and gradually increase by 1 to 9999, repeating.
  for(int l = 0;l < 10;l++ )
  {
    for(int k = 0; k < 10;k++)
    {
      for(int j = 0; j < 10; j++)
      {
        for(int i = 0;i < 10;i++)
        {
          //125 flashes a second equals one second.
          //1000/8=125
          for(int q = 0;q<125;q++)
          {
            Display(1,l);//The first nixie tube shows the value of L.
            delay(2);
            Display(2,k);
            delay(2);
            Display(3,j);
            delay(2);
            Display(4,i);
            delay(2);
          }
          
        }
      }
    }
  }
}
//Display functions: g ranges from 1 to 4,num ranges from 0 to 9
void Display(unsigned char g,unsigned char n) 
{
  digitalWrite(d_a,LOW);      //Remove the light
  digitalWrite(d_b,LOW);
  digitalWrite(d_c,LOW);
  digitalWrite(d_d,LOW);
  digitalWrite(d_e,LOW);
  digitalWrite(d_f,LOW);
  digitalWrite(d_g,LOW);
  digitalWrite(d_dp,LOW);
  
  switch(g)           //Gate a choice
  {
    case 1:
      digitalWrite(G1,LOW);   //Choose the first digit
      digitalWrite(G2,HIGH);
      digitalWrite(G3,HIGH);
      digitalWrite(G4,HIGH);
      break;
    case 2:
      digitalWrite(G1,HIGH);
      digitalWrite(G2,LOW);   //Choose the second bit
      digitalWrite(G3,HIGH);
      digitalWrite(G4,HIGH);
      break;
    case 3:
      digitalWrite(G1,HIGH);
      digitalWrite(G2,HIGH);
      digitalWrite(G3,LOW);   //Choose the third bit
      digitalWrite(G4,HIGH);
      break;
    case 4:
      digitalWrite(G1,HIGH);
      digitalWrite(G2,HIGH);
      digitalWrite(G3,HIGH);
      digitalWrite(G4,LOW);   //Choose the fourth bit
      break;
    default:break;
  }
  
  digitalWrite(d_a,num[n][0]);      //a Queries the code value table
  digitalWrite(d_b,num[n][1]);
  digitalWrite(d_c,num[n][2]);
  digitalWrite(d_d,num[n][3]);
  digitalWrite(d_e,num[n][4]);
  digitalWrite(d_f,num[n][5]);
  digitalWrite(d_g,num[n][6]);
  digitalWrite(d_dp,num[n][7]);
}
//**********************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the 4-digit 7-segment display displays 0-9999，and repeat these actions in an infinite loop.

## Project 10：8×8 Dot-matrix Display

1.Introduction

Dot matrix display is an electronic digital display device that can display information on machine, clocks, public transport departure indicators and many other devices. In this project, we will use ESP32 to control 8x8 LED dot matrix to display digits.

2.Components

| ![img](./media/wps13-1699415557955-100.png) | ![img](./media/wps14-169802243324430-1699415557955-101.jpg) |
| ------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                                |
| ![img](./media/wps15-1699415557955-102.jpg) | ![img](./media/wps16-1699415557955-103.jpg)                 |
| 8*8 dot matrix module *1                    | 220Ω Resistor*8                                             |
| ![img](./media/wps17-1699415557955-104.jpg) | ![img](./media/wps18-1699415557955-105.jpg)                 |
| Jumper Wires                                | USB Cable*1                                                 |

3.Component Knowledge

**8\*8 dot matrix module：**The 8\*8 dot matrix is composed of 64 LEDs, including row common anode and row common cathode. Our module is row common anode, each row has a line connecting the positive pole of the LED, and the column is connecting the negative pole of the LED lamp, as shown in the following figure :

![](./media/69c719a7898907ab32f089f0cbbaff13-1699415557955-106.png)

![](./media/bcfa2498367eaf9c7733da15af32eae7-1699415557955-107.png)

4.Wiring Diagram

![](./media/af4d73ef798a933228f16dedc6578b8e-1699415557955-108.png)

5.Test Code
```c
//**********************************************************************************
/* 
 * Filename    : 8×8 Dot-matrix Display
 * Description : 8×8 Dot-matrix displays numbers from 0 to 9.
 * Auther      : http//www.keyestudio.com
*/
int R[] = {14,26,4,27,19,16,18,17};
int C[] = {32,21,22,12,0,13,33,25};

unsigned char data_0[8][8] =
{
{0,0,1,1,1,0,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,0,1,1,1,0,0,0}
};

unsigned char data_1[8][8] =
{
{0,0,0,0,1,0,0,0},
{0,0,0,1,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,1,1,1,0,0}
};

unsigned char data_2[8][8] =
{
{0,0,1,1,1,0,0,0},
{0,1,0,0,0,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,1,0,0,0,0},
{0,0,1,0,0,0,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_3[8][8] =
{
{0,0,1,1,1,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,1,1,1,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_4[8][8] =
{
{0,1,0,0,0,0,0,0},
{0,1,0,0,1,0,0,0},
{0,1,0,0,1,0,0,0},
{0,1,1,1,1,1,1,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_5[8][8] =
{
{0,1,0,0,0,0,0,0},
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,0,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_6[8][8] =
{
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,0,0,0},
{0,1,0,0,0,0,0,0},
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_7[8][8] =
{
{0,0,0,0,0,0,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,1,0,0,0},
{0,0,0,1,0,0,0,0},
{0,0,1,0,0,0,0,0},
{0,1,0,0,0,0,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_8[8][8] =
{
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

unsigned char data_9[8][8] =
{
{0,1,1,1,1,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,1,0,0},
{0,0,0,0,0,1,0,0},
{0,1,1,1,1,1,0,0},
{0,0,0,0,0,0,0,0}
};

void Display(unsigned char dat[8][8])
{
for(int c = 0; c<8;c++)
{
digitalWrite(C[c],LOW);
for(int r = 0;r<8;r++)
{
digitalWrite(R[r],dat[r][c]);
}
delay(1);
Clear();
}
}

void Clear()
{
for(int i = 0;i<8;i++)
{
digitalWrite(R[i],LOW);
digitalWrite(C[i],HIGH);
}
}

void setup(){
  for(int i = 0;i<8;i++)
  {
    pinMode(R[i],OUTPUT);
    pinMode(C[i],OUTPUT);
  }

}

void loop(){
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_0);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_1);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_2);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_3);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_4);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_5);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_6);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_7);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_8);
  }
  for (int i = 1; i <= 100; i = i + (1)) {
    Display(data_9);
  }
}
//**********************************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the 8\*8 dot matrix displays the numbers 0\~9 respectively.

## Project 11：74HC595N Control 8 LEDs 

1.Introduction

In previous projects, we learned how to light up an LED. With only 32 IO ports on ESP32, how do we light up a lot of
leds? Sometimes it is possible to run out of pins on the ESP32, and you need to extend it with the shift register. You can use the 74HC595N chip to control 8 outputs at a time, taking up only a few pins on your microcontroller. In addition, you can also connect multiple registers together to further expand the output.

In this project, we will use a ESP32，a 74HC595 chip and LEDs to make a flowing water light to understand the function of the 74HC595 chip.

2.Components

| ![img](./media/wps19-1699415557955-109.png) | ![img](./media/wps20-1699415557955-110.jpg) | ![img](./media/wps21-1699415557955-111.jpg) | ![img](./media/wps22-1699415557955-112.jpg) |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                | 74HC595N chip*1                             | Jumper Wires                                |
| ![img](./media/wps23-1699415557955-113.jpg) | ![img](./media/wps24-1699415557955-114.jpg) | ![img](./media/wps25-1699415557955-115.jpg) |                                             |
| 220Ω Resistor*8                             | Red LED*8                                   | USB Cable*1                                 |                                             |


3.Component Knowledge

![](./media/6921c6d60135e072ed4bd24564ec4a6d-1699415557955-116.png)

**74HC595N Chip:** To put it simply, 74HC595N chip is a combination of 8-digit shifting register, memorizer and equipped with tri-state output. The shift register and the memorizer are synchronized to different clocks, and the data is input on the rising edge of the shift register clock SCK and goes into the memory register on the rising edge of the memory register clock RCK.

If the two clocks are connected together, the shift register is always one pulse earlier than the storage register. The shift register has a serial shift input (SI) and a serial output (SQH) for cascading. The 8-bit shift register can be reset asynchronously (low-level reset), and the storage register has an 8-bit Three-state parallel bus output, when the output enable (OE) is enabled (active low), the storage register is output to the 74HC595N pin (bus).

![](./media/858b189f06ad68afe051b15043b2affd-1699415557955-117.png)

**Pins**：

<table border="1">
<tbody>
<tr class="odd">
<td>Pin13 OE</td>
<td>It is an output enable pin to ensure that the data of the latch is input to the Q0 to Q7 pins or not. When it is low, no high level is output. In this experiment, we directly connect to GND and keep the data output low.</td>
</tr>
<tr class="even">
<td>Pin14 SI</td>
<td>This is the pin for 74HC595 to receive data, i.e. serial data input, only one bit can be input at a time, then 8 times in a row, it can form a byte.</td>
</tr>
<tr class="odd">
<td>Pin10 SCLR</td>
<td>A pin to initialize the storage register pins. It initializes the internal storage registers at a low level. In this experiment, we connect VCC to maintain a high level.</td>
</tr>
<tr class="even">
<td>Pin11 SCK</td>
<td>The clock pin of the shift register. At the rising edge, the data in the shift register is shifted backward as a whole, and new data input is received.</td>
</tr>
<tr class="odd">
<td>Pin12 RCK</td>
<td>The clock input pin of the storage register . At the rising edge, the data is transferred from the shift register to the storage register. At this time, the data is output in parallel from the Q0 to Q7 ports.</td>
</tr>
<tr class="even">
<td>Pin9 SQH</td>
<td>It is a serial output pin dedicated for chip cascading to the SI terminal of the next 74HC595.</td>
</tr>
<tr class="odd">
<td>Q0--Q7(Pin 15,Pin1-7)</td>
<td>Eight-bit parallel output, can directly control the 8 segments of the digital tube.</td>
</tr>
</tbody>
</table>

4.Wiring Diagram

Note: Pay attention to the direction in which the 74HC595N chip is inserted.

![](./media/image-20231108141143286.png)![image-20231108141147208](./media/image-20231108141147208.png)

![](./media/11a03579b6cf94599f00554bfe014a3b-1699415557955-119.png)

5.Test Code

```c
//**********************************************************************
/* 
 * Filename    : 74HC595N Control 8 LEDs
 * Description : Use 74HC575N to drive ten leds to display the flowing light.
 * Auther      : http//www.keyestudio.com
*/
int dataPin = 14;   // Pin connected to DS of 74HC595(Pin14)  
int latchPin = 12;  // Pin connected to ST_CP of 74HC595(Pin12)
int clockPin = 13;  // Pin connected to SH_CP of 74HC595(Pin11) 
    void setup() {
      // set pins to output
      pinMode(latchPin, OUTPUT);
      pinMode(clockPin, OUTPUT);
      pinMode(dataPin, OUTPUT);
    }
    void loop() {
  // Define a one-byte variable to use the 8 bits to represent the state of 8 LEDs of LED bar graph.
  // This variable is assigned to 0x01, that is binary 00000001, which indicates only one LED light on.
  byte x = 0x01;    // 0b 0000 0001
  for (int j = 0; j < 8; j++) { // Let led light up from right to left
    writeTo595(LSBFIRST, x);
    x <<= 1; // make the variable move one bit to left once, then the bright LED move one step to the left once.
    delay(50);
  }
  delay(100);
  x = 0x80;       //0b 1000 0000
  for (int j = 0; j < 8; j++) { // Let led light up from left to right
    writeTo595(LSBFIRST, x);
    x >>= 1;    
    delay(50);
  }
  delay(100);
}
void writeTo595(int order, byte _data ) {
  // Output low level to latchPin
  digitalWrite(latchPin, LOW);
  // Send serial data to 74HC595
  shiftOut(dataPin, clockPin, order, _data);
  // Output high level to latchPin, and 74HC595 will update the data to the parallel output port.
  digitalWrite(latchPin, HIGH);
}
//**********************************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the 8 LEDs start flashing in flowing water mode.

## Project 12：Active Buzzer

1.Introduction

Active buzzer is a sound component that is widely used as a sound component for computers, printers, alarms, electronic toys and phones, timers etc. It has an internal vibration source, just by connecting to a 5V power supply, it can continuously buzz. In this project, we will use ESP32 to control the active buzzer to beep.

2.Components

| ![img](./media/wps26-1699415557955-120.png) | ![img](./media/wps27-1699415557955-121.jpg) | ![img](./media/wps28-1699415557955-122.jpg) |                                             |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                | Active buzzer*1                             |                                             |
| ![img](./media/wps29-1699415557955-123.jpg) | ![img](./media/wps30-1699415557955-124.jpg) | ![img](./media/wps31-1699415557955-125.jpg) | ![img](./media/wps32-1699415557955-126.jpg) |
| NPN Transistor(S8050)*1                     | 1kΩ Resistor*1                              | Jumper Wires                                | USB Cable*1                                 |


3.Component Knowledge

![](./media/11ec5ddc982db9928341e858aab94652-1699415557955-127.png)

The active buzzer inside has a simple oscillator circuit , which can convert constant direct current into a certain frequency pulse signal. Once active buzzer receives a high level, it will sound. The passive buzzer is an integrated electronic buzzer with no internal vibration source. It must be driven by 2K to 5K square wave instead of a DC signal.

The appearance of the two buzzers is very similar, but passive buzzers come with a green circuit board, and active buzzers come with a black tape. Passive buzzers don't have positive pole, but active buzzers have. As shown below:

![](./media/0f9825969867ac2d65bb1a19ed0ad2ab-1699415557955-128.png)

**Transistor:**

![](./media/9197d4aff9356c585b7ef68e33a6881d-1699415557955-129.png)

Since the buzzer requires such large current that GPIO of ESP32 output capability cannot meet the requirement, a transistor of NPN type is needed here to amplify the current.

Transistor, the full name: semiconductor transistor, is a semiconductor device that controls current. Transistor can be used to amplify weak signal, or work as a switch. It has three electrodes(PINs): base (b), collector (c) and emitter (e).

When there is current passing between "be", "ce" , which will allow several-fold current (transistor magnification) pass, at this point, transistor works in the amplifying area. When current between "be" exceeds a certain value, "ce" , which will not allow current to increase any longer, at this point, transistor works in the saturation area. Transistor has two types as shown below: PNP and NPN,

![](./media/02dad9f2fcac0d7bfe4cc135d2301aa6-1699415557955-130.png)

PNP transistor NPN transistor

In our kit, the PNP transistor is marked with 8550, and the NPN transistor is marked with 8050.

Based on the transistor's characteristics, it is often used as a switch in digital circuits. As micro-controller's capacity to output current is very weak, we will use a transistor to amplify current and drive large-current components.

When using the NPN transistor to drive a buzzer, we often adopt the following method. If GPIO outputs high level, current will flow through R1, the transistor will get conducted, and the buzzer will sound. If GPIO outputs low level, no current flows through R1, the transistor will not be conducted, and buzzer will not sound.

When using the PNP transistor to drive a buzzer, we often adopt the following method. If GPIO outputs low level, current will flow through R1, the transistor will get conducted, and the buzzer will sound. If GPIO outputs high level, no current flows through R1, the transistor will not be conducted, and buzzer will not sound.

![](./media/2a9755ec14ab58c67d7d8341601d8dbc-1699415557955-131.png)

4.Wiring Diagram

![](./media/5c215684c8945622441478edb6f16e30-1699415557955-132.png)

Note: The buzzer power supply in this circuit is 5V. On a 3.3V power supply, the buzzer can work, but it will reduce the loudness.

5.Test Code

```c
//**********************************************************************
/* 
 * Filename    : Active Buzzer
 * Description : Active buzzer beeps.
 * Auther      : http//www.keyestudio.com
*/
#define buzzerPin  15   //define buzzer pins

void setup ()
{
  pinMode (buzzerPin, OUTPUT);
}
void loop ()
{
  digitalWrite (buzzerPin, HIGH);
  delay (500);
  digitalWrite (buzzerPin, LOW);
  delay (500);
}
//**********************************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the active buzzer beeps.

## Project 13：Passive Buzzer

1.Introduction

In a previous project, we studied an active buzzer, which can only make a sound and may make you feel very monotonous. In this project, we will learn a passive buzzer and use the ESP32 control it to work. Unlike the active buzzer, the passive buzzer can emit sounds of different frequencies. 

2. Components

| ![img](./media/wps33-1699415557955-133.png) | ![img](./media/wps34-1699415557956-134.jpg) | ![img](./media/wps35-1699415557956-135.jpg) |                                             |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                | Passive Buzzer *1                           |                                             |
| ![img](./media/wps36-1699415557956-136.jpg) | ![img](./media/wps37-1699415557956-137.jpg) | ![img](./media/wps38-1699415557956-138.jpg) | ![img](./media/wps39-1699415557956-139.jpg) |
| NPN Transistor(S8050)*1                     | 1kΩResistor*1                               | Jumper Wires                                | USB Cable*1                                 |


3.Component Knowledge：

![](./media/8d0020e53824072cbe9d4f7d2f8acb4f-1699415557956-140.png)

**Passive buzzer:** A passive buzzer is an integrated electronic buzzer with no internal vibration source and it has to be driven by 2K-5K square waves, not DC signals. The two buzzers are very similar in appearance, but one buzzer with a green circuit board is a passive buzzer and the other buzzer with black tape is an active buzzer. Passive buzzers cannot distinguish between positive polarity while active buzzers can.

![](./media/fc42c5ed014609ff0b290ee5361bb2fd-1699415557956-141.png)

**Transistor:** Please refer to project 12.

4.Wiring Diagram

![](./media/9c12d89ce3f10c838e63f1334f41fc9e-1699415557956-142.png)

5.Test Code

```c
//**********************************************************************
/*
 * Filename    : Passive Buzzer
 * Description : Passive Buzzer sounds the alarm.
 * Auther      : http//www.keyestudio.com
*/
#define LEDC_CHANNEL_0 0

// LEDC timer uses 13 bit accuracy

#define LEDC_TIMER_13_BIT  13

// Define tool I/O ports

#define BUZZER_PIN  15

//Create a musical melody list, Super Mario

int melody[] = {330, 330, 330, 262, 330, 392, 196, 262, 196, 165, 220, 247, 233, 220, 196, 330, 392, 440, 349, 392, 330, 262, 294, 247, 262, 196, 165, 220, 247, 233, 220, 196, 330, 392,440, 349, 392, 330, 262, 294, 247, 392, 370, 330, 311, 330, 208, 220, 262, 220, 262,

294, 392, 370, 330, 311, 330, 523, 523, 523, 392, 370, 330, 311, 330, 208, 220, 262,220, 262, 294, 311, 294, 262, 262, 262, 262, 262, 294, 330, 262, 220, 196, 262, 262,262, 262, 294, 330, 262, 262, 262, 262, 294, 330, 262, 220, 196};

//Create a list of tone durations

int noteDurations[] = {8,4,4,8,4,2,2,3,3,3,4,4,8,4,8,8,8,4,8,4,3,8,8,3,3,3,3,4,4,8,4,8,8,8,4,8,4,3,8,8,2,8,8,8,4,4,8,8,4,8,8,3,8,8,8,4,4,4,8,2,8,8,8,4,4,8,8,4,8,8,3,3,3,1,8,4,4,8,4,8,4,8,2,8,4,4,8,4,1,8,4,4,8,4,8,4,8,2};
void setup() {
pinMode(BUZZER_PIN, OUTPUT); // Set the buzzer to output mode
}

void loop() {

  int noteDuration; //Create a variable of noteDuration

  for (int i = 0; i < sizeof(noteDurations); ++i)

  {
      noteDuration = 800/noteDurations[i];

      ledcSetup(LEDC_CHANNEL_0, melody[i]*2, LEDC_TIMER_13_BIT);

      ledcAttachPin(BUZZER_PIN, LEDC_CHANNEL_0);

      ledcWrite(LEDC_CHANNEL_0, 50);

      delay(noteDuration * 1.30); //delay
  }
}
//**********************************************************************
```


6.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the passive buzzer plays music.

## Project 14: Mini Table Lamp

1. Introduction

Do you know that the ESP32 can light up an LED when you press a button? In this project, we will use a ESP32, a button switch and a LED to make a mini table lamp.

2. Components

| ![img](./media/wps40-1699415557956-143.png) | ![img](./media/wps41-1699415557956-144.jpg) | ![img](./media/wps42-1699415557956-145.jpg) | ![img](./media/wps43-1699415557956-146.jpg) |                                             |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                | Button*1                                    | 10KΩ Resistor*1                             |                                             |
| ![img](./media/wps44-1699415557956-147.jpg) | ![img](./media/wps45-1699415557956-148.jpg) | ![img](./media/wps46-1699415557956-149.jpg) | ![img](./media/wps47-1699415557956-150.jpg) | ![img](./media/wps48-1699415557956-151.jpg) |
| Red LED*1                                   | 22Ω Resistor*1                              | USB Cable*1                                 | Jumper Wires                                | Button Cap*1                                |

3. Component Knowledge

![](./media/5b8fea4657b47510d199f740fdcaaa9d-1699415557956-152.png)

**Button:** A button can control the circuit on and off, the button is plugged into a circuit, the circuit is disconnected when the button is not pressed. The circuit works when you press the button, but breaks again when you release it. Why does it only work when you press it? It starts from the internal structure of the button, which don’t allow current to travel from one end of the button to the other before it is pressed. When pressed, a metal strip inside the button connects the two sides to allow electricity to pass through.

The internal structure of the button is shown in the figure：![](./media/d2a204e61c768f18924150db58aee093-1699415557956-153.png). Before the button is pressed, 1 and 2 are on, 3 and 4 are also on, but 1, 3 or 1, 4 or 2, 3 or 2, 4 are off(not working). Only when the button is pressed, 1, 3 or 1, 4 or 2, 3 or 2, 4 are on.

The button switch is one of the most commonly used components in circuit design.

**Schematic diagram of the button:**

![](./media/5e42fde9876f9be810d85a7fb8b331f7-1699415557956-154.png) ![](./media/8677548f9e756281629430d66ba3a460-1699415557956-155.png)

**What is button** **shake?**

We think of the switch circuit as "press the button and turn it on immediately", press it again and turn it off immediately". In fact, this is not the case.

The button usually uses a mechanical elastic switch, and the mechanical elastic switch will produce a series of [shake](javascript:;) due to the
elastic action at the moment when the mechanical contact is opened and closed (usually about 10ms). As a result, the button switch will not immediately and stably turn on the circuit when it is closed, and it will not be completely and instantaneously disconnected when it is turned off.

![](./media/7e7ac82db8bb810a7ee1de4181ceaa2d-1699415557956-156.jpeg)

**How to eliminate the shake?**

There are two common methods, namely fix shake in the software and hardware. We only discuss the shake removal
in the software.

We already know that the shake time generated by elasticity is about 10ms, and the delay command can be used to delay the
execution time of the command to achieve the effect of shake removal.

Therefore, we delay 0.02s in the code to achieve the key anti-shake function.

![](./media/c0d68d1134b0b4097e8983ed2cac07fc-1699415557956-157.jpeg)

4. Wiring Diagram

![](./media/a5b85f1e1f5714afbe4730b1265e3a15-1699415557956-158.png)

**Note:**

How to connect the LED

![](./media/f70404aa49540fd7aecae944c7c01f83-1699415557953-20.jpeg)

How to identify the 220Ω 5-band resistor and 10KΩ 5-band resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

5. Test code

```c
//******************************************************************
/* 

 * Filename    : Mini Table Lamp
 * Description : Make a table lamp.
 * Auther      : http//www.keyestudio.com
   */
   #define PIN_LED    4
   #define PIN_BUTTON 15
   bool ledState = false;

void setup() {
  // initialize digital pin PIN_LED as an output.
  pinMode(PIN_LED, OUTPUT);
  pinMode(PIN_BUTTON, INPUT);
}

// the loop function runs over and over again forever
void loop() {
  if (digitalRead(PIN_BUTTON) == LOW) {
    delay(20);
    if (digitalRead(PIN_BUTTON) == LOW) {
      reverseGPIO(PIN_LED);
    }
    while (digitalRead(PIN_BUTTON) == LOW);
  }
}

void reverseGPIO(int pin) {
  ledState = !ledState;
  digitalWrite(pin, ledState);
}
//**********************************************************************
```

6. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that press the push button switch, the LED turns on; When it is released, the LED is still on. Press it again, and the LED turns off. When it is released, the LED stays off. Doesn't it look like a mini table lamp?

## Project 15：Tilt And LED

1. Introduction

The ancients without electronic clock, so the hourglass are invented to measure time. The hourglass has a large capacity on both sides, and which is filled with fine sand on one side. What’s more, there is a small channel in the middle, which can make the hourglass stand upright, the side with fine sand is on the top. due to the effect of gravity,the fine sand will flow down through the channel to the other side of the hourglass.

When the sand reaches the bottom, turn it upside down and record the number of times it has gone through the hourglass, therefore, the next day we can know the approximate time of the day by it.

In this project, we will use ESP32 to control the tilt switch and LED lights to simulate an hourglass to make an electronic hourglass.

2. Components

| ![img](./media/wps49-1699415557956-159.png) | ![img](./media/wps50-1699415557956-160.jpg) | ![img](./media/wps51-1699415557956-161.jpg) | ![img](./media/wps52-1699415557956-162.jpg) |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Tilt Switch*1                               | Red LED*4                                   | 10KΩ Resistor*1                             |
| ![img](./media/wps53-1699415557956-163.jpg) | ![img](./media/wps54-1699415557956-164.jpg) | ![img](./media/wps55-1699415557956-165.jpg) | ![img](./media/wps56-1699415557956-166.jpg) |
| Breadboard*1                                | 220Ω Resistor*4                             | USB Cable*1                                 | Jumper Wires                                |

3. Component Knowledge

![](./media/8c40739f8e05f753f145420b421a0f47-1699415557956-167.png)

Tilt switch is also called digital switch. Inside is a metal ball that can roll. The principle of rolling the metal ball to contact with the
conductive plate at the bottom, which is used to control the on and off of the circuit. When it is a rolling ball tilt sensing switch with single directional trigger, the tilt sensor is tilted toward the trigger end (two gold-plated pin ends), the tilt switch is in a closed circuit and the voltage at the analog port is about 5V(binary number is 1023).

In this way, the LED will light up. When the tilting switch is in horizontal position or tilting to the other end, the tilting switch is
in open state the voltage of the analog port is about 0V (binary number is 0), the LED will turn off. In the program, we judge the state of the switch based on whether the voltage value of the analog port is greater than 2.5V (binary number is 512).

The internal structure of the tilt switch is used here to illustrate how it works, as shown below:

![](./media/bf8b10ad248ac939ac4ef96d02ed87c7-1699415557956-168.png)

4. Wiring Diagram

![](./media/a46c0b8be898ba596308ce56993c26ba-1699415557956-169.png)

Note:

How to connect the LED

![](./media/f70404aa49540fd7aecae944c7c01f83-1699415557953-20.jpeg)

How to identify the 220Ω 5-band resistor and 10KΩ 5-band resistor

![](./media/55c0199544e9819328f6d5778f10d7d0-1699415557953-22.png)

![](./media/246cf3885dc837c458a28123885c9f7b-1699415557953-23.png)

5. Test Code

```c
//******************************************************************
/* 
 * Filename    : Tilt And LED
 * Description : Tilt switches and four leds to simulate an hourglass.
 * Auther      : http//www.keyestudio.com
*/
   #define SWITCH_PIN  15  // the tilt switch is connected to Pin15
   byte switch_state = 0;
   void setup()
   {
     for(int i=16;i<20;i++)
     {
        pinMode(i, OUTPUT);
     } 
    pinMode(SWITCH_PIN, INPUT);
    for(int i=16;i<20;i++)
     {
    digitalWrite(i,0);
     } 
     Serial.begin(9600);
   }
   void loop()
   {
   switch_state = digitalRead(SWITCH_PIN); 
   Serial.println(switch_state);
    if (switch_state == 0) 
    {
    for(int i=16;i<20;i++)
     {
    digitalWrite(i,1);
    delay(500);
     } 
     }
   if (switch_state == 1) 
    {
   for(int i=19;i>15;i--)
   {
    digitalWrite(i,0);
    delay(500);
   }
     }
   }
   //**********************************************************************************
```

6. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that when you tilt the breadboard to an angle, the LEDs will light up one by one. When you turn the breadboard to the original angle, the LEDs will turn off one by one. Like the hourglass, the sand will leak out over time.

## Project 16: I2C 128×32 LCD

1. Introduction

In everyday life, we can do a host of experiments with the display module and also DIY a broad menu of small objects. For example, you can make a temperature meter with a temperature sensor and a display, or make a distance meter with an ultrasonic module and a display. 

In this project, we will use the LCD\_128X32\_DOT module as the display and connect it to the ESP32, which will be used to control
the LCD\_128X32\_DOT display to show various English words, common symbols and numbers.

2. Components

| ![img](./media/wps57-1699415557956-170.png) | ![img](./media/wps58-1699415557956-171.jpg) |                                             |
| ------------------------------------------- | ------------------------------------------- | ------------------------------------------- |
| ESP32*1                                     | Breadboard*1                                |                                             |
| ![img](./media/wps59-1699415557956-172.jpg) | ![img](./media/wps60-1699415557956-173.jpg) | ![img](./media/wps61-1699415557956-174.jpg) |
| LCD_128X32_DOT*1                            | M-F Dupont Wires                            | USB Cable*1                                 |

3. Component Knowledge

![](./media/2c2645e94a00867ac23e8a022f0a631a-1699415557956-175.png)

**LCD\_128X32\_DOT**: It is an LCD module with 128\*32 pixels and its driver chip is ST7567A. The module uses the IIC communication mode, while the code contains a library of all alphabets and common symbols that can be called directly.

When using, we can also set it in the code so that the English letters and symbols show different text sizes. To make it easy to set up the pattern display, we also provide a mold capture software that converts a specific pattern into control code and then copies it directly into the test code for use.

**Schematic diagram of LCD\_128X32\_DOT**

![](./media/5451aed32bc5b7b30fbd5613ad09a65b-1699415557956-176.png)

**Features:**

Pixel: 128\*32 character

Operating voltage(chip)：4.5V to 5.5V

Operating current：100mA (5.0V)

Optimal operating voltage(module):5.0V

4. Wiring Diagram

![](./media/072d954dac310add077688398ad59af2-1699415557956-177.png)

5. Adding the lcd128\_32\_io library

This code uses a library named "**lcd128\_32\_io**", if you haven't installed it yet, please do so before learning. The steps to add third-party libraries are as follows:

Click on the link to download the library file:[Arduino C "lcd128_32_io.h" Librarie](./Arduino-Librarie.zip)

6. Test Code


```C
//**********************************************************************************
/*

 * Filename    : LCD 128*32
 * Description : LCD 128*32 display string
 * Auther      : http//www.keyestudio.com
   */
   #include "lcd128_32_io.h"

//Create lCD128 *32 pin，sda--->21， scl--->22
lcd lcd(21, 22);

void setup() {
  lcd.Init(); //initialize
  lcd.Clear();  //clear
}

void loop() {
  lcd.Cursor(0, 4); //Set display position
  lcd.Display("KEYESTUDIO"); //Setting the display
  lcd.Cursor(1, 0);
  lcd.Display("ABCDEFGHIJKLMNOPQR");
  lcd.Cursor(2, 0);
  lcd.Display("123456789+-*/<>=$@");
  lcd.Cursor(3, 0);
  lcd.Display("%^&(){}:;'|?,.~\\[]");
}
//**********************************************************************************
```



6. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the 128X32LCD module display will show“KEYESTUDIO”at the first line，“ABCDEFGHIJKLMNOPQR”will be displayed at the second
line，“123456789+-\*/\<\>=$@”will be shown at the third line and“%^&(){}:;'|?,.\~\\\\\[\]”will be displayed at the fourth line.

## Project 17：Small Fan

1. Introduction

In hot summer, we need electric fans to cool us down, so in this project, we will use a ESP32 to control a DC motor and small fan blades to make a **small electric fan.**

2. Components

| ![img](./media/wps1-169802292392031-1699415557956-178.png) | ![img](./media/wps2-1699415557956-179.png)                  | ![img](./media/wps3-169802292689932-1699415557957-180.jpg)  | ![img](./media/wps4-169802292821233-1699415557957-181.jpg) | ![img](./media/wps5-169802292946134-1699415557957-182.jpg)  |
| ---------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                    | DC Motor*1                                                  | Breadboard*1                                                | Fan*1                                                      | NPN Transistor (S8050)*1                                    |
| ![img](./media/wps6-169802293138035-1699415557957-183.jpg) | ![img](./media/wps7-169802293310736-1699415557957-184.jpg)  | ![img](./media/wps8-169802293466837-1699415557957-185.jpg)  | ![img](./media/wps9-169802293611538-1699415557957-186.jpg) | ![img](./media/wps10-169802293761939-1699415557957-187.jpg) |
| PNP Transistor (S8550)*1                                   | 1KΩ Resistor*1                                              | Jumper Wire                                                 | Diode*1                                                    | USB Cable*1                                                 |
| ![img](./media/wps11-1699415557957-188.png)                | ![img](./media/wps12-169802294110740-1699415557957-189.jpg) | ![img](./media/wps13-169802294237941-1699415557957-190.jpg) |                                                            |                                                             |
| 6 AA Battery Holder*1                                      | Keyestudio Breadboard Power Module*1                        | AA Battery(Self-prepared)*6                                 |                                                            |                                                             |

3. Component Knowledge:

**Keyestudio Breadboard Power Supply Module：**

![7ff03f4506988f1ce99c5757892fc6de-1699410520133-189](./media/7ff03f4506988f1ce99c5757892fc6de-1699410520133-189.jpeg)

**Introduction:**

This breadboard power supply module is compatible with 5V and 3.3V, which can be applied to MB102 breadboard. The module contains two channels of independent control, powered by the USB all the way.

The output voltage is constant for the DC5V, and another way is powered by DC6.5-12V, output controlled by the slide switch, respectively for DC 5V and DC 3.3V.

If the other power supply is DC 6.5-12v, when the slide switch is switched to +5V, the output voltages of the left and right lines of the module are DC 5V. When the slide switch is switched to +3V, the output voltage of the USB power supply terminal of the module is DC 5V , and the output voltage of the DC 6.5-12V power supply terminal of the other power supply is DC 3.3V.

**Specification:**

- Applied to MB102 breadboard;

- Input voltage：DC 6.5-12V or powered by USB;

- Output voltage：3.3V or 5V

- Max output current:\<700ma

- Up and down two channels of independent control, one of which can be
switched to 3.3V or 5V;

Comes with two sets of DC output pins, easy for external use.

4. Wiring Diagram 1：

We use the S8050（NPN transistor) to control the motor

![](./media/715ae32c3fac7c6537f380fb91e5e83c-1699415557957-192.png)

Wire up first, then connect a fan at the DC motor

5. Test Code 1：


```C
//**********************************************************************
/* 

 * Filename    : Small_Fan
 * Description : S8050 triode drives the motor working
 * Auther      : http//www.keyestudio.com
   */

void setup() {

  pinMode(15, OUTPUT); // Initialize pin 15 as output.
}

void loop() {
  digitalWrite(15, HIGH);   // Turn on the motor (HIGH means HIGH level)
  delay(4000);              // Delay 4 seconds
  digitalWrite(15, LOW);    // Reduce the voltage and turn off the motor
  delay(2000);              // Delay 2 seconds
}
//**********************************************************************************
```

6. Test Result 1：

Upload the code to the ESP32 and power up. You will view the motor rotate for 4s, stop for 2s, in a loop way

7. Wiring Diagram 2：

We use the S8050（PNP transistor) to control the motor

![](./media/04293fbe70eeec27c2d8127f42afbaf2-1699415557957-193.png)

Wire up first, then connect a fan at the DC motor

8. Test Code 2：


```C
//**********************************************************************
/* 

 * Filename    : Small_Fan
 * Description : S8550 triode drives the motor working
 * Auther      : http//www.keyestudio.com
   */

void setup() {

  pinMode(15, OUTPUT); // Initialize pin 15 as output.
}

void loop() {
  digitalWrite(15, LOW);   // Turn on the motor (LOW means LOW level)
  delay(4000);              // Delay 4 seconds
  digitalWrite(15, HIGH);    // Raise the voltage and turn off the motor
  delay(2000);              // Delay 2 seconds
}
//**********************************************************************************
```

9. Test Result 2：

Upload the code to the ESP32 and power up. You will view the motor rotate for 4s, stop for 2s, in a loop way

## Project 18: Dimming Light

1. Introduction

A potentiometer is a three-terminal resistor with sliding or rotating contacts that forms an adjustable voltage divider. It works by changing the position of the sliding contacts across a uniform resistance. In the potentiometer, the entire input voltage is applied across the whole length of the resistor, and the output voltage is the voltage drop between the fixed and sliding contact.

In this project, we will learn how to use ESP32 to read the values of the potentiometer, and make a dimming lamp with LED.

2. Components

| ![img](./media/wps14-1699415557957-194.png)                 | ![img](./media/wps15-169802300085142-1699415557957-195.jpg) | ![img](./media/wps16-169802300201643-1699415557957-196.jpg) | ![img](./media/wps17-169802300331544-1699415557957-197.jpg) |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                     | Breadboard*1                                                | Potentiometer*1                                             | Red LED*1                                                   |
| ![img](./media/wps18-169802300523445-1699415557957-198.jpg) | ![img](./media/wps19-1699415557957-199.jpg)                 | ![img](./media/wps20-169802300990646-1699415557957-200.jpg) |                                                             |
| 220ΩResistor*1                                              | Jumper Wires                                                | USB Cable*1                                                 |                                                             |

3. Component Knowledge

![](./media/03ab81e8b4f09287d2781ef0fd297f85-1699415557957-201.png)

**Adjustable potentiometer:** It is a kind of resistor and an analog electronic component, which has two states of 0 and 1(high level and low level). The analog quantity is different, its data state presents a linear state such as 1 \~ 1024。

**ADC :** An ADC is an electronic integrated circuit used to convert analog signals such as voltages to digital or binary form consisting of 1s and 0s. The range of our ADC on ESP32 is 12 bits, that means the resolution is 2^12=4096, and it represents a range (at 3.3V) will be divided equally to 4096 parts. The rage of analog values corresponds to ADC values. So the more bits the ADC has, the denser the partition of analog will be and the greater the precision of the resulting conversion.

![](./media/f6c45550f4adf8373d7f1d01daec2c64-1699415557957-202.png)

Subsection 1: the analog in rang of 0V---3.3/4095 V corresponds to digital 0.

Subsection 2: the analog in rang of 3.3/4095 V---2\*3.3 /4095V corresponds to digital 1;

The following analog will be divided accordingly.

The conversion formula is as follows:

![img](./media/wps1-1699424129578-20.png)

**DAC：**The reversing of this process requires a DAC, Digital-to-Analog Converter. The digital I/O port can output high level and low level (0 or 1), but cannot output an intermediate voltage value.

This is where a DAC is useful. ESP32 has two DAC output pins with 8-bit accuracy, GPIO25 and GPIO26, which can divide VCC (here is 3.3V) into 2^8=256 parts. For example, when the digital quantity is 1, the output voltage value is 3.3/256 \*1 V, and when the digital quantity is 128, the output voltage value is 3.3/256 \*128=1.65V, the higher the accuracy of DAC, the higher the accuracy of output voltage value will be.

The conversion formula is as follows:

![img](./media/wps2-1699424140244-22.png)

**ADC on ESP32：**

ESP32 has 16 pins can be used to measure analog signals. GPIO pin sequence number and analog pin definition are shown in the following table：

| **ADC number in ESP32** | **ESP32 GPIO number** |
| ----------------------- | --------------------- |
| **ADC0**                | **GPIO 36**           |
| **ADC3**                | **GPIO 39**           |
| **ADC4**                | **GPIO 32**           |
| **ADC5**                | **GPIO33**            |
| **ADC6**                | **GPIO34**            |
| **ADC7**                | **GPIO 35**           |
| **ADC10**               | **GPIO 4**            |
| **ADC11**               | **GPIO0**             |
| **ADC12**               | **GPIO2**             |
| **ADC13**               | **GPIO15**            |
| **ADC14**               | **GPIO13**            |
| **ADC15**               | **GPIO 12**           |
| **ADC16**               | **GPIO 14**           |
| **ADC17**               | **GPIO27**            |
| **ADC18**               | **GPIO25**            |
| **ADC19**               | **GPIO26**            |


**DAC on ESP32：**

ESP32 has two 8-bit digital analog converters to be connected to GPIO25 and GPIO26 pins, respectively, and it is immutable. As shown in the following table：

| **Simulate pin number** | **GPIO number** |
| ----------------------- | --------------- |
| **DAC1**                | **GPIO25**      |
| **DAC2**                | **GPIO26**      |


The DAC pin number is already defined in ESP32's code base; for example, you can replace GPIO25 with DAC1 in the code.

4. Read the values of the potentiometer：

We connect the potentiometer to the analog IO port of ESP32 to read the ADC value, DAC value and voltage value of the potentiometer, please refer to the wiring diagram below：

![](./media/0cda3256a0930404abc097ec8ffa3013-1699415557957-203.png)

```C
//**********************************************************************************
/*  
 * Filename    : Read Potentiometer Analog Value
 * Description : Basic usage of ADC，DAC and Voltage
 * Auther      : http//www.keyestudio.com
*/
#define PIN_ANALOG_IN  36  //the pin of the Potentiometer

void setup() {
  Serial.begin(115200);
}

//In loop()，the analogRead() function is used to obtain the ADC value, and then the map() function is used to convert the value into an 8-bit precision DAC value. The input and output voltage are calculated according to the previous formula, and the information is finally printed out.
void loop() {
  int adcVal = analogRead(PIN_ANALOG_IN);
  int dacVal = map(adcVal, 0, 4095, 0, 255);
  double voltage = adcVal / 4095.0 * 3.3;
  Serial.printf("ADC Val: %d, \t DAC Val: %d, \t Voltage: %.2fV\n", adcVal, dacVal, voltage);
  delay(200);
}
//**********************************************************************************
```


Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable, open the serial monitor and set the baud rate to 115200 and press the reset button first.

You will see that the serial monitor window will print out the ADC value, DAC value and voltage value of the potentiometer. When turning the potentiometer handle, the ADC value, DAC value and voltage value will change. As shown below:

![](./media/64afecf1bfe9f634e352955c906a9632-1699415557957-204.png)

5. Wiring diagram of the dimming lamp

In the previous step, we read the ADC value, DAC value and voltage value of the potentiometer. Now we need to convert the ADC value of the potentiometer into the brightness of the LED to make a lamp that can adjust the brightness.The wiring diagram is as follow:

![](./media/3396bd77169711de6e15da73f14c8afb-1699415557957-205.png)

6. Test Code


```C
//**********************************************************************************
/*  

 * Filename    : Dimming Light
 * Description : Controlling the brightness of LED by potentiometer.
 * Auther      : http//www.keyestudio.com
   */
   #define PIN_ANALOG_IN    36  //the pin of the potentiometer
   #define PIN_LED     15  // the pin of the LED
   #define CHAN            0
   void setup() {
     ledcSetup(CHAN, 1000, 12);
     ledcAttachPin(PIN_LED, CHAN);
   }

void loop() {
  int adcVal = analogRead(PIN_ANALOG_IN); //read adc
  int pwmVal = adcVal;        // adcVal re-map to pwmVal
  ledcWrite(CHAN, pwmVal);    // set the pulse width.
  delay(10);
}
//**********************************************************************************
```

6. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that turn the potentiometer handle and the brightness of the LED will change accordingly.

![](./media/eca30dead3f4923afa0dcb0306db2319-1699415557957-206.jpeg)

## Project 19：Flame Alarm

1. Introduction

Fire is a terrible disaster and fire alarm systems are very useful in houses、commercial buildings and factories. In this project, we will use ESP32 to control a flame sensor, a buzzer and a LED to simulate fire alarm devices. This is a meaningful maker activity.

2. Component：

| ![img](./media/wps21-1699415557957-207.png)                 | ![img](./media/wps22-169802309482047-1699415557957-208.jpg) | ![img](./media/wps23-169802309620448-1699415557957-209.jpg) | ![img](./media/wps24-169802309736349-1699415557957-210.jpg) |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                     | Breadboard*1                                                | Red LED*1                                                   | Active Buzzer*1                                             |
| ![img](./media/wps25-169802309924950-1699415557957-211.jpg) | ![img](./media/wps26-1699415557957-212.jpg)                 | ![img](./media/wps27-169802310238051-1699415557957-213.jpg) | ![img](./media/wps28-169802310373752-1699415557957-214.jpg) |
| Flame Sensor*1                                              | 220Ω Resistor*1                                             | 10KΩResistor*1                                              | Jumper Wires                                                |
| ![img](./media/wps29-169802310559653-1699415557957-215.jpg) | ![img](./media/wps30-169802310790054-1699415557957-216.jpg) | ![img](./media/wps31-169802310924455-1699415557957-217.jpg) |                                                             |
| NPN Transistor(S8050)*1                                     | 1kΩ Resistor*1                                              | USB Cable*1                                                 |                                                             |

3. Component Knowledge

   ![image-20231108141632338](./media/image-20231108141632338.png)

The flame emits a certain amount IR light that is invisible to the human eye, but our flame sensor can detect it and alert a microcontroller(such as ESP32) that a fire has been detected. It has a specially designed infrared receiver tube to detect the flame and then convert the flame brightness into a fluctuating level signal. 

The short pin of the receiving triode is negative pole and the other long pin is positive pole. We should connect the short pin (negative) to 5V and the long pin (positive) to the analog pin, a resistor and GND. As shown in the figure below：

![](./media/87bd204db523c602c80745266c1ee452-1699415557957-219.png)

**Note:** Since vulnerable to radio frequency radiation and temperature changes, the flame sensor should be kept away from heat sources like radiators, heaters and air conditioners, as well as direct irradiation of sunlight, headlights and incandescent light.

4 .Read the values of the flame sensor

We first use a simple code to read the ADC value, DAC value and voltage value of the flame sensor and print them out. Please refer to the wiring diagram below：

![](./media/76ce57355da1df27e049bdc6e19f0650-1699415557957-220.png)

```C
//**********************************************************************************
/*  
 * Filename    : Read Analog Value Of Flame Sensor
 * Description : Basic usage of ADC，DAC and Voltage
 * Auther      : http//www.keyestudio.com
*/
#define PIN_ANALOG_IN  36  //the pin of the Flame sensor

void setup() {
  Serial.begin(115200);
}

//In loop()，the analogRead() function is used to obtain the ADC value, and then the map() function is used to convert the value into an 8-bit precision DAC value. The input and output voltage are calculated according to the previous formula, and the information is finally printed out.
void loop() {
  int adcVal = analogRead(PIN_ANALOG_IN);
  int dacVal = map(adcVal, 0, 4095, 0, 255);
  double voltage = adcVal / 4095.0 * 3.3;
  Serial.printf("ADC Val: %d, \t DAC Val: %d, \t Voltage: %.2fV\n", adcVal, dacVal, voltage);
  delay(200);
}
//**********************************************************************************
```


Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable, open the serial monitor and set the baud rate to 115200 and press the reset button first.

You will see that the serial monitor window will print out the ADC value, DAC value and voltage value of the flame sensor. When the sensor is closed to fire, the ADC value,DAC value and voltage value will get greater. Conversely, the ADC value,DAC value and voltage value decrease.

![](./media/64afecf1bfe9f634e352955c906a9632-1699415557957-204.png)

5. Wiring diagram of the flame alarm

Next, we will use a flame sensor, a buzzer, and a LED to make an interesting project, that is flame alarm. When flame is detected, the LED flashes and the buzzer alarms.

![](./media/e9fa0e50df23c1f2e58fdd319ad21b4c-1699415557957-221.png)

6. Test Code

（Note: ![](./media/1600623570befb10056c39ab4cc16806-1699415557957-222.png)the threshold of 500 in the code can be reset as required)


```C
//**********************************************************************************
/*  

 * Filename    : Flame Alarm
 * Description : Controlling the buzzer and LED by flame sensor.
 * Auther      : http//www.keyestudio.com
   */
   #define PIN_ADC0      36  //the pin of the flame sensor
   #define PIN_LED       15  // the pin of the LED
   #define PIN_BUZZER    4  // the pin of the buzzer

void setup() {
  pinMode(PIN_LED, OUTPUT);
  pinMode(PIN_BUZZER, OUTPUT);
  pinMode(PIN_ADC0, INPUT);
}

void loop() {
  int adcVal = analogRead(PIN_ADC0); //read the ADC value of flame sensor
  if (adcVal >= 500) {
    digitalWrite (PIN_BUZZER, HIGH); //turn on buzzer
    digitalWrite(PIN_LED, HIGH); // turn on LED
    delay(500); // wait a second.
    digitalWrite (PIN_BUZZER, LOW);
    digitalWrite(PIN_LED, LOW); // turn off LED
    delay(500); // wait a second
  }
 else
 {
    digitalWrite(PIN_LED, LOW);  //turn off LED
    digitalWrite (PIN_BUZZER, LOW); //turn off buzzer
  }
}
//**********************************************************************************
```

7. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that when the flame sensor detects the flame, the LED will flash and the buzzer will alarm, otherwise, the LED does not light up and the buzzer does not sound.

## Project 20: Night Lamp

1. Introduction

Sensors or components are ubiquitous in our daily life. For example, some public street lamps will automatically turn on at night and turn off during the day. In fact, this make use of a photosensitive element that senses the intensity of external ambient light. When the outdoor brightness decreases at night, the street lights will turn on automatically. In the daytime, the street lights will automatically turn off.

In this project, we use a ESP32 to control a LED to achieve the effect of the street light.

2. Components

| ![img](./media/wps32-1699415557957-223.png)                 | ![img](./media/wps33-1699415557957-226.jpg)                 | ![img](./media/wps34-169802317029758-1699415557957-224.jpg) | ![img](./media/wps35-169802317453661-1699415557957-225.jpg) |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                     | Breadboard*1                                                | Red LED*1                                                   | 10KΩResistor*1                                              |
| ![img](./media/wps36-169802316568356-1699415557957-227.jpg) | ![img](./media/wps37-169802316882157-1699415557958-228.jpg) | ![img](./media/wps38-169802317179559-1699415557958-229.jpg) | ![img](./media/wps39-169802317302860-1699415557958-230.jpg) |
| Photoresistor*1                                             | 220ΩResistor*1                                              | Jumper Wires                                                | USB Cable*1                                                 |

3. Component Knowledge

![9e553e75b6f976f33438171eb2f2e775-1699344906400-78](./media/9e553e75b6f976f33438171eb2f2e775-1699344906400-78.png)

**Photoresistor :** It is a kind of photosensitive resistor, its principle is that the photoresistor surface receives brightness (light)
to reduce the resistance, the resistance value will change with the detected intensity of the ambient light . With this characteristic, we can use the photoresistor to detect the light intensity. Photoresistor and its electronic symbol are as follows：

![](./media/7d575da675a2f6cb511d28b801e2abaa-1699415557958-233.png)

The following circuit is used to detect changes in resistance values of photoresistors：

![](./media/5a7f7e641eb78007760a94151c1d80a5-1699415557958-232.png)

In the circuit above, when the resistance of the photoresistor changes due to the change of light intensity, the voltage between the photoresistor and resistor R2 will also change.  Thus, the intensity of light can be obtained by measuring this voltage.

4. Read the values of the photoresistor

We first use a simple code to read the ADC value, DAC value and voltage value of the photoresistor and print them out. Please refer to the following wiring diagram：

![](./media/b762098c798beb08e4d433137c317dc7-1699415557958-234.png)

```C
//**********************************************************************************
/*  
 * Filename    : Read Photosensitive Analog Value
 * Description : Basic usage of ADC
 * Auther      : http//www.keyestudio.com
*/
#define PIN_ANALOG_IN  36  //the pin of the photosensitive sensor

void setup() {
  Serial.begin(115200);
}

//In loop()，the analogRead() function is used to obtain the ADC value, and then the map() function is used to convert the value into an 8-bit precision DAC value. The input and output voltage are calculated according to the previous formula, and the information is finally printed out.
void loop() {
  int adcVal = analogRead(PIN_ANALOG_IN);
  int dacVal = map(adcVal, 0, 4095, 0, 255);
  double voltage = adcVal / 4095.0 * 3.3;
  Serial.printf("ADC Val: %d, \t DAC Val: %d, \t Voltage: %.2fV\n", adcVal, dacVal, voltage);
  delay(200);
}
//**********************************************************************************
```


Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable, open the serial monitor and set the baud rate to 115200 and press the reset button first.

You will see that the serial monitor window will print out the ADC value、DAC value and voltage value of the photoresistor. When the light intensity around the photoresistor is gradually reduced, the ADC value, DAC value and voltage value will gradually increase. On the contrary, the ADC value, DAC value and voltage value decrease gradually.

![](./media/64afecf1bfe9f634e352955c906a9632-1699415557957-204.png)

5. Wiring diagram of the light-controlled lamp：

Now we will make a light controlled lamp. The principle is the same as the small dimming lamp , that is, the ESP32 takes the analog values of the sensor, and then adjusts the brightness of the LED.

![](./media/77a0c534501f51e7fe7aa221e4db71d9-1699415557958-235.png)

6. Test Code


```c
//**********************************************************************************
/*  

 * Filename    : Night Lamp
 * Description : Controlling the brightness of LED by photosensitive sensor.
 * Auther      : http//www.keyestudio.com
   */
   #define PIN_ANALOG_IN    36  // the pin of the photosensitive sensor
   #define PIN_LED     15  // the pin of the LED
   #define CHAN            0
   #define LIGHT_MIN       372
   #define LIGHT_MAX       2048
   void setup() {
     ledcSetup(CHAN, 1000, 12);
     ledcAttachPin(PIN_LED, CHAN);
   }

void loop() {
  int adcVal = analogRead(PIN_ANALOG_IN); //read adc
  int pwmVal = map(constrain(adcVal, LIGHT_MIN, LIGHT_MAX), LIGHT_MIN, LIGHT_MAX, 0, 4095);  // adcVal re-map to pwmVal
  ledcWrite(CHAN, pwmVal);    // set the pulse width.
  delay(10);
}
//**********************************************************************************
```

7. Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that when the intensity of light around the photoresistor is reduced, the LED will be bright, on the contrary, the LED will be dim.

## Project 21：Temperature Instrument

1.Introduction

Thermistor is a kind of resistor whose resistance depends on temperature changes, which is widely used in gardening, home alarm systems and other devices. Therefore, we can use the features to make a temperature instrument.

2.Components

| ![img](./media/wps40-169802322065862-1699415557958-236.png) | ![img](./media/wps41-169802322216363-1699415557958-237.jpg) | ![img](./media/wps42-169802322340364-1699415557958-238.jpg) | ![img](./media/wps43-169802322594765-1699415557958-239.jpg) |
| ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                     | Breadboard*1                                                | Thermistor*1                                                | 10KΩResistor*1                                              |
| ![img](./media/wps44-169802322789966-1699415557958-240.jpg) | ![img](./media/wps45-169802322953967-1699415557958-241.jpg) | ![img](./media/wps46-169802323129168-1699415557958-242.jpg) | ![img](./media/wps47-169802323264369-1699415557958-243.jpg) |
| M-F Dupont Wires                                            | LCD 128X32 DOT*1                                            | Jumper Wires                                                | USB Cable*1                                                 |


3.Component Knowledge

**Thermistor:** It is a temperature sensitive resistor. When it senses a change in temperature, the resistance of the thermistor will change. We can take advantage of this characteristic to detect temperature intensity. The thermistor and its electronic symbol are shown below:

![](./media/809b8634747fb295021f12e3b92b7894-1699415557958-244.png)

The relationship between resistance and temperature of the thermistor is：

![img](./media/wps3-1699424271347-24.png)

**Rt** is the thermistor resistance under T2 temperature;

**R** is the nominal resistance of thermistor under T1 temperature;

**EXP\[n\]** is nth power of e;

**B** is temperature index;

**T1, T2** is Kelvin temperature (absolute temperature). Kelvin temperature=273.15 + Celsius temperature.

**Parameters** : B=3950, R=10k, T1=25.

The circuit connection method of the thermistor is similar to the photoresistor, as shown below：

![](./media/b0f80e9bd350a8b7390a73756ac1ac8c-1699415557958-246.jpeg)

We can use the value measured by the ADC converter to obtain the resistance of thermistor, and then we can use the formula to obtain the temperature value.

Therefore, the temperature formula can be derived as:

![img](./media/wps4-1699424286177-26.png)

4.Read the value of the thermistor

First we will learn the thermistor reading the current ADC value, voltage value and temperature value and print them out. Please connect the wirings according to the wiring diagram below：

![](./media/806fd81bf8a761b4ae1a638489c426ce-1699415557958-248.png)

```c
//**********************************************************************************
/*  
 * Filename    : Thermomter
 * Description : Making a thermometer by thermistor.
 * Auther      : http//www.keyestudio.com
*/
#define PIN_ANALOG_IN   36
void setup() {
  Serial.begin(115200);
}

void loop() {
  int adcValue = analogRead(PIN_ANALOG_IN);                       //read ADC pin
  double voltage = (float)adcValue / 4095.0 * 3.3;                // calculate voltage
  double Rt = 10 * voltage / (3.3 - voltage);                     //calculate resistance value of thermistor
  double tempK = 1 / (1 / (273.15 + 25) + log(Rt / 10) / 3950.0); //calculate temperature (Kelvin)
  double tempC = tempK - 273.15;                                  //calculate temperature (Celsius)
  Serial.printf("ADC value : %d,\tVoltage : %.2fV, \tTemperature : %.2fC\n", adcValue, voltage, tempC);
  delay(1000);
}
//**********************************************************************************
```


Upload the code to the ESP32, power up with a USB cable, open serial monitor and set baud rate to 115200. Press the rest button of the ESP32 board,then you will view ADC value, voltage value and temperature value of the thermistor displayed.

Pinch the thermistor a while, the temperature value will increase.

![](./media/26637ed2225ebfea3b2562e6d7a46f92-1699415557958-249.png)

5.Wiring diagram of the temperature instrument

![](./media/5a437bfdcad012211e15cab54e35dad7-1699415557958-250.png)

6.Adding the lcd128\_32\_io library

Please add the **lcd128\_32\_io** library first：

![](./media/de6bddbc7cb9b94dad6c75d4be235dc3-1699415557958-251.png)

7.Test Code

```c
//**********************************************************************************
/*  
 * Filename    : Temperature Instrument
 * Description : LCD displays the temperature of thermistor.
 * Auther      : http//www.keyestudio.com
*/
#include "lcd128_32_io.h"

#define PIN_ANALOG_IN   36

lcd lcd(21, 22); //Create lCD128 *32 pin，sda->21， scl->22

void setup() {
  lcd.Init(); //initialize
  lcd.Clear();  //clear
}
char string[10];

void loop() {
  int adcValue = analogRead(PIN_ANALOG_IN);                       //read ADC pin
  double voltage = (float)adcValue / 4095.0 * 3.3;                // calculate voltage
  double Rt = 10 * voltage / (3.3 - voltage);                     //calculate resistance value of thermistor
  double tempK = 1 / (1 / (273.15 + 25) + log(Rt / 10) / 3950.0); //calculate temperature (Kelvin)
  double tempC = tempK - 273.15;                                  //calculate temperature (Celsius)
  lcd.Cursor(0,0); //Set display position
  lcd.Display("Voltage:"); //Setting the display
  lcd.Cursor(0,8);
  lcd.DisplayNum(voltage);
  lcd.Cursor(0,11);
  lcd.Display("V");
  lcd.Cursor(2,0); 
  lcd.Display("tempC:");
  lcd.Cursor(2,8);
  lcd.DisplayNum(tempC);
  lcd.Cursor(2,11);
  lcd.Display("C");
  delay(200);
}
//**********************************************************************************
```


8.Test Result

Compile and upload the code to ESP32, after the code is uploaded successfully, power up with a USB cable and you will see that the LCD 128X32 DOT displays the voltage value of the thermistor and the temperature value in the current environment.

## Project 22：Bluetooth

This chapter mainly introduces how to make simple data transmission through Bluetooth of ESP32 and mobile phones. Project 22.1 is classic Bluetooth while project 22.2 is Bluetooth control LED.

### Project 22.1：Classic Bluetooth

1.Components

| ![img](./media/wps1-16980213780351-1699415557952-1.png) | ![img](./media/wps2-16980213803472-1699415557952-2.jpg) |
| ------------------------------------------------------- | ------------------------------------------------------- |
| ESP32*1                                                 | USB Cable*1                                             |


In this tutorial we need to use a Bluetooth APP called serial Bluetooth terminal to assist in the experiment.

Download link: <https://www.appsapk.com/serial-bluetooth-terminal/> .

![](./media/7b98d6708888b0a6f38f85ffca484857-1699415557958-252.png)

2.Component Knowledge

Bluetooth is a short-distance communication system that can be divided into two types, namely low power bluetooth (BLE) and classic bluetooth. There are two modes for simple data transfer: master mode and slave mode. 

**Master Mode**: In this mode, work is done on the master device and can be connected to the slave device. When the device initiates a connection request in the main mode, information such as the address and pairing password of other bluetooth devices are required.  Once paired, you can connect directly to them.  

**Slave Mode**: A bluetooth module in the slave mode can only accept connection requests from the host, but cannot initiate connection requests. After being connected to a host device, it can send and receive data through the host device.

Bluetooth devices can interact with each other, when they interact, the bluetooth device in the main mode searches for nearby devices. While a connection is established, they can exchange data. For example, when a mobile phone exchanges data with ESP32, the mobile phone is usually in master mode and the ESP32 is in slave mode.  

![image-20231108115521293](./media/image-20231108115521293.png)

**Master Slave**

3.Wiring Diagram

We can use a USB cable to connect ESP32 mainboard to the USB port on the Raspberry P.

![image-20231108115532956](./media/image-20231108115532956.png)

4.Test Code

![](./media/ade63930bd851b560d26b36d1db272da-1699415557958-254.png)

```c
//**********************************************************************************
/*
 * Filename    : Classic Bluetooth--SerialToSerialBT
 * Description : ESP32 communicates with the phone by bluetooth and print phone's data via a serial port
 * Auther      : http//www.keyestudio.com
*/
#include "BluetoothSerial.h"

BluetoothSerial SerialBT;
String buffer;
void setup() {
  Serial.begin(115200);
  SerialBT.begin("ESP32test"); //Bluetooth device name
  Serial.println("\nThe device started, now you can pair it with bluetooth!");
}

void loop() {
  if (Serial.available()) {
    SerialBT.write(Serial.read());
  }
  if (SerialBT.available()) {
    Serial.write(SerialBT.read());
  }
  delay(20);
}
//**********************************************************************************
```


5.Test Result

Compile and upload the code to the ESP32. After uploading successfully，we will use a USB cable to power on. Open the serial
monitor and set the baud rate to **115200 then press the reset button first**. When you see the serial monitor prints out the character string as below, it indicates that the Bluetooth of ESP32 is ready and waiting for connection with a phone. (If open the serial monitor and set the baud rate to 115200, the information is not displayed, please press the RESET button of the ESP32)

![](./media/1fd21fafd84d2b529931a89d21a03d6a-1699415557958-255.png)

![](./media/c088057c588111809d08f36001501440-1699415557958-256.png)

Make sure that the Bluetooth of your phone has been turned on and “Serial Bluetooth Terminal”has been installed.

![](./media/382529edef3989e60264cad217d88e6f-1699415557958-257.png)

Click“Search”，search for the nearby Bluetooth and select to connect the“ESP32 test”.

![](./media/0608c9a78b5f56d4c8f1994c55c9cd46-1699415557958-258.png)

Turn on software APP, click the left of the terminal. Select "**Devices**" .

![](./media/32b8c3abd51fc538ba854b1d72e1165e-1699415557958-259.png)

Select ESP32test in classic Bluetooth mode, and a successful connecting prompt will appear as shown below.

![](./media/00f9b335cb512704763e3621e7c598b2-1699415557958-260.png)

Data can be transferred between your phone and the Raspberry Pi via ESP32 now.  

Send“Hello\!”, When the Raspberry Pi receives it, which will reply with "Hi\!".

![](./media/065e369f868e974242c4755088d01f21-1699415557958-261.png)

![](./media/4f4e6b4e45996ccbde4da17219f02d00-1699415557958-262.png)

### **Project 22.2：Bluetooth Control LED**

1.Components

| ![img](./media/wps50-1699415557958-263.png)                 | ![img](./media/wps51-169802337300371-1699415557958-264.jpg) |
| ----------------------------------------------------------- | ----------------------------------------------------------- |
| ESP32*1                                                     | Breadboard*1                                                |
| ![img](./media/wps52-169802338486772-1699415557958-265.jpg) | ![img](./media/wps53-169802338645173-1699415557958-266.jpg) |
| Red LED*1                                                   | 220ΩResistor*1                                              |
| ![img](./media/wps54-169802339350874-1699415557958-269.jpg) | ![img](./media/wps55-169802339513175-1699415557958-267.jpg) |
| Jumper Wires                                                | USB Cable*1                                                 |


2.Wiring Diagram

![](./media/0735997593c8858ad6441d8e9867206f-1699415557953-31.png)

3.Test Code

![](./media/635d68040ee1edbb20d26e2206bdcfd6-1699415557958-268.png)

```c
//**********************************************************************************
/*
 * Filename    : Bluetooth Control LED
 * Description : The phone controls esp32's led via bluetooth.
                When the phone sends "LED_on," ESP32's LED lights turn on.
                When the phone sends "LED_off," ESP32's LED lights turn off.
 * Auther      : http//www.keyestudio.com
*/
#include "BluetoothSerial.h"
#include "string.h"
#define LED 15
BluetoothSerial SerialBT;
char buffer[20];
static int count = 0;
void setup() {
  pinMode(LED, OUTPUT);
  SerialBT.begin("ESP32test"); //Bluetooth device name
  Serial.begin(115200);
  Serial.println("\nThe device started, now you can pair it with bluetooth!");
}

void loop() {
  while(SerialBT.available())
  {
    buffer[count] = SerialBT.read();
    count++;
  }
  if(count>0){
    Serial.print(buffer);
    if(strncmp(buffer,"led_on",6)==0){
      digitalWrite(LED,HIGH);
    }
    if(strncmp(buffer,"led_off",7)==0){
      digitalWrite(LED,LOW);
    }
    count=0;
    memset(buffer,0,20);
  }
}
//**********************************************************************************
```


4.Test Result

Compile and upload the code to the ESP32. The APP operation is the same as the project 22.1. To make the external LED on and off, simply change the sending content to "led\_on" and "led\_off". Moving the APP to send data:

![](./media/21ec63e3abe43a119ab8a3d4634894f0-1699415557958-270.png)

The serial monitor will display as follows:

![](./media/b761fcf1cf4cf8999f75de349c860a6a-1699415557958-271.png)

![](./media/a1e66d46e5797995a1b66a761c7857f8-1699415557958-272.png)

**Note:** If the "led-on 'or" led-off " is not sent, the status of the LED will not change. If the LED is on, it remains on when irrelevant
content is received; Conversely, if the LED is off, it continues to be off when irrelevant content is received.

## Project 23：WiFi Station Mode

1.Introduction

ESP32 has three different WiFi operating modes : Station mode，AP mode and AP+Station mode. All WiFi programming projects must be configured with WiFi operating mode before using, otherwise WiFi cannot be used. In this project, we are going to learn the WiFi Station mode of the ESP32.

2.Components

| ![img](./media/wps1-16980213780351-1699415557952-1.png) | ![img](./media/wps2-16980213803472-1699415557952-2.jpg) |
| ------------------------------------------------------- | ------------------------------------------------------- |
| ESP32*1                                                 | USB Cable*1                                             |


3.Wiring Diagram

Plug the ESP32 to the USB port of the Raspberry Pi

![image-20231108115553082](./media/image-20231108115553082.png)

4.Component Knowledge

**Station mode：**

When setting Station mode, the ESP32 is taken as a WiFi client. It can connect to the router network and communicate with other devices on the router via a WiFi connection. As shown in the figure below, the PC and the router have been connected. If the ESP32 wants to communicate with the PC, the PC and the router need to be connected.

![](./media/f74baff97695aa2ee33a8c19370d2547-1699415557958-273.png)

5.Test Code

![](./media/6bda6c04ff94e098ef86e4f8971fa76d-1699415557958-274.png)

Since WiFi names and passwords vary from place to place, thereby users need to enter the correct WiFi names and passwords in the box shown below before running the program code.  

![](./media/dfc5250143dbe04dce6c233faae7cc08-1699415557958-275.png)

```c
//**********************************************************************************
/*
 * Filename    : WiFi Station
 * Description : Connect to your router using ESP32
 * Auther      : http//www.keyestudio.com
*/
#include <WiFi.h> //Include the WiFi Library header file of ESP32.

//Enter correct router name and password.
const char *ssid_Router     = "ChinaNet-2.4G-0DF0"; //Enter the router name
const char *password_Router = "ChinaNet@233"; //Enter the router password

void setup(){
  Serial.begin(115200);
  delay(2000);
  Serial.println("Setup start");
  WiFi.begin(ssid_Router, password_Router);//Set ESP32 in Station mode and connect it to your router.
  Serial.println(String("Connecting to ")+ssid_Router);
//Check whether ESP32 has connected to router successfully every 0.5s.  
  while (WiFi.status() != WL_CONNECTED){
    delay(500);
    Serial.print(".");
  }
  Serial.println("\nConnected, IP address: ");
  Serial.println(WiFi.localIP());//Serial monitor prints out the IP address assigned to ESP32.
  Serial.println("Setup End");
}
 
void loop() {
}
//**********************************************************************************
```


![](./media/1fd21fafd84d2b529931a89d21a03d6a-1699415557958-255.png)

6.Test Result

After making sure the router name and password are entered correctly, compile and upload the code to ESP32, open serial monitor and set baud rate to 115200 then press the reset button first. When ESP32 successfully connects to“ssid\_Router”, serial monitor will print out the IP address, then monitor will display as follows: (If open the serial monitor and set the baud rate to 115200 and the information is not displayed, please press the RESET button of the ESP32).

![](./media/e62c5b5b07ccb71623430e4ab68071ad-1699415557959-276.png)

## Project 24：WiFi AP Mode

1.Introduction

In this project, we are going to learn the WiFi AP mode of the ESP32.

2.Components

| ![img](./media/wps1-16980213780351-1699415557952-1.png) | ![img](./media/wps2-16980213803472-1699415557952-2.jpg) |
| ------------------------------------------------------- | ------------------------------------------------------- |
| ESP32*1                                                 | USB Cable*1                                             |


3.Wiring Diagram

Plug the ESP32 mainboard to the USB port of the Raspberry Pi

![image-20231108115604784](./media/image-20231108115604784.png)

4.Component Knowledge

**AP Mode:**

When setting AP mode, a hotspot network will be created, waiting for other WiFi devices to connect. As shown below;

![](./media/35d90f1ce10814ea1897ba63f8bd7ad9-1699415557960-283.png)

5.Test Code

![](./media/02a41b24675ad837330d959a03ab9f9e-1699415557960-277.png)

Before running the code , you can make any changes to the ESP32 AP name and password in the box as shown below, but in a default circumstance, it doesn’t need to modify.

![](./media/9ad8a0e92c650dce6548b21aea71b803-1699415557960-279.png)

```c
//**********************************************************************************
/*
 * Filename    : WiFi AP
 * Description : Set ESP32 to open an access point
 * Auther      : http//www.keyestudio.com
*/
#include <WiFi.h> //Include the WiFi Library header file of ESP32.

const char *ssid_AP     = "ESP32_WiFi"; //Enter the router name
const char *password_AP = "12345678"; //Enter the router password

IPAddress local_IP(192,168,1,108);//Set the IP address of ESP32 itself
IPAddress gateway(192,168,1,1);   //Set the gateway of ESP32 itself
IPAddress subnet(255,255,255,0);  //Set the subnet mask for ESP32 itself

void setup(){
  Serial.begin(115200);
  delay(2000);
  Serial.println("Setting soft-AP configuration ... ");
  WiFi.disconnect();
  WiFi.mode(WIFI_AP);
  Serial.println(WiFi.softAPConfig(local_IP, gateway, subnet) ? "Ready" : "Failed!");
  Serial.println("Setting soft-AP ... ");
  boolean result = WiFi.softAP(ssid_AP, password_AP);
  if(result){
    Serial.println("Ready");
    Serial.println(String("Soft-AP IP address = ") + WiFi.softAPIP().toString());
    Serial.println(String("MAC address = ") + WiFi.softAPmacAddress().c_str());
  }else{
    Serial.println("Failed!");
  }
  Serial.println("Setup End");
}
 
void loop() {
}
//**********************************************************************************
```


6.Test Result

Enter the ESP32 AP name and password correctly, compile and upload the code to ESP32, open the serial monitor and set the baud rate to **115200 and press the reset button first**, then monitor will display as follows:

(If open the serial monitor and set the baud rate to 115200, the information is not displayed, please press the RESET button of the ESP32)

![](./media/1fd21fafd84d2b529931a89d21a03d6a-1699415557958-255.png)

![](./media/38d88043831a89fb66bdf71ae167e977-1699415557960-278.png)

When observing the printed information of the serial monitor, turn on the WiFi scanning function of the mobile phone, you can see the ssid\_AP on ESP32, which is dubbed "ESP32\_Wifi" in this code. You can connect to it either by typing the password "12345678" or by modifying the code to change its AP name and password.  

![](./media/3e0ad895bea7f5100cc02a415adcace7-1699415557960-280.png)

## Project 25：WiFi Station+AP Mode

1.Introduction

In this project, we are going to learn the AP+Station mode of the ESP32.

2.Components

| ![img](./media/wps1-16980213780351-1699415557952-1.png) | ![img](./media/wps2-16980213803472-1699415557952-2.jpg) |
| ------------------------------------------------------- | ------------------------------------------------------- |
| ESP32*1                                                 | USB Cable*1                                             |

3.Wiring Diagram

![image-20231108115653222](./media/image-20231108115653222.png)

Plug the ESP32 mainboard to the USB port of the Raspberry Pi

4.Component Knowledge

**AP+Station mode:**

In addition to the AP mode and the Station mode, **AP+Station mode** can be used at the same time. Turn on the Station mode of the ESP32, connect it to the router network, and it can communicate with the Internet through the router. Then turn on the AP mode to create a hotspot network. Other WiFi devices can be connected to the router network or the hotspot network to communicate with the ESP32.

5.Test Code

![](./media/bc271d152351970dff1543ebe49f4c11-1699415557960-281.png)

Before running the code, you need to modify the ssid\_Router, password\_Router、ssid\_AP and password\_AP, as shown in the box below:

![](./media/8c84b39a74430800ad2c76de09dc19ca-1699415557960-282.png)

```c
//**********************************************************************************
/*
 * Filename    : WiFi AP+Station
 * Description : ESP32 connects to the user's router, turning on an access point
 * Auther      : http//www.keyestudio.com
*/
#include <WiFi.h>
 
const char *ssid_Router     =  "ChinaNet-2.4G-0DF0";  //Enter the router name
const char *password_Router =  "ChinaNet@233";  //Enter the router password
const char *ssid_AP         =  "ESP32_WiFi"; //Enter the router name
const char *password_AP     =  "12345678";  //Enter the router password

void setup(){
  Serial.begin(115200);
  Serial.println("Setting soft-AP configuration ... ");
  WiFi.disconnect();
  WiFi.mode(WIFI_AP);
  Serial.println("Setting soft-AP ... ");
  boolean result = WiFi.softAP(ssid_AP, password_AP);
  if(result){
    Serial.println("Ready");
    Serial.println(String("Soft-AP IP address = ") + WiFi.softAPIP().toString());
    Serial.println(String("MAC address = ") + WiFi.softAPmacAddress().c_str());
  }else{
    Serial.println("Failed!");
  }
  
  Serial.println("\nSetting Station configuration ... ");
  WiFi.begin(ssid_Router, password_Router);
  Serial.println(String("Connecting to ")+ ssid_Router);
  while (WiFi.status() != WL_CONNECTED){
    delay(500);
    Serial.print(".");
  }
  Serial.println("\nConnected, IP address: ");
  Serial.println(WiFi.localIP());
  Serial.println("Setup End");
}

void loop() {
}
//**********************************************************************************
```


6.Test Result

Ensure that the code in the program has been modified correctly, compile and upload the code to the ESP32. After uploading successfully，we will use a USB cable to power on. Open the serial monitor and set the baud rate to 115200 and press the reset button, then monitor will display as follows: (If open the serial monitor and set the baud rate to 115200 and the information is not displayed, please press the RESET button of the ESP32)

![](./media/1fd21fafd84d2b529931a89d21a03d6a-1699415557958-255.png)

![](./media/38d88043831a89fb66bdf71ae167e977-1699415557960-278.png)

Open the WiFi scanning function of the mobile phone, you can see the ssid\_AP.

![](./media/3e0ad895bea7f5100cc02a415adcace7-1699415557960-280.png)

