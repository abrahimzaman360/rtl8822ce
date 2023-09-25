# Use it only if your wifi is not working correctly.
On my system, Lunar Lubster (Ubuntu) wifi is working properly without doing anything below or else.
Just continue on that.



# Realtk's rtl8822ce 802.11 ac
Story Behind How I Fixed My Wifi.
 
## Read My Story [Scroll Down if You don't wanna read my story, Read it if you like (:]
=> When i started my new laptop, i noticed that i'm missing something important in life.
What was that it was Linux, After using Windows 11 for 1 Month. I got tired of this trash.
Then, I installed monster of distros " Ubuntu ", But

=> Then Next Moment I Saw Glitches of My WiFi.
I got so confused, i started searching on Internet about my chipset espacially Linux.org but those Tips didn't work.
I tried many distros but same except for Mint but I don't like Mint for Personal Reasons.
I Love GNOME (: Sorry Other DE User if You are...
I got disappointed with Linux and After that and Reinstalled Windows 11...

=> After all something again happened to my brain and I installed Ubuntu Kinetic Kudu.
Same thing happened to me again but this time,  I said to myself to figure out real problem and what's going on device.
I started searching again for the solution I saw many repos of Kernel Modules but One Repo got my issue and ...

=> Initially Installed it though DKMS Method but I got another issue, kinda issues and (:
I started searching again on internet " how to remove old instance of wireless kernel driver",
Linux.org's one man replied to me but he was busy or he's going somewhere, I again started querying on google etc.

then on one Linux Community Page I got a fix.
1 Line Substitution Method for Commenting Out a Command in Makefile of Driver.
I scared first that something will happen to laptop but i'm never really scared of software issues (: (: (;
Instead of DKMS method;
This time is used another method.
One Liner by Me (Warning: If you scare of this command please enter one by one each before AND Operator):
### One Line Command and Done [May Override Current Drivers, Please Backup them]:
* ``` git clone https://github.com/juanro49/rtl88x2ce-dkms.git && cd rtl88x2ce-dkms && sudo sed -i 's/EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/#EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/g' ./Makefile && sudo make && sudo make install && sudo modprobe rtl88x2ce ```

-> Reboot and Done.


### Resources Behind Wifi Fix:
* Kernel Module for Realtk Most Problmatic Chip *
* https://github.com/juanro49/rtl88x2ce-dkms
(Warning: For Me Other Method Worked Well Because You'll See 2 Wifi Instances by DKMS Method).

### How to Substitute MakeFile [Installation (Step by Step Method)]:
* ``` git clone https://github.com/juanro49/rtl88x2ce-dkms ```
* ``` cd rtl88x2ce-dkms ```
* ``` sudo sed -i 's/EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/#EXTRA_CFLAGS += -DCONFIG_CONCURRENT_MODE/g' ./Makefile ```
* ``` sudo make && sudo make install ```
* ``` sudo modprobe rtl88x2ce ```

-> Reboot and Done...
## Unloading Kernel Module aka Drivers:
* ``` sudo modprobe -r rtl88x2ce ```
  
## My Probe or Specs:
* https://linux-hardware.org/?probe=f84f8c068b

### Warning
This Workflow really helped me on my laptop. I'm not sure or responsible if it didn't work on your's.
