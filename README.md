# Linux 802.11 AC support
## *Realtek rtl8812au chipset & family*

## TO DO...
1) Grab, build and test the driver in this repo  
3) Deploy & test widely  
## End of TO DO

This repo is forked from here:  
https://github.com/gordboy/rtl8812au  

See this article for interesting information on 802.11AC in Linux:  
https://forums.linuxmint.com/viewtopic.php?t=234143


### Two USB to 802.11AC chipsets for Linux:
Mediatek MT7612U chipset  - Useless drivers for Linux  
-or-  
Realtek 8812, 8814 chipsets – many github repos with drivers all based on Realtek driver  
So, we will focus on the Realtex 8812 & family  

### Realtek supplied Driver
The Latest and greatest  (FTP site)Realtek driver can be found here:  
Realtek FTP - ftp3.realtek.com.tw, user: RTL8812A pass: J2e8Fg  
http://www.realtek.com.tw/DOWNLOADS/ExpressFTPSite.aspx?DownTypeID=3&DownID=436&PFid=1&Conn=5  
Also, maybe here for an older version:  
http://down.tendacn.com/uploadfile/2017/Drive/U12_linux_v5.1.5_19247.20160830.rar  

But, this cannot be used as is.  For Linux, it has to be integrated into a kernel module.  
These interesting Realtek rtl8812au related repos below have that code - only one has the latest 5.29 driver.   

### Repos
https://github.com/gordboy/rtl8812au  **** (5.2.9 Realtek Driver & where this repo was forked from)  
https://github.com/astsam/rtl8812au/tree/v5.1.5 *** (5.15 Realtek driver!)  
https://github.com/0syntral/rtl8812au (From Kali Linux!)  
https://github.com/diederikdehaas/rtl8812AU  
https://github.com/abperiasamy/rtl8812AU_8821AU_linux *  
https://github.com/ojnickel/rtl8812au  
https://github.com/ulli-kroll/rtl8821au/  
https://github.com/mk-fg/rtl8812au ** (5.15)  
https://github.com/xxNull-lsk/rtl8812AU ** (5.15)  
https://github.com/zyworkshop/rtl8812au_v5.1.5 ** (5.15)  
https://github.com/codeworkx/rtl8812au_asus  
https://github.com/Grawp/rtl8812au_rtl8821au/tree/4.3.20 (From Arch Linux!)  

### Supported Commercial Devices (from: rtl8812au/os_dep/linux/usb_intf.c):  
### 8812
These are the Vendor & Device IDs that are supported by this driver.  You can add others for the same chip set.  
{USB_DEVICE(USB_VENDER_ID_REALTEK, 0x8812), .driver_info = RTL8812}, /* Default ID */  
{USB_DEVICE(USB_VENDER_ID_REALTEK, 0x881A), .driver_info = RTL8812}, /* Default ID */  
{USB_DEVICE(USB_VENDER_ID_REALTEK, 0x881B), .driver_info = RTL8812}, /* Default ID */  
{USB_DEVICE(USB_VENDER_ID_REALTEK, 0x881C), .driver_info = RTL8812}, /* Default ID */  
  
{USB_DEVICE(0x0409, 0x0408), .driver_info = RTL8812}, /* NEC - */  
{USB_DEVICE(0x0411, 0x025D), .driver_info = RTL8812}, /* Buffalo - WI-U3-866D */  
{USB_DEVICE(0x04BB, 0x0952), .driver_info = RTL8812}, /* I-O DATA - Edimax */  
{USB_DEVICE(0x050D, 0x1106), .driver_info = RTL8812}, /* Belkin - Sercomm */  
{USB_DEVICE(0x050D, 0x1109), .driver_info = RTL8812}, /* Belkin - SerComm F9L1109 */  
{USB_DEVICE(0x0586, 0x3426), .driver_info = RTL8812}, /* ZyXEL - */  
{USB_DEVICE(0x0789, 0x016E), .driver_info = RTL8812}, /* Logitec - Edimax */  
{USB_DEVICE(0x07B8, 0x8812), .driver_info = RTL8812}, /* Abocom - Abocom */  
{USB_DEVICE(0x0B05, 0x17D2), .driver_info = RTL8812}, /* ASUS - Edimax */  
{USB_DEVICE(0x0DF6, 0x0074), .driver_info = RTL8812}, /* Sitecom - Edimax */  
{USB_DEVICE(0x0E66, 0x0022), .driver_info = RTL8812}, /* HAWKING - Edimax */  
{USB_DEVICE(0x1058, 0x0632), .driver_info = RTL8812}, /* WD - Cybertan */  
{USB_DEVICE(0x13B1, 0x003F), .driver_info = RTL8812}, /* Linksys - WUSB6300 */  
{USB_DEVICE(0x148F, 0x9097), .driver_info = RTL8812}, /* Amped Wireless - ACA1 */  
{USB_DEVICE(0x1740, 0x0100), .driver_info = RTL8812}, /* EnGenius - EnGenius */  
{USB_DEVICE(0x2001, 0x330E), .driver_info = RTL8812}, /* D-Link - ALPHA */  
{USB_DEVICE(0x2001, 0x3313), .driver_info = RTL8812}, /* D-Link - ALPHA */  
{USB_DEVICE(0x2001, 0x3315), .driver_info = RTL8812}, /* D-Link - Cameo */  
{USB_DEVICE(0x2001, 0x3316), .driver_info = RTL8812}, /* D-Link - Cameo */  
{USB_DEVICE(0x2019, 0xAB30), .driver_info = RTL8812}, /* Planex - Abocom */  
{USB_DEVICE(0x20F4, 0x805B), .driver_info = RTL8812}, /* TRENDnet - Cameo */  
{USB_DEVICE(0x2357, 0x0101), .driver_info = RTL8812}, /* TP-Link - Archer T4U */  
{USB_DEVICE(0x2357, 0x0103), .driver_info = RTL8812}, /* TP-Link - Archer T4UH */  
{USB_DEVICE(0x2357, 0x010D), .driver_info = RTL8812}, /* TP-Link - Archer T4U AC1300 */  
{USB_DEVICE(0x2357, 0x010E), .driver_info = RTL8812}, /* TP-Link - Archer T4UH AC1300 */  
{USB_DEVICE(0x2357, 0x010F), .driver_info = RTL8812}, /* TP-Link - T4UHP */  
{USB_DEVICE(0x7392, 0xA822), .driver_info = RTL8812}, /* Edimax - Edimax */  

### 8814  
{USB_DEVICE(USB_VENDER_ID_REALTEK, 0x8813), .driver_info = RTL8814A}  
{USB_DEVICE(0x2001, 0x331a), .driver_info = RTL8814A}, /* D-Link - D-Link */  
{USB_DEVICE(0x0b05, 0x1817), .driver_info = RTL8814A}, /* ASUS - ASUSTeK */  
{USB_DEVICE(0x056E, 0x400B), .driver_info = RTL8814A}, /* ELECOM - ELECOM */  
{USB_DEVICE(0x056E, 0x400D), .driver_info = RTL8814A}, /* ELECOM - ELECOM */  
{USB_DEVICE(0x7392, 0xA834), .driver_info = RTL8814A}, /* Edimax - Edimax */  
#  

### make  
To make this driver:  
```
cd ~  
mkdir 80211AC  
cd 80211AC  
```
```
sudo apt-get update  
sudo apt-get upgrade  
sudo apt-get install linux-headers-generic  
sudo apt-get install build-essential  
sudo apt-get install git  
sudo apt-get install dkms  
```
```
git clone https://github.com/embeddednow/rtl8812au_5_29.git  
cd rtl8812AU  
make clean  
make  
```
### Warnings & Errors
NOTE: You may get these warning messages:  They are ok.  If you need to, delete the _DATE_ & _TIME_ system variables  
`rtl8812au/core/rtw_debug.c:50:62: warning: macro "__DATE__" might prevent reproducible builds [-Wdate-time]`  
-and-  
`rtl8812au/core/rtw_debug.c:50:62: warning: macro "__TIME__" might prevent reproducible builds`  

### Removing old drivers
if you have previously installed a driver for the 8812au, you have to erase any previous module rtl8812au.ko or 8812au.ko  
It is located in: (Note: Use the appropriate version for your kernel)  
`/lib/modules/4.4.0-83-generic/kernel/drivers/net/wireless/`  

If you have a module for rtl812au there, erase it  
(Again Note: Use the appropriate version for your kernel)  
`sudo rm -r /lib/modules/4.4.0-83-generic/kernel/drivers/net/wireless/8812au.ko`  
-or-  
`sudo rm -r /lib/modules/4.4.0-83-generic/kernel/drivers/net/wireless/rtl8812au.ko`  

and unload the module in case it is active  
`sudo modprobe -r 8812au.ko`  
-or-  
`sudo modprobe -r rtl8812au.ko`  

### Finally! - Install the driver module  
`sudo make install`  
`sudo modprobe 8812au`  
-or-  
`sudo modprobe rtl8812au`  

### To use dkms:  
This is necessary if you want the OS to automatically rebuild this driver after a kernel change or upgrade  
As root (or sudo) copy source folder contents to /usr/src/rtl8812au-5.2.9  
`sudo dkms add -m rtl8812au -v 5.2.9`  
`sudo dkms build -m rtl8812au -v 5.2.9`  
`sudo dkms install -m rtl8812au -v 5.2.9`  
To use dkms uninstall and remove...  
`sudo dkms remove -m rtl8812au -v 5.2.9 --all`  

### NetworkManager and other configuration  
Add this stanza to /etc/NetworkManager/NetworkManager.conf  
(This prevents a random WiFi MAC address being assigned everytime)  

`[device]`  
`wifi.scan-rand-mac-address=no`  

### If the wifi network won't come back after a soft reboot or resume, do the following...  
`sudo lshw -class network`  
-or-  
`iwconfig`  

You will find a logical name for the wireless network.  
Mine is wlx74da38c01319.  
Remember (yeah right!) or copy this name.  
BTW - You will also see in dmesg or the system logs where wlan0 was renamed to this logical name at some point.  

Anyway, edit the following file (or create it if it doesn’t exist):  

`sudo vi /etc/pm/config.d/config`  

put this line in the file:  

`SUSPEND_MODULES=“8812au wlx74da38c01319”`  
-or-  
`SUSPEND_MODULES=“rtl8812au wlx74da38c01319”`  

### To force a new ip address and forget all old leases do the following.  This is necessary sometimes when an access point goes down, the DHCP lease expires and the access point comes back up
`sudo dhclient -r wlx74da38c01319`  
`sudo rm /var/lib/dhcp/dhclient.leases`  
`sudo service network-manager restart`  


