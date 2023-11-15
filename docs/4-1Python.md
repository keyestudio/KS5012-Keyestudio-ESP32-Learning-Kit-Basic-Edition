# Python

1.Install Thonny：

Thonny is a free and open source software platform with small size, simple interface, simple operation and rich functions. It is a Python IDE suitable for beginners. In this tutorial, we use this IDE to develop a ESP32. Thonny supports multiple operating systems including Windows, Mac OS, Linux.

2.Download Thonny：

1)  Enter the website：[<span class="underline">https://thonny.org</span>](https://thonny.org) to download the latest version of Thonny.

(2)Thonny open-source code library：[<span class="underline">https://github.com/thonny/thonny</span>](https://github.com/thonny/thonny).

<table border="1">
<tbody>
<tr class="odd">
<td>System</td>
<td>Download link</td>
</tr>
<tr class="even">
<td>MAC OS：</td>
<td><a href="https://github.com/thonny/thonny/releases/download/v3.2.7/thonny-3.2.7.pkg">https://github.com/thonny/thonny/releases/download/v3.2.7/thonny-3.2.7.pkg</a></td>
</tr>
<tr class="odd">
<td>Windows：</td>
<td><a href=" https:/github.com/thonny/thonny/releases/download/v3.2.7/thonny-3.2.7.exe">https://github.com/thonny/thonny/releases/download/v3.2.7/thonny-3.2.7.exe</a></td>
</tr>
<tr class="even">
<td>Linux：</td>
<td><p>Latest version:</p>
<p><strong>Binary bundle for PC (Thonny+Python):</strong></p>
<p>bash &lt;(wget -O - https://thonny.org/installer-for-linux)</p>
<p><strong>With pip:</strong></p>
<p>pip3 install thonny</p>
<p><strong>Distro packages (may not be the latest version):</strong></p>
<p><strong>Debian, Rasbian, Ubuntu, Mint and others:</strong></p>
<p>sudo apt install thonny</p>
<p><strong>Fedora:</strong></p>
<p>sudo dnf install thonny</p></td>
</tr>
</tbody>
</table>

![](./media/bd5823ede2c01d1fa4696438c62aec51-1699415955707-985.png)


1. The downloaded Thonny icon is as follow:

![](./media/d3caa98d406fa06a124d5c98195b90db-1699415955707-986.png)

2.Double-click“thonny-3.3.13.exe”and select install mode. You can choose ![](./media/37be3f3bcc9aa0eb48c8b844eb46a71c-1699415955707-987.png)

![](./media/4c044b255da8b14fe674eb9cce01627d-1699415955707-988.png)

3.You can also keep selecting **Next** to finish the installation.

![](./media/995b36640124b6a9b23f10473ff8a38a-1699415955708-989.png)

![](./media/8bcc17840b9fc15d76f79fee8a0168ee-1699415955708-990.png)

4.If you want to change the route of installing Thonny，just click“**Browse...**”to select a new route and click **OK**.

![](./media/df6f63b42ebb1676b22c26b25dc9c7aa-1699415955708-991.png)

![](./media/f5cd6d619b4645601c5b098ffdbec12a-1699415955708-992.png)

5.Click **Create desktop icon,** you will view Thonny on your desktop.

![](./media/a30c89dde3de81ad00aced30510071be-1699415955708-993.png)

6.Click“**Install**”

![](./media/6ace65142291e5e8af5f81e4a6b2f180-1699415955708-994.png)

7.Wait for a while but don’t click **Cancel

![](./media/a504b3a3ab16b4d91040cd5878acea0c-1699415955708-995.png)

G. Click**“Finish”**

![](./media/a1fb6027e54a975de1c0aa1e1a0d6a29-1699415955708-996.png)

![](./media/80f35044d91d66f734e36059db35f273-1699415955708-997.png)


2.Basic Setting：

Double-click Thonny, choose language and initial settings and click **Let’s go！**

![](./media/ee240978a4f844184f1ea9f5a21d0395-1699415955708-998.png)

![](./media/619a856895d95e00beed748b1438072d-1699415955708-999.png)

![](./media/bcf6c31e4f69c904a7a0c0e9df7e8d7d-1699415955708-1000.png)

Click“**View**”→“**File**”and“**Shell**”

![](./media/5ff5c305585dbe7e832cc41183db5818-1699415955708-1001.png)

![](./media/d41b79772c9846fd8bf295c8451f8321-1699415955708-1002.png)

![](./media/3d04fe6893ca104e4e593a0786cb3799-1699415955708-1003.png)

**Install the CP2102 driver：**

Before using the Thonny, we need to install the CP2102 driver in the computer.

**Windows system**

Check if the CP2102 driver has been installed

1. Interface the ESP32 with your PC with a USB cable

![image-20231108104620668](./media/image-20231108104620668-1699415955708-1004.png)

2. Click“This PC”and right-click Manage”

![](./media/84bc1f7d3169cad24b23d2ac620bc111-1699415955708-1005.png)

3.Click“Device Manager”, if the CP2102 driver has been installed，Silicon Labs CP210x USB to UART Bridge(COMx) will be
shown.

![](./media/a320816d8aed54304018d8380b5b6b3d-1699415955708-1006.png)

If the CP2102 has not been installed

![](./media/776adb879fe6e299e3610cc92cfaf70b-1699415955708-1007.png)

Click“CP2102USB to UART Bridge Controller”and Update driver”.

![](./media/7b342fbd38b03cba4dfce2045f4fe17b-1699415955708-1008.png)

Click“Browse my computer for drivers ”.

![](./media/1cb9eaea189e4766d17a0a5977c23a74-1699415955708-1009.png)

Click Browse... to choose CP210x\_6.7.4 (“4. Python Tutorial\\1.Development Environment Configuration\\CP2102 Driver File-Windows”) and click Next

![](./media/b1995fce2ccc024f32a9b9b83cbc28a6-1699415955708-1010.png)

The CP2102 driver will be installed

![](./media/b99fbcb61c133392d1b94b65f51fc2c7-1699415955708-1012.png)

![](./media/da0dffd89b5f385612c3230422ee732f-1699415955708-1011.png)

**MAC System**

Download link for CP2102：[CP2102-Driver-File-MAC.zip](CP2102-Driver-File-MAC.zip)

Download MacOS version

![](./media/c09e7c279a858574756d1192b3a995aa-1699415955708-1013.png)

Unzip the downloaded package

![](./media/6870a714ddd11015dc43b1d5743e0666-1699415955708-1014.jpeg)

Open the folder and double-click“SiLabsUSBDriverDisk.dmg”file

![](./media/61ae3e706a1c4afa7948d5fb2e797a6d-1699415955708-1015.png)

Then you can see the following file

![](./media/3f1afe9499f6d852492cfb9d6b11e9ab-1699415955708-1016.jpeg)

Double-click**“Install CP210x VCP Driver”，tap**“**Don’t warn me when
opening application on this disk image**”and click“**Open**”

![](./media/14f6ebb088e654abc2f0149645e34ed1-1699415955708-1017.png)

Click“**Continue**”

![](./media/b1cb125dccf6470ebe255f8f65b902eb-1699415955708-1018.jpeg)

Click“**Agree**”，then tap“**Continue**”

![](./media/865dcc76cb7f58854b56f1020233f05e-1699415955708-1019.jpeg)

Click“**Continue**”，then input your user password

![](./media/1ef6d65b61ad7c6e0a3989ba59de74d5-1699415955708-1020.jpeg)

![](./media/29bbca3360d806164717733460574356-1699415955708-1021.png)

Select“**Select Open Security Preferences**”

![](./media/ca6bc6e536202f07a53c09201a0996ff-1699415955708-1023.png)

Click on security lock and enter your user password to
authorize.

![](./media/cb6be428257143635fc4f729487549c5-1699415955708-1022.jpeg)

![](./media/e8f637a3a9510aa8f90c65820d4d1cd8-1699415955708-1024.jpeg)

When you see that the lock is opened, click "Allow".

![](./media/250a1cbb7f93fc2a572944bea9fe5494-1699415955708-1025.jpeg)

Return to the installation interface and wait for the installation as prompted.

![](./media/0da6d0d4296d6e3de0b30dfd3c615265-1699415955708-1026.jpeg)

The installation is successful

![](./media/7cca827fe946096f228797dadce10661-1699415955708-1027.jpeg)



**3.Burn Micropython firmware**

To run a Python program on the ESP32 board, we need to burn the firmware to the ESP32 board first.

Download Micropython firmware

microPython website：<http://micropython.org/>

ESP32 firmware：[<span class="underline">https://micropython.org/download/esp32/</span>](https://micropython.org/download/esp32/)

![](./media/c706d3cd6862323dcfccfd11ec7d1da3-1699415955708-1028.png)

The firmware we use：**esp32-20210902-v1.17.bin

Firmware：[Download Python Firmware](Python-Firmware.zip)

Burn the Micropython firmware

Connect the ESP32 to your PC with a USB cable

![image-20231108104717650](./media/image-20231108104717650-1699415955708-1029.png)



Make sure the driver has been installed successfully and the COM port can be identified correctly. Open Device Manager and  expand “Ports”.

![](./media/d154c68ab7e252cf013b374069a2c6c0-1699415955708-1030.png)

Open Thonny，click“run”and“Select interpreter...”

![](./media/bda2bfc9d4576aef0b63e1f6373bf5a7-1699415955708-1031.png)

Select Micropython (ESP32) and Silicon Labs CP210x USB to UART Bridge(COM3) and click “Install or update firmware”.

![](./media/adfa634e977c803db209b18418f1df76-1699415955708-1041.png)

Select“Silicon Labs CP210x USB to UART Bridge(COM3)”，click “ Browse...”and choose the firmware **esp32-20210902-v1.17.bin.**
Check“Erase flash before installing”and“Flash mode”，then click“Install”.

If you haven't downloaded the firmware, please click on the link to download：[Download Python Firmware](Python-Firmware.zip)

（(Note：If you fail to install the firmware，press the Boot button on the ESP32 board and click“Install”）

![](./media/8b746aeb78c731ab638141c8c197437b-1699415955708-1032.png)

![](./media/6e13c0f08fdbf4586295c6c224f38b91-1699415955708-1033.png)

![](./media/055d392fe9a633564b3608128c7fd0a7-1699415955708-1034.png)

Then click Close and OK

![](./media/f706c7f121e659e206fd9727665f1af2-1699415955708-1035.png)

![](./media/5ff623e84c9a432edeb9534fe563f172-1699415955708-1036.png)

![](./media/7fc6ac0c25d55775ef60449f497c6f2f-1699415955708-1037.png)

Turn off all windows and turn to the main page and click ![](./media/a807dd85c760f2bda89025b9fd70156e-1699415955708-1038.png)“STOP.

![](./media/e9d1c2d43c22cf13ada2bdf4808aacb9-1699415955708-1039.png)

**Test Code**

Test the Shell commander

Input print('hello world') in the“Shell”and press **Enter**

![](./media/0dd4176ed13f85a7c96c14b4e20e6166-1699415955709-1047.png)

**Run the test code(online)**

Connect the ESP32 to your PC. Users can program and debug programs with Thonny.

Open Thonny and click Open.

If you haven't downloaded the code file yet, please click on the link to download it:[Download Python Codes](Python-Codes.zip)

![](./media/7fded176b193d1ac598571f7d16599f7-1699415955708-1040.png)

When a new window pops up, click“This computer”

![](./media/101bf94e8e29ce5bc4a948f15b5dbe51-1699415955708-1042.png)

Select the file“Project\_01\_HelloWorld.py”

![](./media/06cec75374d1818e56341ef87a090411-1699415955708-1043.png)

Click ![](./media/31511be865975be04b53f27aa45c60a7-1699415955708-1044.png),“Hello World”will be printed in the“Shell”monitor.

![](./media/95686a34ef893fbad426628f8eedbdc6-1699415955709-1045.png)

Note: Press the reset button to reboot

**Run the test code(offline)**

After rebooting the ESP32, run the boot.py file under the root directory first then run your code file.

So, we need to add a guide program to run the code of users.

Move the file“4. Python Tutorial\\2. Python Projects” to the disk(D)，the route is“D:/2. Python Projects”, then open the “Thonny”.

![](./media/000a950d20ba8d5cb478cbeb33dd238c-1699415955709-1046.png)

Click project 00. Boot.Boot and double-click boot.py, then the code under MicroPython device can run offline.

![](./media/da4d70e3edebeaba6bb5fa6247a777b9-1699415955709-1048.png)

If you want to run the code offline, you nee to upload boot.py and program code to MicroPython device, then press the ESP32’s reset button. We will take the project 00 and project 01 as an example. Select boot.py and right-click Upload to /.

![](./media/4322dafa440f20bea8bca8b5f0437b17-1699415955709-1049.png)

Similarly, upload the project\_01\_Helloworld. py file to the "MicroPython Device". 

![](./media/5734425738777d7a79a7e0abc4d65106-1699415955709-1050.png)

Press the Reset button, you will view code running in the Shell monitor

![](./media/40e0e288b6b228b8a906054d8b602869-1699415955709-1051.png)

Upload the code to the ESP32

We take the boot.py as an example. If we add a boot.py in each code directory, reboot the ESP32, the boot.py will run first.

![](./media/2a33e5afa8793c96d69255afb9067f15-1699415955709-1052.png)

Select “boot.py”in the file Project 03：LED Flashing, right-click to select“Upload to /”. Then the code will be uploaded to the root
directory of the ESP32 and click OK.

![](./media/f3bca24026e4beda4f05ccd89cbeea14-1699415955709-1053.png)

![](./media/14a519166b9f9e7b3420812fb4295210-1699415955709-1054.png)

Download the code to your PC:

MicroPython device\<boot.py, then right-click Download to…

![](./media/cf9de37f4565f94e386542c777403dc3-1699415955709-1055.png)

Delete files of the ESP32

For example, click“boot.py”in the MicroPython device and right-click Delete.

![](./media/70e75f7f9f40b454dd3a3b580b736b2f-1699415955709-1056.png)

Select boot.py in the Project 03：LED Flashing folder, right-click Move to Recycle Bin to delete it.

![](./media/646bb65f65361eb2c70b4abf40fc74ea-1699415955709-1057.png)

Create and save code

Click“File”→“New”to create and edit code.

![](./media/1d71df4720f9455dcaf17a72ec38bb1b-1699415955709-1058.png)

Enter the code in the new file. We take the Project\_03\_LED\_Flashing.py as an example.

![](./media/e80d2f6ce955d013a708fd7134d6e64a-1699415955709-1059.png)

Click ![](./media/40348c4ef49beb5e90593df6050c1d62-1699415955709-1060.png) to save the code to your PC or the ESP32.

![](./media/0f184894cef3d5d00a216dc2161d05d0-1699415955709-1061.png)

Select MicroPython device and enter main.py in the new page and click OK.

![](./media/895a782664e10406ce2ab9ba18507d19-1699415955709-1062.png)

Then the code will be uploaded to the ESP32.

![](./media/cec982987cf6b8cc24d5830e7777ac63-1699415955709-1063.png)

Disconnect the USB cable and connect it, you can see the effect of the LED flashing continuously in the circuit on a cycle.  

![](./media/2dcc6a55b77b4175b5175f717eb196c3-1699415955709-1064.png)

