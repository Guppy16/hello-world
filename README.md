# Projects

This repo stores is a list of ideas and my research so far. 
If enough progress has been made, I will create a separate repo for that project.
View my complete projects on my [GitHub](https://github.com/Guppy16)

---
## Spun out Repos
List of repos that have spun out from this idea generation repo

- [pi-gamez](https://github.com/Guppy16/pi-gamez): Using a Wii remote or pi as a game controller
- [electric-board](https://github.com/Guppy16/electric-board): Making an electric penny board

---

## Research in Progress

- LinuxMint
  - Motivation: Repurposing old laptop for lightweight tasks (browsing, coding, pdf viewing)
  - [VerifyISOimage](https://linuxmint-installation-guide.readthedocs.io/en/latest/verify.html) on [Windows](https://forums.linuxmint.com/viewtopic.php?f=42&t=291093)

- Thermal Camera project
  - Aim: Detect thermally cool spots within the house to determine if insulation is needed. 
  - Thermal camera: MLX90640 from [Pimorini](https://shop.pimoroni.com/products/mlx90640-thermal-camera-breakout)
  - The repo that worked on my Pico was a [driver by Vian Patel](https://github.com/VianPatel/mlx90640-RPI-Pico). 
  This should be used as a submodule within my project. 
  - The simplest approach would be to live stream the serial data over usb and plot in Python. Interpolation with scipy would be nice. 
  - Other resources:
    - [Datasheet](https://cdn.sparkfun.com/assets/7/b/f/2/d/MLX90640-Datasheet-Melexis.pdf)
    - [Pimorini Pico Library](https://github.com/pimoroni/pimoroni-pico)
    - [Pimorini MLX90640 Library](https://github.com/pimoroni/mlx90640-library) (I don't think this is compatible with the Pico, due to the I2C driver being different).
  

- Universal Remote
  - IR
    - Bought IR LEDs from bitsboxuk. (TSOP31236, TSOP2438, TSUS5400)
    - Arduino IR-Remote [github repo](https://github.com/Arduino-IRremote/Arduino-IRremote)
    - Cheap IR blaster [TSOP 31238](https://www.mouser.co.uk/datasheet/2/427/tsop312-1767175.pdf). 
    Tests showed that this was unreliable.
    - [TSUS 54xx](https://docs.rs-online.com/f3b6/0900766b80e22d5c.pdf) Note sure why this was researched
    - Other methods:
      - RPi Geek post using _lirc_ library
      - [Johannes' blog](https://wej.k.vu/electronics/serial_ir_remote_control/)
      - VR19 IR sensor
      - Build a Universal IR Controller using an older smartphone
      - 
  - Wifi
    - Need to experiment with Pico Wireless module
    - Does radio remote work on the required frequency?


- Turn a laptop hard drive into a portable drive [here](https://www.cnet.com/google-amp/news/how-to-reuse-your-old-laptop-hard-drive/)
- Home Server
  - Check out this home lab [article](https://haydenjames.io/home-lab-beginners-guide-hardware/)
  - Media server using _Plex Server_
  - Article from [the Home Journey](https://thesmarthomejourney.com/2021/09/06/home-server-basics-ansible/)
  - Video by [Raid Owl](https://www.youtube.com/watch?v=rmVCtZrtvgA)
  - Check notes with Noah
  - [TrueNAS](https://www.truenas.com/truenas-core/)
  - [How to setup a simple DIY NAS](https://www.technicallywizardry.com/how-to-set-up-a-simple-diy-nas-build/)
  - [DIY NAS 2020](https://blog.briancmoses.com/2020/11/diy-nas-2020-edition.html)
  - [Conver Router into a NAS Server](https://dongknows.com/turning-wi-fi-router-usb-port-into-a-nas-server/)
  - [Re-using an Old Router (perhaps as a NAS server?)](https://www.makeuseof.com/tag/ways-reuse-old-router/)
- [Add SSD + HDD combo to PC](https://www.makeuseof.com/tag/using-a-small-ssd-and-a-regular-hard-drive-how-to-organize-your-files/)

---

## Backlog

- Laptop Repair
  - I own a Dell XPS 2-in-1 7390, which has a [common issue]([url](https://www.dell.com/community/en/conversations/xps/xps-13-7390-2-in-1-the-rubber-strip-at-the-bottom-came-off-after-two-months/647f87e6f4ccf8a8de729a68?page=2)) of the rubber coming off the back casing
  - Sol 1: [2pcs /Set New Laptop Bottom Cover Base Replacement Pad Rubber For Dell XPS 13 9370 9380 7390 P82G](https://www.aliexpress.com/item/1005006037614254.html)
  - Sol 2: [Genuine Dell XPS 13 7390 2-in-1 P103G Base Bottom Case Cover 02CXR0 Grade C](https://www.ebay.co.uk/itm/404489208832)
- Linux on Dell XPS 2-in-1 7390
  - Brief: Windows uses too much RAM and SSd storage. I don't use any CAD software anymore, so I can switch over to Linux
  - It seems that current versions of Linux/Kernel don't support:
    - Camera, Bluetooth pen (partial support was mentioned in Gentoo)
  - Arch:
    - [Wiki](https://wiki.archlinux.org/title/Dell_XPS_13_2-in-1_(7390)) page shows more setup information
    - [Talk](https://wiki.archlinux.org/title/Talk:Dell_XPS_13_2-in-1_(7390) page is a discussion on current issues
    - This [gist](https://gist.github.com/giannivh/02f69ebf1470c811d0f52fec5dc669e4) exists to help configure the settings when installing Arch
  - Ubuntu:
    - [Wiki](https://wiki.ubuntu.com/Dell/XPS/XPS-13-7390-2-in-1) lists known issues
 

- Minigames
  - Aim: Use the SSD1306 displays bought ages ago
  - Display [datasheet](https://cdn-shop.adafruit.com/datasheets/SSD1306.pdf)
  - Display [schematic](https://cdn-learn.adafruit.com/assets/assets/000/093/884/original/adafruit_products_0-96in_OLED_sch.png?1596746114)
  - 

- DJI Tello Drone in Acro Mode
  - Seems like no one has coded it, but some ppl may wna try it
  - Not sure if it's feasible considering the drone's props are NOT screwed on and battery may not be suitable
  - Could try and get sponsored from [here](https://www.unmannedtech.co.uk/studentsresearchers.html)

- Nixie Clock
  - Purchase the kit w/o IN-14 tubes on [ebay](https://www.ebay.co.uk/itm/184671627749)
  - Purchase the IN-14 tubes in [4](https://www.ebay.co.uk/itm/303748809541) / [6](https://www.ebay.co.uk/itm/274874326051) pack on ebay
  - PV Electronics Kit [Instructions](http://www.pvelectronics.co.uk/index.php?main_page=page_2)
  - Note that the kit on PV Electronics [site](https://www.pvelectronics.co.uk/index.php?products_id=244) is more expensive

- [DIY VR Haptic Gloves](https://hackaday.io/project/178243-lucidvr-budget-haptic-glove)
  - [YT Vid](https://www.youtube.com/watch?v=nmP8iGaPbeI)

- Convert mechanical standing desk into electric standing desk
   - use [motor](https://www.amazon.co.uk/WINOMO-3V-6V-Short-Shaft-Torque/dp/B010SP427I) connected in H-bridge
   - rpi simple button control for now
   - possible upgrade would be to make it voice activated

- Arduino Whack-a-mole Lockdown exercise game inspired by [Sajed Dosenbach](https://www.youtube.com/watch?v=iWI_qy8OntE)
  - Could try a software approach using paper and img processing
  - OR could copy him and use 3D printed parts
    - Could plant it outside in soil to play outside

- Setup Pi Hole
  - [Tutorial by LTT](https://linustechtips.com/topic/1094810-pi-hole-setup-tutorial/)
  - May need to do some DNS manipulation with [OpenDNS](https://support.opendns.com/hc/en-us/articles/228009007-Android-Configuration-instructions-for-OpenDNS)
  - [Tutorial and Docs from Pi Hole](https://docs.pi-hole.net/guides/vpn/openvpn/installation/)

- Frisbee that can be seen in the dark 
by using the reflective propoerties of stree-reflectors [cat's eyes](https://en.m.wikipedia.org/wiki/Cat's_eye_(road))

- Simulation of particle dyanmics inspired from vid by [Reducible](https://www.youtube.com/watch?v=eED4bSkYCB8)

- Build your own keyboard using this [PCB Guide book](https://wiki.ai03.com/books/pcb-design)

- Home networking
  - Home automation using HomeAssistant
  - _Syncthing_ can be used to sync files seamlessly; perhaps streaming may be more sensible

- Phone APKs
  - ReVanced - not sure what's the most legit, or if they're all the same
    - [revanced.app](https://revanced.app/)
    - [VancedManager](https://vancedmanager.com/)
    - [revanced.io](https://revanced.io/youtube/)
  - GCam Mode

- Mirror Magic
  - I got a spare monitor from a partially broken monitor at school. [Panel specs](https://www.panelook.com/LTM170EU-L31_Samsung_17.0_LCM_overview_8029.html)
  - [Monitor Driver board I bought](https://www.aliexpress.com/item/4000996604990.html)
  - [Other potential board](https://www.aliexpress.com/item/32828904517.html)
  - May need to purchase an expandable micro usb to USB slots

- Photo Storage
  - Motivation: After going on a group trip, I wanted people to share pictures, however current methods do nota allow this without using up a lot of storage space.
  - Ideas: Create a new google account, and share pictures using up its free tier
  - There are some articles:
    - https://www.techradar.com/best/best-photo-storage
    - https://www.greenfly.com/other-resources/collect-photos-from-group/
  - Motivation 2: I want to be able to store photos in a way that makes it easier for me to recall events.
  - Photocircle: https://www.photocircleapp.com/
  - 

---

## 3D printer upgrades

- Modify Start GCode
- [Full Control](https://fullcontrol.xyz/) e.g. overhang challenge
- Check firmware
  - [Update Firmware](https://howchoo.com/ender3/ender-3-v2-firmware-update)
  - [Creality Site](https://www.creality.com/download)
  - It may be better to compile firmware from source
- Octoprint
  - [x] [Setup Octoprint](https://howchoo.com/octoprint/ender-3-v2-octoprint)
  - [ ] Record vids and upload them to YT
  - [ ] [Power RPi from 3D printer power supply](https://howchoo.com/3dprinting/how-to-power-a-raspberry-pi-from-your-3d-printer)
  - [ ] [Print an enclosure for RPi](https://www.thingiverse.com/thing:3256773). [Another One](https://www.thingiverse.com/thing:4176051) - interesting design, but may not work
  - [ ] [Print Camera mount](https://www.thingiverse.com/thing:3417079)
  - [ ] Attach a fan and camera

- Safety
  - [ ] Ventilation
  - [ ] Smoke detector
  - [ ] Smart switch
  - [ ] Enclosed

- Upgrade to Aluminium Extruder
  - [Tutorial](https://www.youtube.com/watch?v=ikVFselJO4Y)
  - [Purchase](https://www.th3dstudio.com/product/ezfeed-extruderupgraded-aluminum-extruder-v2/)

- Connect a projector to get a live preview of what's being built

---

## Toys to fix

- Fix laser in Khet game
  - Will need to figure out safety of laser
  - Find laser [here](https://www.aliexpress.com/w/wholesale-laser-1-mw-red.html)

- Fix Robi robot
  - Seems like smth wrong with the voice recognition
  - Check the [forum](https://forum.model-space.co.uk/)

---

## Skills to Learn / Reading List

- [Explainable AI Packages](https://selfexplainml.github.io/PiML-Toolbox/_build/html/guides/testing.html)
- Build WebApps using Rust (e.g. Rocket Framework)
- [Gemoetric Deep Learning](https://geometricdeeplearning.com/)
- Quantum Computing for programmers
- Learn dvorak
- Python ML for recognising digits
- Python ML for games using reinforcement learning
- [Functional Programming](https://mitpress.mit.edu/sites/default/files/sicp/full-text/book/book.html)
- Watch maths for ML
- Flashcards using [Gizmo](https://gizmo.ai/) (A Cambridge startup)
