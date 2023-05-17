Droidian on Moto G Power (sofia)
========

Droidian is a GNU/Linux distribution based on top of Mobian, a Debian-based distribution for mobile devices. The goal of Droidian is to be able to run Mobian on Android phones.<br />

# Phosh
<img src="https://deb.arpio.ca/droidian0.png" width="100" height="200"/> <img src="https://deb.arpio.ca/droidian1.png" width="100" height="200"/> <img src="https://deb.arpio.ca/droidian2.png" width="100" height="200"/> <img src="https://deb.arpio.ca/droidian3.png" width="100" height="200"/>

# Cutie-Shell
<img src="https://deb.arpio.ca/cuties1.jpg" width="100" height="200"/> <img src="https://deb.arpio.ca/cuties2.jpg" width="100" height="200"/> <img src="https://deb.arpio.ca/cuties3.jpg" width="100" height="200"/> <img src="https://deb.arpio.ca/cuties4.jpg" width="100" height="200"/> 

## THE INSTRUCTIONS BELLOW WILL WIPE ALL THE DATA ON YOUR DEVICE

# Default password: 1234

## You have stock Android10
 * Continue in the Prepare section

## You have stock Android11
 * You need to download the official Android10 firmware for example from here: https://mirrors.lolinet.com/firmware/motorola/sofia/official/
 * You need to extract the vendor image from the official firmware.

## Prepare
 * You need unlocked bootloader.
 * Go to Settings->About phone and tap the Build number 7 times
 * Got to Settings->System->Advanced->Developer options and activate USB debugging
 * Backup all your data, the installation steps will wipe everything in the userdata partition.
 * Using adb for example: `adb pull /dev/block/by-name/userdata`
 * Make sure you can boot both slots a & b

## Installation
 * Download the latest build here: https://github.com/arpio23/droidian-images/releases
 * Unpack the zip file
 * Boot to fastbootd:
   <pre><code>adb reboot fastboot</code></pre>
 
 * ANDROID11 BASE SYSTEM ONLY:
   Flash the previously extracted vendor image from official Android10 firmware.
   <pre><code>fastboot flash vendor path/to/vendor.img</code></pre>
   DO NOT REBOOT
   
 * Using fastboot flash following partitions:
    <pre><code>fastboot flash boot data/boot.img
   fastboot flash userdata data/userdata.img</code></pre>
 * Reboot to system and "DO NOT PRESS THE POWER BUTTON WHEN SCREEN IS BLACK or BLANK, BE PATIENT"
 * If you have a Moto G Power (sofia) and the instructions did not work, create an issue: https://github.com/arpio23/droidian-images/issues
 * Find the solution here: https://t.me/DroidianLinux

## Mobile Data set up on PHOSH
 * You successfuly booted Droidian
 * Go to Setteings->Mobile Network and activate Mobile data
      Add the Acces Point for your provider
 * Using ssh or the terminal app on the phone:
      <pre><code>cd /usr/share/ofono/scripts
      ./deactivate-context 1
      ./set-context-property 0 AccessPointName YOUR_AP_NAME
      ./activate-context 1
      </code></pre>
* Reboot
* Go to Setteings->Mobile Network and toggle Mobile data

## Mobile Data set up on CUTIE
* Just set your apn in the settings app
