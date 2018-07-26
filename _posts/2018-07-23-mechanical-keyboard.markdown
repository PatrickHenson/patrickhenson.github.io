---
layout: post
title: "Custom DZ60 Keyboard Build"
tags: [ keyboards ]
---

## Why

It's not as convenient as buying an 'overpriced' keyboard and certainly not cheaper.

## Usefull resources

* [medium article](https://medium.com/@clmyles/building-a-60-keyboard-a-dz60-build-guide-679e98083221)

* [qmk_firmware documentation](https://docs.qmk.fm/#/)

* [qmk_firmware keycodes](https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md)

## Build Process

### Parts

* DZ60 PCB

* Gateron Green Switches

* Black Aluminum Case

* Vortex Doubleshot White/Black PBT Keycaps

### Test the DZ60 PCB

Prior to soldering, I tested the PCB using the [keyboard tester website](http://www.keyboardtester.com/) and a pair of tweezers to confirm that each individual key registered.  This also allowed me to become familiar with the soldering point locations.

### Determine switch layout



### Place stabilizers



### Solder switches



### Mount



### Add keycaps

Installing keycaps is extremely simple.  Line up the keycap over the appropriate switch's stem and firmly press down.  

I originally added the keycaps and used the keyboard sitting on the bubble wrap it shipped in, since the case I ordered arrived a week later than the rest of the parts.  Once the case arrived, I pulled the switches covering the mounting holes.

## Program and Flash

I personally used qmk_firmware to compile and flash a custom layout to the keyboard.  The process is fairly straightforward

Other methods, such as using [qmkeyboard.cn and qmk_toolbox](https://medium.com/@armno/customizing-dz60-keyboard-firmware-e6ad7222288f) can be used as well.


Grab the [qmk_firmware repo](https://github.com/qmk/qmk_firmware) from GitHub and install the necessary dependencies.

```
# Clone repository
git clone https://github.com/qmk/qmk_firmware.git

# Run script to install the necessary dependencies
cd qmk_firmware
sudo util/install_dependencies.sh

# Test compiling and flashing the default profile
# The make instruction uses the following pattern: <keyboard>:<keymap>:dfu
sudo make dz60:default:dfu
```

If the message, "Error: Bootloader not found. Trying again in 5s.", is displayed the device isn't recognized.  To force it to register, unplug, and plug back in while holding the <space> + <b> keys.  Some DZ60 PCBs have a reset pin, however, the USB-C version doesn't appear to have this feature.

After testing the ability to flash the key mapping, I created my own using my prefered Fn layout and moved the RGB backlighting and LED settings to the Fn-2 layer.  My custom key map can be found on [GitHub](https://github.com/PatrickHenson/dz60_layout).

```
# Copy the key map into qmk_firmware
cp keymap.c /qmk_firmware/keyboards/dz60/keymaps/custom_keymap

# Compile and flash the key mapping
sudo make dz60:custom_keymap:dfu
```
