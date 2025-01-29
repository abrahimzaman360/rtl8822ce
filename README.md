
# Hypnotic Writing:

**(Warn):** Use it only if your wifi is not working correctly.  
On my system, Lunar Lubster (Ubuntu) wifi is working properly without doing anything below or else. Just continue on that.

**[Sorry]** I've sacrificed this card, after the screw which was holding it not moving out!  
And replaced it with Intel AX Series Wifi. **[Thanks]**  
Realtk's rtl8822ce 802.11 ac

## Story Behind How I Fixed My Wifi.

### Read My Story 
*Scroll Down if You don't wanna read my story, Read it if you like (:*

=> When I started my new laptop, I noticed that I was missing something important in life. What was that? It was Linux. After using Windows 11 for 1 month, I got tired of this trash. Then, I installed the monster of distros, **"Ubuntu"**. But  
=> Then, the next moment I saw glitches with my WiFi. I got so confused, I started searching on the internet about my chipset, especially Linux.org, but those tips didn't work. I tried many distros, but the same problem occurred, except for Mint. However, I don't like Mint for personal reasons. I love GNOME (: Sorry other DE users if you are... I got disappointed with Linux and after that, I reinstalled Windows 11...  
=> After all, something again happened to my brain, and I installed Ubuntu Kinetic Kudu. Same thing happened to me again, but this time, I said to myself to figure out the real problem and what was going on with the device. I started searching again for the solution. I saw many repos of Kernel Modules, but one repo solved my issue and...  
=> Initially, I installed it through the DKMS method but ran into another issue. Kinda frustrating and (: I started searching again on the internet "How to remove old instance of wireless kernel driver". One man from Linux.org replied to me, but he was busy or going somewhere. I continued querying on Google, etc.  
Then, on one Linux community page, I found a fix. It was a **1 Line Substitution Method** for commenting out a command in the Makefile of the driver. I was scared at first that something would happen to my laptop, but I'm never really scared of software issues! 
Instead of the DKMS method, this time, I used another method!

**One Liner by Me**  
*(Warning: If you're scared of this command, please enter each one before the AND operator):*

##### Method 1. One line - Command [May Override Current Drivers, Please Backup them]:
* ``` git clone https://github.com/juanro49/rtl88x2ce-dkms.git && cd rtl88x2ce-dkms && sudo sed -i 's/EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/#EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/g' ./Makefile && sudo make && sudo make install && sudo modprobe rtl88x2ce ```

-> Reboot and Done.

##### Method 2. How to Substitute MakeFile [Installation (Step by Step Method)]:
* ``` git clone https://github.com/juanro49/rtl88x2ce-dkms ```
* ``` cd rtl88x2ce-dkms ```
* ``` sudo sed -i 's/EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/#EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/g' ./Makefile ```
* ``` sudo make && sudo make install ```
* ``` sudo modprobe rtl88x2ce ```

-> Reboot and Done...
##### Unloading Kernel Module (if there is an problem or things didn't go correctly):
* ``` sudo modprobe -r rtl88x2ce ```



##### Resources Behind Wifi Fix:
* Kernel Module for Realtk Most Problmatic Chip *
* https://github.com/juanro49/rtl88x2ce-dkms
(Warning: For Me Above Methods Worked Well, if you installed another way, you might see multiple wifi instances, you can uninstall/unload that module and use my installation method).
  
## My Probe or Specs:
* https://linux-hardware.org/?probe=f84f8c068b

### Warning
This Workflow really helped me on my laptop. I'm not sure or responsible if it didn't work on your's.
