# [Pwnagotchi](https://github.com/evilsocket/pwnagotchi)

Pwnagotchi is an A2C-based "AI" leveraging bettercap that learns from its surrounding WiFi environment to maximize the crackable WPA key material it captures (either passively, or by performing authentication and association attacks). This material is collected as PCAP files containing any form of handshake supported by hashcat, including PMKIDs, full and half WPA handshakes.
---
## Required Hardware
* [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/) : series of small single-board computers (SBCs) </br>
* [MicroSD](https://www.amazon.com/-/zh_TW/SanDisk-%E6%A5%B5%E9%80%9F%E6%89%8B%E9%81%8A%E8%A8%98%E6%86%B6%E5%8D%A1-microSD-%E5%8D%A1%EF%BC%8DC10%E3%80%81U3%E3%80%81V30%E3%80%814K%E3%80%81A1%E3%80%81Micro-SD%EF%BC%8DSDSQXAF-032G-GN6GN/dp/B089M5KV4Y/ref=sr_1_2?crid=3MYOCFDX4PSA0&dib=eyJ2IjoiMSJ9.AZmNmFpwV36TKqV9gUsXJebejGaoSd0WYwDdudO6rqa-2sKk0g71l0m7CRZkYrAV0qKeQra3bhZ8BxDXJ2EYy3YlKmUITlD2ZpE-06KOFOfdq0ImvCQrQPhtPjr5XnE_zpPyNH1KkRpnBYMnpclD9-NjXDVyLB_JINzrBVMi1fpvscK-K-hMP6HNK7V7TZ-9lRZFDBTkXiv0IbhLNVeTb0NIDvD02uJOLMSJnwzpzLY.Eu41XQ13YfttRaHcIb0fHlW5oh7CG3twTRrlgme7uyA&dib_tag=se&keywords=microSD+UHS-3+32&qid=1717471640&sprefix=microsd+uhs-3+32%2Caps%2C405&sr=8-2)(at least 8 GB and UHS３)：store Linux os </br>
* [Micro-USB](https://www.amazon.com/-/zh_TW/7A82VA3/dp/B0D128D1Z8/ref=sr_1_10?crid=3KLVSWE71VSIZ&dib=eyJ2IjoiMSJ9.Oj7_ByznFsDahPlkqwvQiFBV4-f5yRa3iMw0Stl-g8cyE9QbCYM1_5CavEE7mmJ3-gmqJVpnRkLuG8UqXkhjA6Qsa_DsfOTdGCvPFk8fW5wPaBLQFKfTXvrNNDh3YP32RrkzfjvO9SeBTTLKic2nVed1cGv3FzccytG6rw0PZAkgfKUZeUXKdfKyZzt3xEfIySjgnGMEPGlD1lUD0Co-2S6pjyGeFGNhiwu18FU8mZ8.4-67POYMvpcE5-03vhW3Bs2y3ZNvZi5C69GfcnJjQn0&dib_tag=se&keywords=micro+usb+data+transfer+cable&qid=1717471471&sprefix=micro+usb+data%2Caps%2C295&sr=8-10) : that allows data transfer for flash os in sd card </br>
* [Card Reader](https://www.amazon.com/SmartQ-C368-Multi-Card-Compatible-Supports/dp/B06Y1G18KS?th=1) </br>
* [2.13inch e-Paper HAT(Waveshare 3 or 4)](https://www.waveshare.com/2.13inch-e-paper-hat.htm) : screen of pwnagotchi
* (Optional)[PiSugar](https://github.com/PiSugar/PiSugar) :   Battery model for raspberry pi </br>
* (Optional[RTC Model](https://i.imgur.com/KThnkIA.png) : PCF8523, DSL1307 or DS3231 based of real time clock for check pcap file log </br>
* (Optional)[Case](https://pwnagotchi.org/3d-printable-cases/index.html) : 3D print case to protect raspberry pi </br>
---
## OS installation
Sourse: </br>
* balenaEtcher(.exe/.rpm) - https://github.com/balena-io/etcher/releases/ </br>
* Pwnagotchi Image(.zip) - https://github.com/evilsocket/pwnagotchi/releases </br>

Flesh OS:
* step 1 : Select image to flash os onto sd card </br>
* step 2 : Found Path of image </br>
* step 3 : Select which driver can flash image </br>
* step 4 : start of flash </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/Flash-Image.JPG" width="300"></image> </br>
</br>
After Insert microSD card into raspberry pi </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/zero2-close-up.png" width="200"></image> </br>

---

## Install Rndis drivers
Step 1: Control Panel -> Hardware and Sound -> Device Manager -> Ports(COM & LPT)
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/USB(COM).PNG" width="400"></image> </br>

Step 2: Right Click and Select Update Driver -> Browse my computer for drivers </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/SelectUpdateModel.PNG" width="400"></image> </br>

Step 3: Select Browse of drivers(cat & inf) folder Path -> Next </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/DriverUpdatePath.PNG" width="400"></image> </br>

Successful Install and show on Network Connections </br>
Network Connections Path: control panel -> Network and Internet -> Network and Sharing Center -> Change adapter settings </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/SuccessfulRudisInstall.PNG" width="300"></image> </br>
<image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/ControlPanel-RNDISGadget.PNG" width="300"></image> </br>

---

## Config Network ip
Rigth Click Network -> Properties -> (TCP/IPv4) -> Use the following IP address: </br>
* ip address:```10.0.0.1```
* Subnet mask:```255.255.255.0```
* Default gateway:```10.0.0.1```
* Use the following DNS server addresses
* Preferred DNS server: ```8.8.8.8```
 </br><image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/ControlPanel-RNDISGadget-Config.PNG" width="300"></image> </br>

 ---

 ## SSh Remote Configurations
[Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) remote input ```10.0.0.2``` and ```22``` to Hostname(or IP address) and Port, and input ```pwnagotchi``` to Saved Sessions. Next, Click the ```Load``` button to save a ip and port.
 </br><image src="https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/image/putty-ip%26port.JPG" width="300"></image> </br>
 * User: ```pi```
 * Password: ```raspberry```
 ---
* change root account and reset password
```
su
passwd root
```
Output: 
```
New password: <new password>
Retype new password: <new password>
passwd: password updated successfully
``` 
* enable sshd to remote control FTP
```
echo "PermitRootLogin yes" > /etc/ssh/sshd_config
sudo systemctl restart ssh.service
```
* Edit Pwnagotchi config file and start it
Config.toml can follewing this part : https://github.com/karzaf/Pwnagotchi-tw-zh-/blob/main/pwnagotchi/config/config.md 
```
cd /etc/pwnagotchi/
vi config.toml
pwnagotchi
```


