# Arduino MacOS

## Development Environment Configuration--Mac OS

![](./media/a6fc83596009c574d8e29ef383748549.png)


Click on the link to enter the development environment setup tutorial：[Development Environment Configuration-MacOS](3-1Arduino-MacOS.md)


## **1. Download Arduino IDE:**

![](./media/5d58d3cf67b308423ddb9f286f6cb697.png)

## **2.How to install the CP2102 driver：**

(Note: If you haven’t installed the driver installed, please do the following.) 

(1) Connect the ESP32 motherboard to your MacOS computer using a USB cable and open the Arduino IDE. 

![image-20231108104251634](./media/image-20231108104251634.png)

Click **Tools→Board: ESP32 Dev Module** and **/dev/cu.usbserial-0001.**

![](./media/00d823dbf27e569a2ba23277b1e15a41.jpeg)

Click![](./media/9c9158a5d49baa740ea2f0048f655017.png)to upload the test code

Note: If the the upload fails, follow the steps below to install the CP2102 driver.  Perform step (2) to (16). 

（2）Download link for CP2102：[CP2102-Driver-File-MAC.zip](CP2102-Driver-File-MAC.zip)

（3）Download MacOS version

![](./media/c09e7c279a858574756d1192b3a995aa-1699415955708-1013.png)

（4）Unzip the downloaded package

![](./media/6870a714ddd11015dc43b1d5743e0666-1699415955708-1014.jpeg)

（5）Open the folder and double-click“SiLabsUSBDriverDisk.dmg”file

![](./media/61ae3e706a1c4afa7948d5fb2e797a6d-1699415955708-1015.png)

Then you can see the following file

![](./media/3f1afe9499f6d852492cfb9d6b11e9ab-1699415955708-1016.jpeg)

Double-click**“Install CP210x VCP Driver”，tap**“**Don’t warn me when opening application on this disk image**”and click“**Open**”

![](./media/14f6ebb088e654abc2f0149645e34ed1-1699415955708-1017.png)

（7）Click“**Continue**”

![](./media/b1cb125dccf6470ebe255f8f65b902eb-1699415955708-1018.jpeg)

（8）Click“**Agree**”，then tap“**Continue**”

![](./media/865dcc76cb7f58854b56f1020233f05e-1699415955708-1019.jpeg)

（9）Click“**Continue**”，then input your user password

![](./media/1ef6d65b61ad7c6e0a3989ba59de74d5-1699415955708-1020.jpeg)

![](./media/29bbca3360d806164717733460574356-1699415955708-1021.png)

10. Select“**Select Open Security Preferences**”

![](./media/ca6bc6e536202f07a53c09201a0996ff-1699415955708-1023.png)

（11）Click on security lock and enter your user password to authorize.

![](./media/cb6be428257143635fc4f729487549c5-1699415955708-1022.jpeg)

![](./media/e8f637a3a9510aa8f90c65820d4d1cd8-1699415955708-1024.jpeg)

11) When you see that the lock is opened, click "Allow".

![](./media/250a1cbb7f93fc2a572944bea9fe5494-1699415955708-1025.jpeg)

Return to the installation interface and wait for the installation as prompted.

![](./media/0da6d0d4296d6e3de0b30dfd3c615265-1699415955708-1026.jpeg)

（14）The installation is successful

![](./media/7cca827fe946096f228797dadce10661-1699415955708-1027.jpeg)

（15）Open arduinoIDE，click“**Tools**”and tap“**ESP32 Dev Module**” and“**/dev/cu.usbserial-0001**”.

![](./media/00d823dbf27e569a2ba23277b1e15a41.jpeg)

（16）Click![](./media/9c9158a5d49baa740ea2f0048f655017.png)to upload the program, and you can see the program burned successfully