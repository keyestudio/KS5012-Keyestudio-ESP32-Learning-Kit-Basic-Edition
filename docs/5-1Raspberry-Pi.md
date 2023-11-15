# Raspberry Pi

Raspberry Pi is a card computer whose official system is Raspberry Pi OS, which can be installed on other systems,, such as: ubuntu, Windows IoT. Raspberry Pi can be used as a personal server, a router camera monitoring and recognition, as well as voice interaction by connecting a camera and a voice interactive assistant.

Furthermore, Raspberry Pi leads out 40Pin pins that can be connected to various sensors and control LEDs, motors, etc, making it can be used to create a robot.

## Install the Raspberry Pi OS System：

### 1\. Tools needed for the Raspberry Pi system：

#### 1.1. Hardware Tool：

（1）Raspberry Pi 4B/3B/2B 

（2）Above 16G TFT Memory Card

（3）Card Reader 

（4）Computer and other parts

#### 1.2. Software tools that need to be installed：

**Windows System：**

**（1）Install putty**

Download link：[<span class="underline">https://www.chiark.greenend.org.uk/\~sgtatham/putty/</span>](https://www.chiark.greenend.org.uk/~sgtatham/putty/)

![](./media/c26be4cd1f5543f20f275556ce5892c0-1699357112065-3.png)

![](./media/d888918aa7bf9e5ea94597aad1ee4224-1699357112065-4.png)

After downloading the package file ![](./media/e597704d7033c7c3c5da06d4f561822c-1699357112065-5.png), double-click it and tap“Next”.

![](./media/01f1b2d98915be2be9c0c2a3d330dde2-1699357112065-6.png)

Click “Next”.

![](./media/bd698753a8eea7a2ff5c5e0e598cbd94-1699357112065-7.png)

Select “Install Putty files”, and click “Install”

![](./media/071a0acc98bb2dc5cd45d85dec72d111-1699357112065-8.png)

After a few seconds, the installation is complete, click "Finish".

![](./media/ec368c3a549c09edd70f9786456d5430-1699357112065-9.png)

**Remote Login software -WinSCP**

Download link: [<span class="underline">https://winscp.net/eng/download.php</span>](https://winscp.net/eng/download.php)

After downloading the WinSCP software file![](./media/1719daa1002d7477ad4700e1df85d2df-1699357112066-10.png), double-click it then click![](./media/e09e48a32781d08aabb06156efe1de49-1699357112066-11.png).

![](./media/5ee80ade909fe3eb73dc9535704b4c0b-1699357112066-12.png)

Click“Accept”，then select the appropriate option and click“Next”, then click“Install”.

![](./media/9c652f54f6a7d53f6b2aedba40104a00-1699357112066-13.png)

![](./media/f32891714d5966037d59d1812aa15686-1699357112066-14.png)

![](./media/57d6139ba0aac9ca996bcbe6f6fd218f-1699357112066-15.png)

![](./media/49ffed878ee84546b156af3a0bf5556e-1699357112066-16.png)

After a few seconds, the installation is complete, click "Finish".

![](./media/14ffa1e11243835d30ffb933219dcef5-1699357112066-17.png)

**Format TFT card tool-- SD Card Formatter**

Download link：

[<span class="underline">http://www.canadiancontent.net/tech/download/SD\_Card\_Formatter.html</span>](http://www.canadiancontent.net/tech/download/SD_Card_Formatter.html)

![](./media/fa229f4e063572ce1c59574c308bf452-1699357112066-18.png)

![](./media/ac5d5eb9463805484b9239b99faf04eb-1699357112066-19.png)

Unzip the SDCardFormatterv5\_WinEN package and double-click the SD Card Formatter file![](./media/8c6f8da97bf702080a8e302db2e9f982-1699357112066-20.png) to run it.

![](./media/046c67e4072093ee3dad27e8088fcf9f-1699357112066-21.png)

Click “Next”，select “![](./media/13dc08ae2b5cb52ae3d7ea198134d778-1699357112066-22.png)” and click “Next”.

![](./media/384203e0b54ddfe37f18b65f70e786e5-1699357112066-23.png)

![](./media/cf4e91eac0c0573cff282256a915a01a-1699357112066-24.png)

Click “Next” again, and then click “Install”.

![](./media/0af58ee3afb14005a884ca2dc941157f-1699357112066-25.png)

![](./media/807623ddeea20c8b61503845d8aec9bc-1699357112066-26.png)

After a few seconds, the installation is complete, click "Finish".

![](./media/df2deb7e04c25ee207e994f0d2808194-1699357112066-27.png)

**（4）Burn mirror system software tool--- Win32DiskImager**

Download link：[<span class="underline">https://sourceforge.net/projects/win32diskimager/</span>](https://sourceforge.net/projects/win32diskimager/)

![](./media/4ffb55fd466198ca9524afbde7806271-1699357112066-28.png)

After downloading the software file![](./media/63c3eaf215c92c325f95613c9d8d49ce-1699357112066-29.png)，double-click it and then click “Run”.

![](./media/0f86f055a814207b0b09e1a7e6cb20bc-1699357112066-30.png)

After selecting![](./media/5cdab33a0a7ddd4ab5b2ca8cb04670be-1699357112066-31.png)，and click “Next”.

![](./media/d70ecd0554cbdbd60997a2356b55dc0d-1699357112067-32.png)

Click “Browse...”，select the location where Win32DiskImager is installed and click “Next”.

![](./media/1cdc2638bc1e9fe214344429f5e97a13-1699357112067-33.png)

1.  Click “Browse...”，select the location where Win32DiskImager is installed and click“Next”.

![](./media/cc7949bb335b75000e77b18c85e4e07b-1699357112067-34.png)

2.  > Select![](./media/99d088dd3f9e62d94fe8d56bd4638d1d-1699357112067-35.png)and click“Next”，and then click“Install”.

![](./media/c03510a9961a0e7307945dff10de3550-1699357112067-36.png)

![](./media/0c9c0d647479ee984fc29c3cedc72c79-1699357112067-37.png)

d. After a few seconds, the installation is complete, click "Finish".

![](./media/1d75c6dd9ea4a2c437a2b655b713a1db-1699357112067-38.png)

（5）Scan for IP address software tool---WNetWatcher

Download Link：http://www.nirsoft.net/utils/wnetwatcher.zip

#### 1.3. Raspberry PI mirror system

Download link for the latest version：

[<span class="underline">https://www.raspberrypi.org/downloads/raspberry-pi-os/</span>](https://www.raspberrypi.org/downloads/raspberry-pi-os/)

Download link for the old version：

- > Raspbian：

- > <span class="underline">https://downloads.raspberrypi.org/raspbian/images/</span>

- > Raspbian full：

- > <span class="underline">https://downloads.raspberrypi.org/raspbian\_full/images/</span>

- > Raspbian lite：

- > https://downloads.raspberrypi.org/raspbian\_lite/images/

We use the 2020.05.28 version in the tutorial and recommend you to use this version(Please download this version as shown in the picture below.)

<https://downloads.raspberrypi.org/raspios_full_armhf/images/raspios_full_armhf-2021-05-28/>

![](./media/857946c171dd1f5617a0cbbdd2608baf-1699357112067-39.png)

### 2\. Install Raspberry Pi OS system on Raspberry Pi 4B:

**2.1.Connect the TFT memory card to a card reader, then plug the card reader into a computer’s USB port.**

**2.2.Use the SD Card Formatter to format a TFT memory card, as illustrated below：**

![](./media/79d747e6f00f857a593b3327397cc44f-1699357112067-40.png)

![](./media/cbc55902de71ce984d873ca2cb67fffa-1699357112067-41.png)

![](./media/82031b5354cc4edeccf2bfa7465b7c6c-1699357112067-42.png)

**2.3.Burn System:**

Use **Win32DiskImager** to burn the official **Raspberry Pi OS** mirror to the TFT memory card.

![](./media/80d236cae8bdf63d80dc65048ffb52b3-1699357112067-43.png)

![](./media/243d1ef34211eafe1a92b67fc0ee85a2-1699357112067-44.png)

![](./media/ea854c476e9a8d4f82dd4a7c714cd5af-1699357112067-45.png)

After the mirror system is burned, don’t pull out the card reader, use a notepad to create a file named **SSH** and delete**.txt**, then copy it to the boot directory of the TFT card, so that you can open the SSH login function, as shown in the following figure:

![](./media/ffb73310322accd671da373bb2e71945-1699357112067-46.png)

Pull out the card reader.

**2.4.Log in system:**

The following operations require raspberry to share the same LOCAL area network with the PC.

Insert the burned TFT memory card into the Raspberry Pi, connect internet cables and plug in power. If there is a screen and a HDMI cable of Raspberry Pi, connect the screen, and you can see the Raspberry Pi OS startup screen. If there is not a HDMI cable of Raspberry Pi, you can enter the desktop of Raspberry Pi via SSH remote login software---WinSCP and xrdp.

**Remote login**

**Use WinSCP to log in using the default Raspberry Pi system name、default user name、default password.**

**Note that only a raspberry pi can be connected to a network.**

![](./media/0a41d5c629ec98afbc31dc47ff5c18ec-1699357112068-47.png)

![](./media/ff64e71b9e30df60d0b099dbc2532587-1699357112068-48.png)

**View the ip address and mac address** ![](./media/a4285a452978026c9e60c31d35974315-1699357112068-49.png)

Click to open terminal and input the password: raspberry, and tap“Enter”on keyboard.

![](./media/a433a9ee584c821a702d0250937e2ba8-1699357112068-50.png)

![](./media/7fb10d842cc7fd824a325d30fc3ecdc7-1699357112068-51.png)

After successfully login, open the terminal, input **ip a** and tap“Enter”keyboard to view the ip address and mac address.

![](./media/132e9ab754a0f63e38b3e4cfbc3679f2-1699357112068-52.png)

From the above figure, mac address of this Raspberry Pi is a6:32:17:61:9c, and ip address is 192.168.1.128(use ip address to finish
xrdp remote login).

Since mac address never changes, you could confirm ip via mac address when not sure which ip it is.

**Fix the IP address of Raspberry Pi**

IP address is changeable, therefore, we need to make IP address fixed for convenient use.

Follow the below steps:

Switch to root user

If without root user’s password

① Set root password

Input password in the terminal: sudo passwd root to set password.

② Switch to root user

su root

③ Fix the configuration file of IP address

Firstly change IP address of the following configuration file.

（\#New IP address:：address 192.168.1.99）

Copy the above new address to terminal and tap“**Enter**”keyboard.

**Configuration File:**

echo -e '

auto eth0

iface eth0 inet static

\#Change IP address

address 192.168.1.99

netmask 255.255.255.0

gateway 192.168.1.1

network 192.168.1.0

broadcast 192.168.1.255

dns-domain 119.29.29.29

dns-nameservers 119.29.29.29

metric 0

mtu 1492

'\>/etc/network/interfaces.d/eth0

![](./media/a68a4f59d4d364efa28b6680a2c48d43-1699357112068-53.png)

④ Reboot the system to activate the configuration file.

Input the restart command in the terminal: sudo reboot

You could log in via fixed IP afterwards.

⑤ Check IP to ensure IP address fixed well.

![](./media/b4313e2d78a4289705c658a1ebbc962b-1699357112068-54.png)

Log in desktop on Raspberry Pi wirelessly

If we don't have an HDMI cable to connect to the display, can we wirelessly log in to the Raspberry Pi desktop from the Windows
desktop? Yes, there are many methods, VNC and Xrdp are commonly used to log in desktop of Raspberry Pi wirelessly.

Let’s take an example of Xrdp.

①Install Xrdp Service in the terminal

Installation commands:

Switch to root User: su root

Installation commands: apt-get install xrdp

Enter y and tap“**Enter**”keyboard..

As shown below:

![](./media/aa59941ff4c1e582e8183c1dc3767fce-1699357112068-55.png)

Open the remote desktop connection on Windows

Press **WIN+R** on keyboard and enter mstsc.exe.

As shown below:

![](./media/e5a66a3a1c998f8feb1c21c7a457ec4e-1699357112068-56.png)

Enter the IP address of the Raspberry Pi, as shown below. Click“Connect” and then click “Connect”again. 192.168.1.99 is the ip address we use, you could change it into your IP address.

![](./media/c41c66bea61b30019e02a74b483af700-1699357112068-57.png)

A prompt will appear and you can click“Yes”.

![](./media/297813f1370ce5c158fac61511f61295-1699357112068-58.png)

Then enter the user name: pi ,and the default password: raspberry, as shown below:

![](./media/251fddc1decc15d0b69f8a0c7467d5c1-1699357112068-59.png)

Click“OK”or tap“Enter”keyboard, you will view the desktop of Raspberry Pi OS, as shown below:

![](./media/56bd5693edd484c4433dc438b58c6130-1699357112068-60.png)

Now, we finish the basic configuration of the Raspberry Pi OS system.

## Preparation of C language control basic hardware:

C language is a programming language with a considerably fast running speed. There are numerous software and system core code written in it, such as Linux system. Notably, hardware MCU and embedded class are not exception. Thereby, it makes sense to learn the C language to control hardware.

#### (1)Description of basic raspberry pi accessories：

**Raspberry Pi 4B：**

Below are the raspberry pi pictures and model pictures supported by this learning kit. There are 40 pins.

| Raspberry Pi 4B                                              | Raspberry Pi 4B Model                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![image-20231023083244170](./media/image-20231023083244170-1699357112068-61.png) | ![image-20231023083249083](./media/image-20231023083249083-1699357112068-62.png) |


**Hardware Interfaces**

![](./media/d232a87d73f7426894a6cafed80521a0-1699357112068-63.png)

#### Raspberry Pi +ESP32 main board + breadboard +USB cable, as shown below：

![](./media/57cc1390c1a7a0bdd3525a17d65867d3-1699357112070-64.jpeg)

**(3)Copy Example Code Folder to Raspberry Pi：**

Place example code folder to the pi folder of Raspberry Pi. Just copy and paste the **2. Projects.zip** file (the default is **ZIP** file)that we provided into user pi and unzip it, as shown below:                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            

![](./media/e7b577a013d27250449f6a6062f2a692-1699357112070-65.png)

![](./media/7d4668651b52a101834588ce80756ba9-1699357094012-1-1699357112070-66-1699357524003-227-1699409606509-8.png)

![](./media/83ed5ef4d005232ecd32aeec8e969173-1699357112070-67.png)

![](./media/9e718971963a2a8542239e49f5fda29a-1699357112070-68-1699407400607-1-1699409500460-6.png)

![d768043901c5601e921983510d4bc460-169935711](./media/d768043901c5601e921983510d4bc460-169935711.png)

**Linux System（Raspberry Pi）：**

### (2) Download and install Arduino IDE：

（1）First, click on Raspberry Pi's browser.

![](./media/027fa8703101b0c296fbc82f9f246a36-1699357112070-70.png)

2.  Enter the Official Arduino website in your browser: [www.arduino.cc/en/software](http://www.arduino.cc/en/software) , as shown below:

![](./media/64b964654fbdf403e42b61c753de120d-1699357112070-71.png)

![](./media/e36e4d78ca3e5f57d51204d10be4b1a8-1699357112070-72.png)

There are various versions of IDE for Arduino. Just download a version compatible with your system (install the lasted Arduino IDE) and click“Linux ARM 32 bits”.

![](./media/673eacbf2dd436181621cbf2dd901cdd-1699357112070-73.png)

Just click **JUST DOWNLOAD** to download

![](./media/83d707e7d53788a08e63bab812298b09-1699357112070-74.png)

After a few seconds, the lastest Arduino IDE（Arduino 1.8.19 version）zip file can be directly downloaded.

(4) Click ![](./media/673b0d8e5e8fc594f1914418da8d74a9-1699357112070-75.png), then find the **Downloads** file from the pi folder and click it. In the **Downloads** folder, you can see the package“arduino-1.8.19-linuxarm.tar.xz”that you just downloaded. Then unzip the package“arduino-1.8.19-linuxarm.tar.xz”, after a while, the package is unzipped.

![](./media/8bfa85ec821d531fc042e4e2aa4c40ce-1699357112070-76.png)

![](./media/7721714f317a56214f4c14bfbfb92eeb-1699357112070-77.png)

![](./media/0137b14e0053855856de0ff859ea1161-1699357112070-78.png)

![](./media/2e144aae66a787d7c30945b24072b144-1699357112070-79.png)

（5）Click![](./media/b479804e1f9ae2cdfaa0aad8495523d4-1699357112070-80.png)file and tap it，click“Execute”in the dialog that appears to install the Arduino IDE. Once installed, an Arduino software shortcut is generated in the desktop.

![](./media/282a3e90f752066a10c69d75c58bc0be-1699357112070-81.png)

![](./media/cc0f7b8a14fa5bdcb6560f51f6ffc917-1699357112070-82.png)

![](./media/97bf23de0c9aa37db243d67d5e3f8670-1699357112070-83.png)

（6）Click ![](./media/2ef5420fde334b93163b4a35e32e77dd-1699357112070-84.png)and click![](./media/cc7c9f3977d8da562ba2e98a6246c6b5-1699357112070-85.png) to open the Arduino IDE.

![](./media/97f4118fc1f0d19aeb32a5af08812726-1699357112070-86.png)

![](./media/f48690b0a3f56b9436ad4c56f0667af0-1699357112070-87.png)

### (3) Install the ESP32 on Arduino IDE：

Note: You need to download Arduino IDE 1.8.5 or advanced version to install the ESP32.

1)  > Click![](./media/2ef5420fde334b93163b4a35e32e77dd-1699357112070-84.png) and click ![](./media/cc7c9f3977d8da562ba2e98a6246c6b5-1699357112070-85.png) to open the Arduino IDE.

![](./media/6d61bd9f09f10763899e43a873b8bc75-1699357112070-88.png)

2)  Click **“File**”→**“Preferences”**, copy the website address <https://dl.espressif.com/dl/package_esp32_index.json> in the “**Additional Boards Manager URLs:**” and click “**OK**” to save the address.

![](./media/834b8fc35034df92b21b36956fb1b300-1699357112070-89.png)

![](./media/e509e8aece551e449ccb6ab6fffa0dc1-1699357112070-90.png)

3.  Click “**Tools**”→“**Board:**”, then click “**Boards Manager...**” to enter “**Boards Manager**” page . Enter “**esp32**” as follows and
select the latest version to Install. The installation package is not large, click “**Install**” to start the installation.

![](./media/ca9d80ba478d379d40afe119d60ec8cf-1699357112070-91.png)

![](./media/b6d62e4c9cb8f530dc49b8ee92ecd76e-1699357112070-92.png)

![](./media/1eaf35ef0b85b62a54733c2887bbced6-1699357112071-93.png)


4.  After a while, the ESP32 installation package is installed. Then click “**Close**”.

![](./media/07d535a3532a58b15e79c9848ad8a019-1699357112071-94.png)

### 3\. Arduino IDE Settings and Toolbars:

Click![](./media/2ef5420fde334b93163b4a35e32e77dd-1699357112070-84.png) and click ![](./media/cc7c9f3977d8da562ba2e98a6246c6b5-1699357112070-85.png) to open the Arduino IDE.

![](./media/8aca9b5378e794375f2c15d3b4e238ba-1699357112071-95.png)

When downloading the code to the board, you must select the correct name of Arduino board that matches the board connected to the Raspberry Pi, click“**Tools**”→“**Board:**”, as shown below ;

(Note: We use the ESP32 board in this tutorial; therefore, we select ESP32 Arduino**)**

![](./media/973eb76d6528c9464b0f03db2c679a64-1699357112071-96.png)

![](./media/20172f3be362482efa80c49c2603b888-1699357112071-97.png)

Then select the correct COM port (After connecting the ESP32 mainboard to the Raspberry Pi via a USB cable, you can see the corresponding COM port).

![](./media/fab5efb1aeaae7e6864f1286934c89d7-1699357112071-98.png)

![](./media/e341c279be4e2d1a53389e1124e5128d-1699357112071-99.png)

Before uploading the code to the ESP32 mainboard, we have to demonstrate the function of each symbol.

![](./media/d80f72747dd81a7c38022c057eaa6015-1699357112071-100.png)

A- Used to verify whether there is any compiling mistakes or not.

B- Used to upload the sketch to your Arduino board.

C- Used to create shortcut window of a new sketch.

D- Used to directly open an example sketch.

E- Used to save the sketch.

F- Used to send the serial data received from board to the serial monitor.

## Import the Arduino C library

### What are Libraries ?

Libraries are a collection of code that make it easy for you to connect sensors, displays and modules, etc.

For example, the built-in LiquidCrystal library helps talk to LCD displays. There are hundreds of additional libraries available on the Internet for download.

The built-in libraries and some of these additional libraries are listed in the reference. (https://www.arduino.cc/en/Reference/Libraries)

### How to Install a Library ?

**Step 1:** Click ![](./media/e927e911da6b964ab71f193c63403606-1699357112071-101.png)，tap“Downloads”file![](./media/83ad90890a4783af385a3dac7c0954a3-1699357112071-102.png)，and click“arduino-1.8.19”file![](./media/df44a04c4d9dc93465a56e4ff7c9d184-1699357112071-103.png)，then find and click “libraries” file ![](./media/630636db590e92c4969f89967124f96f-1699357112071-104.png)from the “arduino-1.8.19” file.

![](./media/8fd90361aa115003241352cad2d9072d-1699357112071-105.png)

![](./media/52a6147ae9a153e322672a52f96a4c6d-1699357112071-106.png)

![](./media/438dd551f77795e04c4c532374dc13cc-1699357112071-107.png)

![](./media/fcdfbb335828776c4b8d4a56f3833958-1699357112071-108.png)

![](./media/e63db82531b8923e77969bf95662e446-1699357112071-109.png)

**Step 2 :** Copy and paste the Arduino C library ZIP file (the default is ZIP file) from the provided Arduino Libraries folder into the
libraries file opened in the first step（the route is：/home/pi/Downloads/arduino-1.8.19/libraries.

Click on the link to download the library file：[Arduino C Librarie](Arduino-Librarie.zip)

![](./media/984cc72b88cb3b1ff075cfc3d647693a-1699357112071-111.png)

**Step 3:** Unzip the Arduino C package in the libraries folder（for example：right-click“LCD\_128X32.zip”file![](./media/6e589bd70a19a71fe460fc6131a2ab5a-1699357112071-112.png) ，select and tap “Extract Here”to unzip the “LCD\_128X32.zip”file. Similarly, unzip the remaining library files in the same way.). So you can see all the decompressed Arduino C library files.

![](./media/b421fb83a5e123dcf0696cdfd8e0780e-1699357112071-113.png)

![](./media/12447bf0454ff510cec0c1daedf2bd35-1699357112071-114.png)

