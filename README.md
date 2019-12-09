# Theos IOS13 Intall Guide
How to install theos on ios 13 jailbreak

## Setup

Install PuTTY on windows and SSH into iphone [Tutorial on how to install PuTTY and SSH](https://www.reddit.com/r/jailbreak/comments/8wq55h/guide_how_to_ssh_into_your_device_once_it_has/)

Install Filza File Manager from Cydia 
Install Theos Dependencies from Cydia

## Installation Guide 
This installation guide will install theos.
1) SSH into the Phone and create 'opt' folder in root directory
> mkdir /opt

2) set directory > export THEOS=/opt/theos

3) inside the opt folder run git clone
> git clone --recursive https://github.com/theos/theos.git $THEOS

4) You need to download an sdk for your deivce and place it inside /opt/theos/sdks [sdk downloads for some versions](https://github.com/theos/sdks)

5) run > /opt/theos/bin/nic.pl
and check that the output is as follows
> NIC 2.0 - New Instance Creator
> ------------------------------
>  [1.] iphone/activator_event
>  [2.] iphone/application_modern
>  [3.] iphone/application_swift
>  [4.] iphone/flipswitch_switch
>  [5.] iphone/framework
>  [6.] iphone/library
>  [7.] iphone/preference_bundle_modern
>  [8.] iphone/tool
>  [9.] iphone/tool_swift
>  [10.] iphone/tweak
>  [11.] iphone/xpc_service
> Choose a Template (required):

## Making a tweak
This will show you how to create a simple tweak.
1) run > export THEOS=/opt/theos
2) run > /opt/theos/bin/nic.pl

3) run > cd /

4) select iphone/tweak e.g [10.] iphone/tweak type in 10

5) enter project name for tweak e.g 'besttweak'

6) enter package name e.g 'com.test.besttweak'

7) enter author name e.g 'john'

7) just click enter as no changes are needed

The project name of your tweak should now be in your root directory



