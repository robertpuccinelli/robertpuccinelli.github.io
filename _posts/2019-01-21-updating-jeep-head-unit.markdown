---
layout: single
title:  "Build Your Own: Automotive Head Unit"
excerpt: "A DIY alternative to modern commercial infotainment systems in a 2001 Jeep Wrangler (TJ)."
category: build
tags: [build, jeep, electronics]
comments: true

toc: true
toc_sticky: true

classes:
  - text-justify

introduction:
  - image_path: /assets/images/posts/170704_CapturedDNA.PNG
    url: "/assets/images/posts/170704_CapturedDNA.PNG"
    excerpt: "Small protein spots captures various DNA sequences from solubilized microarray."

Hardware:
  - image_path: /assets/images/posts/190121_VehicleInfotainment.png
    url: "/assets/images/posts/190121_VehicleInfotainment"
    excerpt: "Graphical depiction of implemented infotainment system."

software:
  - image_path: /assets/images/posts/170704_Win98.jpg
    excerpt: "A bit outdated."
    url: "/assets/images/posts/170704_Win98.jpg"
  - image_path: /assets/images/posts/170704_DeRisiArrayMaker.png
    excerpt: "Software pulled from cached site."
    url: "/assets/images/posts/170704_DeRisiArrayMaker.png"
  - image_path: /assets/images/posts/170704_ArrayMaker.png
    excerpt: "ArrayMaker screenshot."
    url: "/assets/images/posts/170704_ArrayMaker.png"
  - image_path: /assets/images/posts/170704_DMC18x2.jpg
    excerpt: "Galil programming reference."
    url: "/assets/images/posts/170704_DMC18x2.jpg"
  - image_path: /assets/images/posts/170704_Gemini.jpg
    excerpt: "Gemini servo reference."
    url: "/assets/images/posts/170704_Gemini.jpg"

CAD:
  - image_path: /assets/images/posts/170704_Arrayer_BlockBody_Solid.png
    excerpt: Pin block body - solid.
    url: "/assets/images/posts/170704_Arrayer_BlockBody_Solid.png"
  - image_path: /assets/images/posts/170704_Arrayer_BlockBody_Xray.png
    excerpt: Pin block body - X-ray.
    url: "/assets/images/posts/170704_Arrayer_BlockBody_Xray.png"
  - image_path: /assets/images/posts/170704_Arrayer_BlockHead.png
    excerpt: Head for block body.
    url: "/assets/images/posts/170704_Arrayer_BlockHead.png"
  - image_path: /assets/images/posts/170704_Arrayer_PrintingArm.png
    excerpt: Printing arm.
    url: "/assets/images/posts/170704_Arrayer_PrintingArm.png"
  - image_path: /assets/images/posts/170704_Arrayer_CalibratorArm.png
    excerpt: Calibrator arm.
    url: "/assets/images/posts/170704_Arrayer_CalibratorArm.png"
  - image_path: /assets/images/posts/170704_Arrayer_CalibratorMount.png
    excerpt: Calibrator mount.
    url: "/assets/images/posts/170704_Arrayer_CalibratorMount.png"
  - image_path: /assets/images/posts/170704_Arrayer_DelrinBlock.png
    excerpt: Delrin block.
    url: "/assets/images/posts/170704_Arrayer_DelrinBlock.png"
---

**PURPOSE:**  
<br>
Provide a DIY alternative to expensive commercial head units. The following in-depth guide is designed to allow anyone to rebuild their system in the event of a break-in or upgrade their system at their own discretion. I would like to thank my insurance company, AAA, for supporting this rebuild by allowing me to cash settle to repair/replace my system after it was damaged by theft. Overall benefits of this system include:  
<br>
  **A.** breaking the system down into individual modules that are less expensive to replace in the event of theft,  
  **B.** modernizing technologically outdated systems,  
  **C.** allowing virtually unparalleled customizability of an infotainment system.  
{: .notice--info}


## Introduction

The automotive head unit is the interface for the infotainment system of a vehicle and is often a prime target for theft due to retained aftermarket value. In older vehicles, it was primarily the stereo. In newer vehicles, it has transformed into a multi-functional touch screen interface for audio, navigation, vehicle diagnostics, rearview cameras, and even portals for an Android or Apple phone.

Security features have been implemented in some units that make them not worth stealing such as detachable face plates (stereo rendered inoperable and therefore unsellable) or complex integration with a vehicle (rendering the system useless in a different vehicle). These features, in addition to other technologies such as universal phone pairing, have supposedly resulted in a decline of stereo theft. Obviously, as I can comment firsthand, theft still exists.

If you are in the market for a new head unit, there are plenty of nice (or budget) commercial systems available and there are also DIY options available which can give you a high degree of customizability at a competitive price. If a DIY system interests you, I would recommend that you familiarize yourself with what options are available. What I have written here is a single build and, given that technology is always advancing, it could be obsolete by tomorrow. That being said, this will still be decades better than some stock units. The following guide is written with sufficient detail that anyone with a TJ Wrangler will be able to follow the guide and end with identical results. Owners of different vehicles may require a few modifications.

What we're building here is a system with many of the conveniences of modern vehicles in a technologically challenged vehicle:
- Touch screen interface (Nexus 7, 2013)
- Built-in navigation (Nexus 7, 2013)
- Android Auto + Apple CarPlay integration (hardware dongle)
- Stereo integration (Digital-to-analog converter)
- FM radio (Software defined radio tuner app + hardware receiver)
- Backup camera (Software app + camera hardware)
- OBDII Interface (Software app + OBDII module)
- Microphone
- Protective cover (Shield the unit from the elements when the top is down and possibly hide the system from potential thieves?)

For those who are fortunate enough to still have their stereos, I hear that beautiful mornings can lead to an ugly evening.

<figure class="half">
  <a href="/assets/images/posts/190121_Sunrise.jpg"><img src="/assets/images/posts/190121_Sunrise.jpg"></a>
  <a href="/assets/images/posts/190121_StolenStereo.jpg"><img src="/assets/images/posts/190121_StolenStereo.jpg"></a>
  <figcaption><center>Morning and evening of November 26.</center></figcaption>
</figure>

## Parts List and Files

This section encompasses everything that is required to build the system to give you an overview of what is involved. After listing the components, each section will examine why certain components were chosen in greater detail. Although software files are listed below, they are largely for my own reference of what was used in the event that I have to rebuild the system. **I strongly encourage others to download files from the original provider** and not from this page. There may be more recent versions available and you can't be certain that these files haven't been tampered with. The links to the original provider are listed. Hardware is listed first because the software is largely dependent on the employed hardware.

### Hardware Description and Rationale

{% include figure image_path="/assets/images/posts/190121_VehicleInfotainment.png" caption="Graphical depiction of implemented infotainment system." %} {: .align-center .width-75 .text-center}

We'll work our way from left to right in the figure above. The star of the show is the Nexus 7, 2013 edition. It is not the most advanced tablet in the market, but the screen has virtually a perfect form factor that matches a double DIN head unit and it has some of the most extensive kernel options available. We'll be running Timur's Kernel v4.0 to integrate the tablet into the Jeep as permanent hardware.

To assert the tablet as the host of the system, all connections must be routed through the on-the-go (OTG) adapter. From here, a special Y cable connects to the powered USB hub to provide the tablet with a high amp supply and to route data. This USB hub is powered by a 12V line that is only active when the ignition is on. This allows the tablet and peripherals to enter a deep sleep / off state when there is no auxiliary power - saving your vehicle's battery when off.

From here, the peripherals are completely user dependent and there is quite a bit of flexibility in options. Not everyone will be interested in having Android Auto / Apple CarPlay, OBDII diagnostics, or a microphone in their vehicle. I did this mainly because I could.

The OBDII unit sits in your vehicle's OBDII port and can transmit data directly to the Nexus 7 via bluetooth. The OBDII port is still powered when the vehicle is off, so a minor modification will be made to the bluetooth unit to only power it when auxiliary power is available.

The radio receiver connects to the USB hub and is controlled by an app on the tablet. It is quite capable of receiving all FM channels and more; however, it is unable to receive AM broadcasts. The transmission frequency for most AM stations is too low for this unit to detect, but other units (such as a HAM upconverter) should make AM accessible if desired. This receiver employed here connects to a F to SMA adapter, which will allow you to plug the antenna into the unit. I was unable to find a Motorola to SMA adapter, so we'll have to modify the adapter a bit to make things work.

A few video cards are usable with Android 6.0.1, but I went for what I thought was the simplest. A subset of USB video cards (UVC) should not require any drivers on any system (including Windows 2000). A lot of cheap cards say they are UVC but still require drivers, which defeats the purpose. Try to avoid those ones to make your life easier. The video card is connected to the USB hub and also has its power switched by an automotive 12V relay. Whenever the reverse gear is engaged, the reverse wire is brought to 12V. When this happens, the relay will power the UVC, which will then begin transmitting video data directly to the Nexus 7. Furthermore, the backup camera also taps the 12V line that power the reverse lights, so the camera will be powered simultaneously.

The microphone isn't anything special. In this case, it's just a USB mic with an integrated driver. A microphone that plugs into the 3.5mm jack on the tablet might work as well. Alternatively, there are bluetooth microphones that might be a better choice.

The phone dongle is a bit of an experiment. This unit should allow for Android Auto or Apple CarPlay to be retrofitted onto older head units, but no one has done it with a Nexus 7 as far as I'm aware of. This dongle should allow the phone to be directly controlled by tablet. I previously installed QuickCharge 3 USB ports in my Jeep for rapid charging of mobile devices. I currently plan to connect the data pins from one of the ports directly to the phone dongle so that the phone can charge quickly while also supporting connectivity.

Last but not least is the digital to analog converter (DAC). This takes digital audio signals from the Nexus 7 and converts them into an analog signal that is sent to the vehicle's speakers. Some DACs have been problematic in builds with microphones for unclear reasons. I think some DACs have a microphone input port that change the DAC from being an output device to being an input/output device. The 6.0.1 Android OS might only support one input at a time, so the standalone microphone input might be disabled as long as the I/O DAC is connected. To connect the DAC to the speakers, RCA lines will be installed for the left and right audio channels. The Nexus 7 only has left and right outputs - an amplifier or some other system will be required for additional channels like front and back.

### Hardware Components
The Amazon Affiliate links below help fund future Build Your Own projects at no cost to you. If you do not wish to support this work, the model number is provided for your reference.
{: .notice--primary}

| Item | Model | Provider | Cost |
|------|-------|----------|------|
| Early TJ Double Din Bezel | Metra 95-6549 70-1817 | [eBay](https://www.ebay.com/itm/JEEP-WRANGLER-TJ-1997-2002-DOUBLE-DIN-DASH-BEZEL-RADIO-STEREO-MOUNTING-KIT/192628453170?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2060353.m2749.l2649) | $79.98 |
| Tablet | Nexus 7, 2013 | [Amazon](https://amzn.to/2G2NSuI) | $75.02 |
| Powered USB Hub | Kootion H6C22 | [Amazon](https://amzn.to/2Wmdto8) | $19.99 |
| Phone Link Dongle | Carlinkit HW01-01 | [Amazon](https://amzn.to/2TfegW7) | $60.99 |
| USB DAC | Signstek Mini USB DAC | [Amazon](https://amzn.to/2MB0ryw) | $21.99 |
| Radio Receiver | NooElec NESDR Smart | [Amazon](https://amzn.to/2Ue3wYa) | $23.95 |
| USB Video Capture Card | EasyCAP FBA_UVC Black | [Amazon](https://amzn.to/2G2RmgM) | $9.94 |
| Backup Camera | DohonesBest 4350450562 | [Amazon](https://amzn.to/2FRWk0N) | $18.99 |
| USB Microphone | MAONA AU-410 | [Amazon](https://amzn.to/2sNV5XK) | $14.99 |
| OBDII Reader | Panlong PL-B02 | [Amazon](https://amzn.to/2RWmqGs) | $10.98 |
| USB OTG Adapter | Cablecc B01KCBSKSA | [Amazon](https://amzn.to/2MEhmAA) | $6.30 |
| USB Y Cable | SaiTech B00VV24L7E | [Amazon](https://amzn.to/2Wnr26I) | $4.99 |
| SMA Coaxial Adapter | DHT AD012 | [Amazon](https://amzn.to/2TingcT) | $5.50 |
| Antiglare Screen Protector | BoxWave bw-862-4841-0 | [Amazon](https://amzn.to/2sLInZD) | $9.95 |
| RCA Plugs, 1.5ft | Monoprice 105346 | [Amazon](https://amzn.to/2Sb7Utx) | $6.64 |

Total cost of all hardware for a 2001 TJ installation at the time of the build: **$370.20**. (Note: I already had a Nexus 7. The $300 cost and reuse of old tech helped motivate this project.)

If you already have a vehicle with a double din bezel and aren't interested in having Android Auto or Apple CarPlay features, you could reduce the cost to $229.23. If you don't have 12V automotive relays or a method of connecting loose ends of wires, those components will incur a small additional cost.

### Software modules

Although there is a high degree of flexibility in hardware, it is greatly outmatched by that of the software. I'll list a few applications that I believe are essential for my use case and will leave all other remaining preferences to the reader. None of the following modules are required to implement an Android head unit and it may be worth your time to explore other options.

_**Automotive Kernel**_<br>
First and foremost, I chose to build the head unit off of [Android 6.0.1 with Timur's v4.0 kernel](https://www.reddit.com/r/timurskernel/comments/51lhgf/v40_for_android_601/). This setup allows the Nexus 7 to charge while also acting as the OTG host for the USB peripherals. It also includes some nice features for an automotive setting such as automatic deep sleep when the ignition is off or automatically launching a backup camera when the reverse gear is engaged. Timur provides instructions on how to install everything, but I will go into a bit more detail in the build guide below because some things were not readily apparent to me. Potential problems and workarounds with this method are listed in the [Pitfalls and Solutions](https://www.reddit.com/r/timurskernel/comments/5elxa7/pitfalls_and_solutions/) thread.

_**Blackout Screen**_<br>
It may be a bit silly to list this function as a second priority, but it is somewhat important to me. Before my previous head unit was stolen, there were many times when I did not need it powered or preferred to keep the cab dark. The tablet is currently set to never sleep when the ignition is on, primarily because the power button is not accessible behind the bezel. Since it never sleeps, the interior is always illuminated. I implemented a gesture control to launch the [BlackScreen](https://play.google.com/store/apps/details?id=net.jomyut.blackscreen) app when a specific spot on my tablet is double tapped.

_**Clean Interface**_<br>
It's important to me that I have a clean home screen with no bloatware. If I'm driving, I don't accidentally want to tap the (in my opinion) useless Google Search bar. I also want to maximize the real estate of the screen, so no dock. As you might observe from this website, I prefer minimalistic designs. I found that the [Evie Launcher](https://play.google.com/store/apps/details?id=is.shortcut) was perfect for my use case and would highly recommend it. I was able to clear the home screen completely and only have a large clock and essential app shortcuts. Most of the settings in the launcher were disabled by choice.

_**Vehicle Dashboard**_<br>
I'm not completely settled on the dashboard yet, but I'm currently evaluating [AutoMate](https://play.google.com/store/apps/details?id=is.shortcut). It's nice because it has separate features on different pages, but transitioning between pages often takes me multiple attempts. Alternatives include [Car dashdroid](https://play.google.com/store/apps/details?id=com.nezdroid.cardashdroid) or [Car Launcher](https://play.google.com/store/apps/details?id=com.autolauncher.motorcar.free). The benefits of a system like this is that it can cleanly organize navigation, phone call, media operations, and OBDII readouts. I'll have a stronger opinion when I get to installing the tablet.

_**Other Modules**_<br>
Radio Tuner: [SDR Touch](https://play.google.com/store/apps/details?id=marto.androsdr2)<br>
OBDII Readout: [Torque Lite](https://play.google.com/store/apps/details?id=org.prowl.torquefree)<br>
Gesture Control and Remove Navigation Bar: [Navigation Gestures](https://play.google.com/store/apps/details?id=com.xda.nobar)<br>
Pop Up Navigation Bar: [Custom Navigation Bar](https://play.google.com/store/apps/details?id=com.navigation.bar.customize.soft.keys)<br>
Backup Camera : VCam2 (Shipped with Timur's Kernel) [Alternative](https://forum.xda-developers.com/devdb/project/dl/?id=26261)<br>
Media Controls on Navigation Bar: [cliffeed mod](https://www.reddit.com/r/timurskernel/comments/4hdc56/mediavolume_buttons_for_navbar_marshmallow/)<br>
Phone Dongle App: [Carlinkit Autokit.apk](http://www.carlinkit.com/autokit.apk)

The following files are listed in the event that the [files from Timur's Reddit thread](https://www.reddit.com/r/timurskernel/comments/51lhgf/v40_for_android_601/) are lost. I would advise you to not download these if the official versions are still available:<br>
[TWRP 3.0.2-0 Debian](https://app.box.com/s/pnc461hr9023na6qx3ln1kad31b8owdc)<br>
[Timur Kernel N7 2013 v4.0 Final Flo Debian](https://app.box.com/s/mfwx5jfm83q8pzv1yvft344p6kc76yp0)<br>
[SuperSU v2.76](https://app.box.com/s/72vhwf94bd7n8jhxp262v6nuom1tlxvy)<br>
Also required is the factory MOB30X Android image.

## Build Guide

The build guide is quite extensive - we'll cover the software aspect first before the hardware. The primary software guide can be found on [Reddit](https://www.reddit.com/r/timurskernel/comments/51lhgf/v40_for_android_601/), the following is largely a reprint of what is there in addition to a few other details. Timur's original commentary is _italicized_ and additional commentary I included is written in normal font. The TJ natively supports a 1.5 DIN (who does that?) and may require some trimming of the dash to place the Nexus 7. Since the Nexus is so thin, it might not be required but be prepared.

### Installation of Android Tools

Before your system can push software from your computer to the Nexus, some development tools have to be installed on your computer. ADB allows debugging of Android over USB and fastboot allows you to unlock the bootloader and push custom software onto the unit. Either Google search how to install those tools or run the following on OSX:
>brew cask install android-platform-tools

Timur's instructions:<br>
_Now enable the "USB debugging" feature on your Android device. In order to do so, open Settings and then open "Developer options"._

_If you cannot find "Developer options" in the list, go to "About tablet" and click the "Build number" five times in a row, until you see a toast message, telling you that: You are now a Developer. Now leave "About tablet" and you should be able to see and open "Developer options"._

_Under "Developer options" you should now be able to enable "USB debugging". While you are in "Developer options", you may also want to enable "Stay awake". This feature is useful, if you want to use the FI-mode feature._

_With your tablet connected to the PC, you should now be able to open a command shell on your PC and run the following commands. This is for testing connectivity only:_

>adb shell date

_This should display the current time and date of your Android device on your PC. If this doesn't work, try the following:_

>adb devices

_This should show the "List of attached Android devices" in the command shell on your PC. If this does not show at least one Android device (with a serial number and a name), you should try unplugging and reconnecting the USB cable. You may need to confirm ADB connectivity in a dialog box on your Android device. If you are not able to establish ADB-over-USB connectivity, google for "adb windows" and/or "adb windows usb drivers". And possibly install/update the required USB drivers. Continue only, if the adb tool is working properly._

### Unlocking the Bootloader

Timur's instructions:<br>
_If your tablet's bootloader is not yet unlocked, you need to unlock it now. This can be done in two quick steps by running the following commands in the command shell on your PC:_

>adb reboot bootloader

_And then, when the tablet shows the bootloader screen, run:_

>fastboot oem unlock

_NOTE: Unlocking the bootloader will fully wipe your device. You need to confirm the unlocking procedure on the device screen. As long as you don't lock your bootloader again, you only need to do this once._

### Kernel installation

Download the following files:
* Android factory image
* TWRP images
* SuperSU ZIP
* Timur's kernel ZIP

The factory image, TWRP recovery tool and Timur's kernel will be dependent on the platform you have. The 2013 Nexus with WiFi will use the Flo variants of the files and the LTE version will use the Debian variants of the files. The following will be written specifically for the flo installation.

Unzip Timur's kernel. Inside the ZIP are two folders of interest - "timur-kernel-n7-2013-v4.0-final.zip" and "timur-pem-update-v4-b107-2017-01-06.zip". Unzip the kernel directory to access the USB host and services ZIPs. Both of those and the pem-update will be uploaded to the Nexus 7 in their ZIP format. These files will be installed onto the Nexus first before the SuperSU zip is installed.

Returning to Timur's instructions:<br>
_Here I describe how you can upgrade your tablet to Android 6.0.1 MOB30X, install Timur's Kernel v4.0 as well as root, without losing any apps or settings - and do so in under 20 minutes. To do this, your tablet bootloader needs to be unlocked once. If you already have a rooted Android 6.0.1 MOB30X with TWRP installed on your tablet, the kernel installation can be done in just a few minutes. In this case, reboot into TWRP and continue with step 4._

1. _Unzip the target Android 6 MOB30X factory image on your PC. In order to prevent the factory image installation from wiping the data partition of your tablet (if you want to keep your installed apps, personal settings and custom data), you need to edit your flash-all script (.sh or .bat, depending on what OS you are using on your PC). To keep your apps and data, remove the "-w" parameter from the last line. However, if want to delete everything on the tablet (wipe) and fully start from scratch, do not modify the flash-all script (keep the "-w" parameter in). Before you continue, this is your last chance to create a full device backup of your tablet. For instance, you can create a full device backup in TWRP recovery._

2. _To install the factory image, connect the tablet to a PC via USB and run the (modified) flash-all script. The installation process will take a couple of minutes. This is IMPORTANT: You need to watch the tablet screen closely, because you need to prevent the tablet from booting into Android automatically at the end of the installation process. As soon as you see the tablet screen turn off, you need to quickly press power + vol-down and keep both buttons pressed for about 15-20 seconds. This will abort the boot process and instead, the tablet will return to the bootloader menu. You need to keep pressing the two buttons until you actually see the bootloader menu. This is when you can release the buttons. The point of all this is, to install TWRP and SuperSU BEFORE the newly installed Android system boots up for the first time._

3. _With the tablet in bootloader (you may need to disconnect/reconnect the PC-USB connection), you can now install TWRP recovery. You always need to do this, because flash-all will overwrite a previous instance of TWRP. To continue, enter in a command line window on your PC: "fastboot flash recovery twrp-3.0.2-0-flo.img" (if you have the LTE model, use the img-file of the deb variant). When done (only a second later), you should be able to launch the newly installed TWRP from bootloader menu. Use the volume keys to select "recovery" and then hit the power button to launch TWRP._

4. _With TWRP recovery running, the tablet should now appear as a USB drive on your PC. This lets you copy the three zip archives required for the next step over: timur-services, timur-usbhost and SuperSU. Make sure these three files are available on the tablet's internal sdcard. Then install the three zip files (timur-services + timur-usbhost before SuperSU!), using the TWRP on-screen UI. Note that whenever you update the kernel (usbhost), you will also need to re-install SuperSU afterwards. - OK, done. You can now restart system and boot into Android OS._

RRP:<br>
The installation of the ZIPs was a bit unfamiliar to me when I started, so I'll explain it in a bit more detail. In your terminal, change directories until you're where your ZIP files are located. These ZIP files are outlined in the first two paragraphs of this section.

To transfer the files, run the following command for each ZIP:
> adb push {insert-filename-here}.zip /sdcard/

Now, all of the files should be located on the tablet in the /sdcard/ directory. On the tablet, select the Install Package button and navigate to the directory. Starting with the two ZIPs from Timur's kernel, select the file and install one at a time. These ZIPs failed the checksum of the installation when I tried, so unchecking that option before installing seems to work. After Timur's ZIPs, repeat with SuperSU.

Afterwards, in order to allow the Nexus to boot automatically when powered (say the battery dies after sitting in an idle vehicle for a few months), run the following command:
> fastboot oem off-mode-charge 0

This can be done at anytime as long as the Nexus is in the fastboot menu.

### Post installation

Now that the core OS is in place, a few small features can be implemented for seamless use of the device.

Timur's instructions:<br>
- _On first boot after installation: Do not immediately open PowerEventMgr. Instead, let the system rest in Launcher for a minute. You should see a SuperSU permission dialog show up for PowerEventMgr (PEM). Grant root access to PowerEventMgr. You can now open PowerEventMgr and, for instance, enable FI-mode and fast charging._

- _VCam2 app will be installed (or updated) when you launch PowerEventMgr and click the "Launch VCam [Exec]" button. If you intend to use VCam2, you should click this button once, every time you have installed or upgraded the kernel (usbhost installer) via recovery system. Launching VCam2 for the first time will bring up a SuperSU permission dialog. It is necessary to grant VCam2 root permissions._

- _It is also possible to install VCam2 manually, by opening VCam2.apk from the /sdcard/ folder (say, using a file manager app). Once VCam2 has been installed (or updated), the file /sdcard/VCam2.apk can be deleted._

- _It is suggested you disable SuperSU toast messages for PowerEventMgr and VCam2. To do so, open SuperSU app, select PowerEventMgr and change the Notifications setting from "Global defaults" to "Disabled". Hit the check mark to store the modified settings. Now do the same for vcam2. And hit the check mark again to store the modified settings._

- _You need to disable Android OTA updates. If you allow an Android OTA to update your system, the kernel, the custom recovery and SuperSU will be removed. Do this: Long press the notification (i-icon) and block, then disable it in app settings. More:_
  [https://www.reddit.com/r/timurskernel/comments/4appwx/anyone_know_how_to_remove_the_android_update_is](https://www.reddit.com/r/timurskernel/comments/4appwx/anyone_know_how_to_remove_the_android_update_is)

- _In order to use PowerEventMgr (PEM) Wakeup-screen, the Android lock-screen must be disabled (see: Security)._

- _You probably want to enable: Settings / Developer options / Stay awake (Screen will never sleep while charging)._

- _You can view the kernel identification string under: Settings / About. It should now say "USBhost..."._

- _You can view the version info and build number at the bottom of the PEM activity._

- _If your system works well, re-boot into TWRP recovery mode and create a new full backup to a USB flash drive (connected via OTG cable)._

- _Keep all of your installer files, including the correct variants of TWRP and SuperSU, in a save place._

RRP:
Now that everything is set, go ahead and install your desired Android apps and customize your system as desired. My preferred applications are outlined in the "Software Modules" section before the build guide begins.

### Hardware installation
