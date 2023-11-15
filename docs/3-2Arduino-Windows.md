# Arduino Windows

Development Environment Configuration

Click on the link to enter the development environment setup tutorial：[Development Environment Configuration-Windows](3-2Arduino-Windows.md)

**Windows System：**

![](./media/6cf6312dc7c7db27794b54d58a8bf80c-1699411453251-577.png)

## 1.Download and install Arduino software：

（1）First, enter arduino's official website: [<span class="underline">https://www.arduino.cc/</span>](https://www.arduino.cc/) , and click “SOFTWARE”to enter the download page. As shown in the figure below：

![](./media/bfe8c9e405c71123dee7921eddff86d3-1699411453251-578.png)

![](./media/7250961db41ba42e4b881d77bd76a319-1699411453251-580.png)

(2) Then, select and download the corresponding installer for your operating system. If you are a Windows user, please select “Windows Installer” to download to install the driver correctly.

![](./media/894116c5cf0023dd9720946cfb441790-1699411453251-579.png)

Choose to click the **Windows Win7 and newer** to download Arduino 1.8.16 version installer, which requires manual installation. But when click the **Windows ZIP File**, the Arduino 1.8.16 zip file will be downloaded directly, just unzip it to complete the installation.

![](./media/a983a2f2eceb968afbff8ba0f0376240-1699411453251-583.png)

In general, you can click **JUST DOWNLOAD** to download it.

(3) After the Arduino IDE is downloaded, continue the installation. When you receive the warning from the operating system, please allow the driver installation by clicking **I Agree** first, and then click **Next** after selecting the components to install.

![](./media/00e334d3c756a2495da6f0d1b2db680a-1699411453251-581.png)

![](./media/de541d90a1cda992ad8e3f0cbaf95f94-1699411453251-584.png)

（4）Select the installation directory (we recommend keeping the default directory), and then click **Install**.

![](./media/7da9aca1e8432c59372e7c7ab2574bd9-1699411453251-582.png)

（5）Select Install if the following screen appears.

![](./media/85b29de2aa791ecc77280ccde91e53c5-1699411453251-585.png)

This process extracts and installs all the necessary files to properly execute the Arduino software (IDE).

![](./media/739c41701fbcab202f0e587f534bad30-1699411453251-586.png)

After installation is complete, an Arduino Software shortcut will be generated in the desktop.

![](./media/d28223c55a30f949760779720fe4ec24-1699411453251-587.png)

## 2.Install a driver on Windows：

（Note：If you have installed the driver, just skip it）

Before using the ESP32 board, you must install a driver, otherwise it can not communicate with the computer. Unlike the USB series chip (ATMEGA8U2) of the Arduino UNO R3, the ESP32 board is used the CP2102 chip USB series chip and USB type C interface.

The driver of the CP2102 chip is included in 1.8.0 version and newer version of Arduino IDE. Usually, you connect the board to the computer and wait for Windows to begin its driver installation process. After a few moments, the process will succeed.

**Note:**

1\. Please make sure that your IDE is updated to 1.8.0 or newer version

2\. If the version of Arduino IDE you download is below 1.8, you should download the driver of CP2102 and install it manually.

Link to download the driver of CP2102: [CP2102-Driver-File-Windows](CP2102-Driver-File-Windows.zip)

If the driver installation process fail, you need to install the driver manually. Open device Manager for your computer and right-click“the computer”→click“Properties”→Click“Device Manager”. Look under Ports (COM & LPT) or other device, a yellow exclamation mark means that the CP2102 driver installation failed.

![](./media/9af2e34bf9bdd6675bdf5fa8cd291971-1699411453251-588.png)

It shows that the driver for CP2102 fails to be installed successfully if there is a yellow mark. Double-click![](./media/a2455b26773cb8d6cb3fccc605ea4dd7-1699411453251-589.png), and then click “**Update drive...**” to update the driver.

![](./media/a122cd6fef74eb5c0c7fe16fac2fed59-1699411453251-590.png)

Click “**Browse my computer for drivers**”to find the Arduino software we installed or downloaded.

![](./media/a02d3e643231cfe267d4debf0ef258c4-1699411453251-591.png)

There is a **drivers** folder in Arduino software installed package（![](./media/aae89b3213589edf1c320d5502489820-1699411453251-592.png)), open the driver folder and you can see the driver of CP210X series chips.

Click“**Browse...**”, then find the drivers folder, or you could enter“driver”to search in rectangular box, then click“**Next**”,

![](./media/eb6ca318005b5c570ad4fbef73024351-1699411453251-593.png)

After a while, the driver is installed successfully.

![](./media/4f2af46602a5ef73985914170911c519-1699411453251-594.png)

Open the computer device Manager again, you can see that the CP2102 driver has been successfully installed, and find the yellow exclamation mark disappear.

![](./media/af2324b73308f1796b8b7c9dc14878e7-1699411453251-595.png)

## 3\. Install the ESP32 on Arduino IDE：

The installation process for ESP32 is almost the same as that for ESP8266. If you are to install ESP32 on an Arduino IDE, follow these steps：

Note：you need to download Arduino IDE 1.8.5 or advanced version to install the ESP32.

1)   Click the icon![](./media/4f2de68a91c7f59024aa87a522e36ab3-1699411453251-596.png)to open the Arduino IDE。

![](./media/8aca9b5378e794375f2c15d3b4e238ba-1699411453251-597.png)

（2）Click“**File**” →**“Preferences”**，copy the website address：<https://dl.espressif.com/dl/package_esp32_index.json> in the“**Additional Boards Manager URLs:**”，and then click“**OK**” to save the address.

![](./media/a8febbd62268514a30cec4e183b1eaed-1699411453251-598.png)

![](./media/ea68c66041f48b44b4682eb3a0e11e79-1699411453251-599.png)

（3）First click “**Tools**”→“**Board:**”，and click “**Boards Manager...**”to enter“**Boards Manager**”, enter“**ESP32**”in the boxafter“**ALL**”, then select the latest version to install, the installation package is not large, click“**Install**”to Install the plug-in, as shown in the figure below.

![](./media/a710d2a8166e3e62d9b48d9b7386e9e4-1699411453251-600.png)

![](./media/9824059733dcbbfb3dff58736923a4a9-1699411453251-601.png)

4.  After successful installation, click“**Close**”to Close the page。

## 4\. Arduino IDE Setting:

（1）Click the icon![](./media/4f2de68a91c7f59024aa87a522e36ab3-1699411453251-596.png) to open the Arduino IDE.

![](./media/8aca9b5378e794375f2c15d3b4e238ba-1699411453251-597.png)

（2）When downloading the code to the board, you must select the correct name of Arduino board that matches the board connected to your computer, then click“**Tools**”→“**Board:**”. As shown below ;

(Note: we use the ESP32 board in this tutorial; therefore, we select ESP32 Arduino**)**

![](./media/78695faae974868fb29c972e89a9d917-1699411453251-602.png)

![](./media/3a3bbc0ce1845aceb35af40aea7c84ca-1699411453251-605.png)

Set the board type as follows:

![](./media/43b6c4d7f639f1e4b7adb017db805ea1-1699411453251-603.png)

Then select the correct COM port (the corresponding COM port can be seen after the driver is installed successfully).

![](./media/94587092f31929ebb9cdbcc5fe1718de-1699411453251-604.png)

![](./media/97ab2e53b87bd0812b2b064405f86196-1699411453251-606.png)

Before a code was uploaded to the ESP32 mainboard, we have to demonstrate the functionality of each symbol that appeared in the Arduino IDE toolbar.

![](./media/1235ef274c17d00db74fca324072ff84-1699411453252-607.png)

A- Used to verify whether there is any compiling mistakes or not.

B- Used to upload the sketch to your Arduino board.

C- Used to create shortcut window of a new sketch.

D- Used to directly open an example sketch.

E- Used to save the sketch.

F- Used to send the serial data received from board to the serial
monitor.
