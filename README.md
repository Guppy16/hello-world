# Projects

This repo stores is a list of ideas and my research so far. 
If enough progress has been made, I will create a separate repo for that project.
View my complete projects on my [GitHub](https://github.com/Guppy16)

---

## Work in Progress

- Electric Penny Board
  - 1 Electric Wheel Combo:
    - [ESC £50](https://www.amazon.co.uk/Focket-Electric-Skateboard-Longboard-Controller/dp/B07WHWV7HJ)
    - [Electric Wheel £70](https://www.ebay.co.uk/itm/353179721593)
  - 2 Electric Wheel Combo:
    - ESC
      - [£90](https://www.amazon.co.uk/Focket-Skateboard-Longboard-Substitute-Mainboard/dp/B07Y7ZHRPQ)
      - [£60](https://www.ebay.co.uk/itm/284278794824)
      - [£50](https://www.ebay.co.uk/itm/203240710991)
     - [Dual Hub Motor Drive Kit](https://www.ebay.co.uk/itm/313658467222)
  - 6S2P or [10S2P > £100](https://www.amazon.co.uk/s?k=10s2p+Battery)
  - Charger 
  - [Spare parts](https://www.ebay.co.uk/itm/163846909246)

- Mirror Magic
  - I got a spare monitor from a partially broken monitor at school. [Panel specs](https://www.panelook.com/LTM170EU-L31_Samsung_17.0_LCM_overview_8029.html)
  - [Monitor Driver board I bought](https://www.aliexpress.com/item/4000996604990.html)
  - [Other potential board](https://www.aliexpress.com/item/32828904517.html)
  - May need to purchase an expandable micro usb to USB slots

- Turn a laptop hard drive into a portable drive [here](https://www.cnet.com/google-amp/news/how-to-reuse-your-old-laptop-hard-drive/)
- Setup a local network storage using modified laptop
  - Check out this home lab [article](https://haydenjames.io/home-lab-beginners-guide-hardware/)
- [Add SSD + HDD combo to PC](https://www.makeuseof.com/tag/using-a-small-ssd-and-a-regular-hard-drive-how-to-organize-your-files/)

---

## Cool Ideas

- Use Wii(U) Controller for Steam
  - Specifically, want to use a wii u controller for drone games such as LiftOff, so that I don't have to take my controller back home
  - Most controllers connect over bluetooth. The BL stack required for this is built in to Linux, but not in to Windows. There are some options for Windows, which I haven't tested yet because they manipulate the BL driver directly:
    - [WiinUPro](https://github.com/KeyPuncher/WiinUPro/releases)
    - TeHaxor69 realsed some SW on [this GBATEMP thread](https://gbatemp.net/threads/wii-u-pro-controller-to-pc-program-release.343159/)
    - [This reddit post](https://www.reddit.com/r/wiiu/comments/3bzdx0/wii_u_pro_controller_as_xbox_controller_on/) uses the Toshiba driver. 
  - However, note that I couldn't get the Wii U Pro Controller to connect to my Linux Mint Laptop, but could get the normal Wii Controller. 
  I suspect this may be a BL stack issue, considering that all controllers can connect to the Wii U normally. It could also be a HW issue.
  Other people also had a similar issues:
    - [Wii U Pro controller was not detected](https://forum.manjaro.org/t/wii-u-pro-controller-is-not-detected-by-bluetooth/54420)
    - Some people found that there was an issue connecting the Wii U Pro Controller after an update [here](https://www.linux.org/threads/solved-cannot-connect-wii-u-pro-controller-after-an-update.33396/)
    - Note that it also seems that a Switch controller can't be connected yet as mentioned on this [reddit thread](https://www.reddit.com/r/linux_gaming/comments/98xkt9/wiiu_pro_controllers_dont_work/). 
    However [this reddit thread](https://www.reddit.com/r/wiiu/comments/f5cn77/wii_u_pro_controller_in_linux/) suggests that there is a `hid-nintendo` driver which can connect to the switch controller. 
  - [Guide getting a Wii U Pro Controller to work](https://www.linuxquestions.org/questions/slackware-14/guide-getting-a-wii-u-pro-controller-to-work-4175576590/). 
    Although I haven't tried it, it doesn't look like it will work, because it assumes that the BL connection works, which it didn't for me.
  - The last resort is to use the Mayflash adpater which can connect to any remote
 

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

- Frisbee that can be seen in the dark by using the reflective propoerties of stree-reflectors (cat's eyes)

- Simulation of particle dyanmics inspired from vid by [Reducible](https://www.youtube.com/watch?v=eED4bSkYCB8)

---

## 3D printer upgrades

- Modify Start GCode
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

## Skills to Learn

- Quantum Computing for programmers
- Learn [cpp](https://www.learncpp.com/)
- Learn dvorak
- Python ML for recognising digits
- Python ML for games using reinforcement learning
- [Functional Programming](https://mitpress.mit.edu/sites/default/files/sicp/full-text/book/book.html)
- Watch maths for ML
- Android programming
