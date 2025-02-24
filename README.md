# MeshCore-FAQ
A list of frequently-asked questions and answers for MeshCore

---

## Q: What do you need to start using MeshCore?
**A:** You need LoRa hardware devices to run MeshCore firmware as clients or server (repeater and room server).

### Hardware
To use MeshCore without using a phone as the client interface, you can run MeshCore on a T-Deck or T-Deck Plus. It is a complete off-grid secure communication solution.  

MeshCore is also available on a variety of 868MHz and 915MHz LoRa devices. For example, RAK4631 devices (19003, 19007, 19026), Heltec V3, Xiao S3 WIO, Xiao C3, Heltec T114, Station G2, Seeed Studio T1000-E. More devices will be supported later.

### Firmware
MeshCore has four firmware types that are not available on other LoRa systems. MeshCore has the following:

#### Companion Radio Firmware
Companion radios are for connecting to the Android app or web app as a messenger client. There are two different companion radio firmware versions:

1. **BLE Companion**  
   BLE Companion firmware runs on a supported LoRa device and connects to a smart device running the Android MeshCore client over BLE (iOS MeshCore client will be available soon)  
   <https://meshcore.co.uk/apps.html>

2. **USB Serial Companion**  
   USB Serial Companion firmware runs on a supported LoRa device and connects to a smart device or a computer over USB Serial running the MeshCore web client  
   <https://meshcore.liamcottle.net/#/>  
   <https://client.meshcore.co.uk/tabs/devices>

#### Repeater
Repeaters are used to extend the range of a MeshCore network. Repeater firmware runs on the same devices that run client firmware. A repeater's job is to forward MeshCore packets to the destination device. It does **not** forward or retransmit every packet it receives, unlike other LoRa mesh systems.  

A repeater can be remotely administered using a password-authenticated T-Deck (and soon from a BLE Companion client).

#### Room Server
A room server is a simple BBS server for sharing posts. Currently (late February 2025), only T-Deck devices can connect to a room server. There are plans to enable smart device clients to connect to a room server. Room servers can be remotely administered using a password-authenticated T-Deck (soon from a BLE Companion client).  

When a client logs into a room server, the client will receive the previously 16 unseen messages.

A room server can also take on the repeater role.  To enable repeater role on a room server, use this command:

`set repeat {on|off}`

---

## Initial Setup

### Q: How many devices do I need to start using meshcore?
**A:** If you have one supported device, flash the BLE Companion firmware and use your device as a client.  You can connect to the device using the Android client via bluetooth (iOS client will be available later).  You can start communiating with other MeshCore users near you.

If you have two supported devices, and there are not many MeshCore users near you, flash both of them to BLE Companion firmware so you can use your devices to communiate with your near-by friends and family.

If you have two supported devices, and there are other MeshcCore users near by, you can flash one of your devices with BLE Companion firmware, and flash another supported device to repeater firmware.  Place the repeater high above ground o extend your MeshCore network's reach.

If you have more supported devices, you can use your additional deivces with the room server firmware.  

### Q: Does MeshCore cost any money?

**A:** All radio firmware versions (e.g. for Heltec V3, RAK, T-1000E, etc) are free and open source developed by Scott at Ripple Radios.  

The native Android and iOS client is free and will be open source developed by Liam Cottle, developer of meshtastic map at [meshtastic.liamcottle.net](https://meshtastic.liamcottle.net) on [github ](https://github.com/liamcottle/meshtastic-map)and [reticulum-meshchat on github](https://github.com/liamcottle/reticulum-meshchat). 

The T-Deck firmware is free to download and most features are available with out cost.  To support the firmware developer, you can pay for a registration key to unlock your T-Deck for deeper map zoom and remote server administration over RF using the T-Deck.  You do not need to pay for the registration to use your T-Deck for direct messaging and connecting to repeaters and room servers. 


### Q: What frequencies are supported by MeshCore?
**A:** It supports the 868MHz range in the UK/EU and the 915MHz range in New Zealand, Australia, and the USA. Countries and regions in these two frequency ranges are also supported. The firmware and client allow users to set their preferred frequency.  
- Australia and New Zealand are using **915.8MHz**
- UK and EU are gravitating toward **867.5MHz**
- There are discussions on discord for UK to move to 869.525MHz (https://discord.com/channels/826570251612323860/1330643963501351004/1342554454498742374)
- USA is gravitating toward **910.525MHz**

the rest of the radio settings are the same for all frequencies:  
- Spread Factor (SF): 10  
- Coding Rate (CR): 5  
- Bandwidth (BW): 250.00  

### Q: What is an "advert" in MeshCore?
**A:** 
Advert means to advertise yourself on the network. In Reticulum terms it would be to announce. In Meshtastic terms it would be the node sending it's node info.

MeshCore allows you to manually broadcast your name, position and public encryption key, which is also signed to prevent spoofing.  When you click the advert button, it broadcasts that data over LoRa.  MeshCore calls that an Advert. There's two ways to advert, "zero hop" and "flood".

* Zero hop means your advert is broadcasted out to anyone that can hear it, and that's it.
* Flooded means it's broadcasted out, and then repeated by all the repeaters that hear it.

MeshCore clients only advertise themselves when the user initiates it. A repeater (and room server?) advertises its presence once every 240 minutes. This interval can be configured using the following command:

`set advert.interval {minutes}`

###Q: Is there a hop limit?

**A:** Internally the firmware has maximum limit of 64 hops.  In real world settings it will be difficult to get close to the limit due to the environments and timing as packets travel further and further.  We want to hear how far your MeshCore conversations go. 


---


## Server Administration

### Q: How do you configure a repeater or a room server?
**A:** One of these servers can be administered with one of the options below:
- Connect the server device through a USB serial connection to a computer running Chrome on this site:  
  <https://googlechromelabs.github.io/serial-terminal/>
- A T-Deck running unlocked/registered MeshCore firmware. Remote server administration is enabled through registering your T-Deck with Ripple Radios. It is one of the ways to support MeshCore development. You can register your T-Deck at:  
  <https://buymeacoffee.com/ripplebiz/e/249834>
- MeshCore smart device clients may have the ability to remotely administer servers in the future.

### Q: Do I need to set the location for a repeater?
**A:** With location set for a repeater, it can show up on a MeshCore map in the future. Set location with the following commands:

`set lat <GPS Lat> set long <GPS Lon>`

You can get the latitude and longitude from Google Maps by right-clicking the location you are at on the map.

### Q: What is the password to administer a repeater or a room server?
**A:** The default admin password to a repeater and room server is `password`. Use the following command to change the admin password:

`password {new-password}`


### Q: What is the password to join a room server?
**A:** The default guest password to a room server is `hello`. Use the following command to change the guest password:

`set guest.password {guest-password}`


---

## T-Deck Related

### Q: What are the steps to get a T-Deck into DFU (Device Firmware Update) mode?
**A:**  
1. Device off  
2. Connect USB cable to device  
3. Hold down trackball (keep holding)  
4. Turn on device  
5. Hear USB connection sound  
6. Release trackball  
7. T-Deck in DFU mode now  
8. At this point you can begin flashing using <https://flasher.meshcore.co.uk/>

### Q: Why is my T-Deck Plus not getting any satellite lock?
**A:** For T-Deck Plus, the GPS baud rate should be set to **38400**. Also, a number of T-Deck Plus devices were found to have the GPS module installed upside down, with the GPS antenna facing down instead of up. If your T-Deck Plus still doesn't get any satellite lock after setting the baud rate to 38400, you might need to open up the device to check the GPS orientation.

### Q: Why is my OG (non-Plus) T-Deck not getting any satellite lock?
**A:** The OG (non-Plus) T-Deck doesn't come with a GPS. If you added a GPS to your OG T-Deck, please refer to the manual of your GPS to see what baud rate it requires. Alternatively, you can try to set the baud rate from 9600, 19200, etc., and up to 115200 to see which one works.

### Q: What size of SD card does the T-Deck support?
**A:** Users have had no issues using 16GB or 32GB SD cards. Format the SD card to **FAT32**.

### Q: How do I get maps on T-Deck?
**A:** You need map tiles. You can get pre-downloaded map tiles here (a good way to support development):  
- <https://buymeacoffee.com/ripplebiz/e/342543> (Europe)  
- <https://buymeacoffee.com/ripplebiz/e/342542> (US)

Another way to download map tiles is to use this Python script to get the tiles in the areas you want:  
<https://github.com/fistulareffigy/MTD-Script>  

There is also a modified script that adds additional error handling and parallel downloads:  
<https://discord.com/channels/826570251612323860/1330643963501351004/1338775811548905572>  

UK map tiles are available separately from Andy Kirby on his discord server:  
<https://discord.com/channels/826570251612323860/1330643963501351004/1331346597367386224>

### Q: Where do the map tiles go?
Once you have the tiles downloaded, copy the `\tiles` folder to the root of your T-Deck's SD card.

### Q: How to unlock deeper map zoom and server management features on T-Deck?
**A:** You can download, install, and use the T-Deck firmware for free, but it has some features (map zoom, server administration) that are enabled if you purchase an unlock code for \$10 per T-Deck device.  
Unlock page: <https://buymeacoffee.com/ripplebiz/e/249834>


### Q: The T-Deck sound is too loud?
### Q: Can you customize the sound?

**A:** You can customise the sounds on the T-Deck, just by placing `.mp3` files onto the `root` dir of the SD card. `startup.mp3`, `alert.mp3` and `new-advert.mp3`


---

## General

### Q: Is MeshCore open source?
**A:** All the firmware is freely available. Everything is open source except the T-Deck firmware.  
- Firmware repo: <https://github.com/ripplebiz/MeshCore>  
- Android and iOS clients: will be available later

### Q: How can I support MeshCore?
**A:** Provide your honest feedback on GitHub and on AndyKirby's Discord server <http://discord.com/invite/H62Re4DCeD>. Spread the word of MeshCore to your friends and communities; help them get started with MeshCore. Support MeshCore development at <https://buymeacoffee.com/ripplebiz>.

### Q: How do I build MeshCore firmware from source?
**A:** See instructions here:  
<https://discord.com/channels/826570251612323860/1330643963501351004/1342120825251299388>  

Andy also has a video on how to build using VS Code:  
*How to build and flash Meshcore repeater firmware | Heltec V3*  
<https://www.youtube.com/watch?v=WJvg6dt13hk> *(Link referenced in the Discord post)*

### Q: Does MeshCore support ATAK
**A:** ATAK is not currently on MeshCore's roadmap.
    
---

## Troubleshooting

### Q: My client says another client or a repeater or a room server was last seen many, many days ago.
### Q: A repeater or a client or a room server I expect to see on my discover list (on T-Deck) or contact list (on a smart device client) are not listed.
**A:**  
- If your client is a T-Deck, it may not have its time set (no GPS installed, no GPS lock, or wrong GPS baud rate).  
- If you are using the Android or iOS client, the other client, repeater, or room server may have the wrong time.  

You can get the epoch time on <https://www.epochconverter.com/> and use it to set your T-Deck clock. For a repeater and room server, the admin can use a T-Deck to remotely set their clock (clock sync), or use the `time` command in the USB serial console with the server device connected.

### Q: How to connect to a repeater via BLE (bluetooth)?
**A:** You can't connect to a device running repeater firmware  via bluetooth.  Devices running the BLE companion firmware you can connect to it via bluetooth using the android app

### Q: I can't connect via bluetooth, what is the bluetooth pairing code?

**A:** the default bluetooth pairing code is `123456`

### Q: My Heltec V3 keeps disconnecting from my smartphone.  It can't hold a solid Bluetooth connection.

**A:** Heltec V3 has a very small coil antenna on its PCB for WiFi and Bluetooth connectivty.  It has a very short range, only a few feet.  It is possible to remove the coil antenna  and replace it with a 31mm wire.  The BT range is much improved with the modification.


---
    
    
