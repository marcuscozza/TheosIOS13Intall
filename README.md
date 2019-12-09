# Theos IOS13 Intallation Guide
How to install theos on ios 13 jailbreak
-tested version:
-``` 13.2.2 ```

## Setup

Install PuTTY on windows and SSH into iphone [Tutorial on how to install PuTTY and SSH](https://www.reddit.com/r/jailbreak/comments/8wq55h/guide_how_to_ssh_into_your_device_once_it_has/)

Install Filza File Manager from Cydia 
Install Theos Dependencies from Cydia

## Installation Guide 
This installation guide will install theos.
1) SSH into the Phone and create 'opt' folder in root directory
``` mkdir /opt ```

2) set directory ``` export THEOS=/opt/theos ```

3) inside the opt folder run git clone ``` git clone --recursive https://github.com/theos/theos.git $THEOS ```

4) You need to download an sdk for your deivce and place it inside /opt/theos/sdks [sdk downloads for some versions](https://github.com/theos/sdks)

5) run ``` /opt/theos/bin/nic.pl ```

and check that the output is as follows
```
 NIC 2.0 - New Instance Creator
 ------------------------------
  [1.] iphone/activator_event
  [2.] iphone/application_modern
  [3.] iphone/application_swift
  [4.] iphone/flipswitch_switch
  [5.] iphone/framework
  [6.] iphone/library
  [7.] iphone/preference_bundle_modern
  [8.] iphone/tool
  [9.] iphone/tool_swift
  [10.] iphone/tweak
  [11.] iphone/xpc_service
 Choose a Template (required):
```
## Making a tweak
This will show you how to create a simple tweak. using SSH and filza
1) run ``` export THEOS=/opt/theos ```
2) run ``` /opt/theos/bin/nic.pl ```
3) run ``` cd / ```

4) select iphone/tweak e.g `[10.] iphone/tweak` type in 10

5) enter project name for tweak e.g `besttweak`

6) enter package name e.g `com.test.besttweak`

7) enter author name e.g `john`

8) after you enter your author name just click enter as no changes are needed

The project name of your tweak should now be in your root directory and their should be 4 files which are `Makefile`, `Tweak.x`, `control` and `(tweakname).plist`.

9) open filza and go to root and then your newly created tweak folder and check that all 4 files are their.

10) click edit top left and select Makefile and click more bottom right and select open with text editor.

11) At the top of the file type in
``` ARCHS = armv7 arm64 ```
and click save then cancel then done

12) repeat step 10 but instead select Tweak.x, you must select all and delete, this is where you can code for your tweak, i have attached a sample tweak which will make the dock transparent.
```
%hook SBDockView
-(void)setBackgroundAlpha:(double)arg1{
%orig(0.0);
}
%end
```
and click save then cancel then done

13) using filza travel to this directory /opts/theos/bin/, and find `fakeroot.sh` file and open it like in step 10 and at the bottom you should see
``` $fakeroot $cmd ``` you must change it to
``` $fakeroot perl /opt/theos/bin/$cmd ```
and click save then cancel then done

## Compile and install a tweak
This will show you how to compile and install your tweak which will show up in cydia.
1) you must cd into your tweak directory
``` cd /`tweakname` ```
2) run 
``` export THEOS=/opt/theos ```
3) run
``` make package  ```
4) run
``` make install ```
your device will respring and your tweak will be active.

## Uninstall a tweak
all the tweaks you install will show up in cydia under `Installed`, simply search for your tweak name and click modify then remove.
