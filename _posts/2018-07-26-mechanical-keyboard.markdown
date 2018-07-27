---
layout: post
title: "DZ60 Keyboard Build"
tags: [ keyboards ]
---

<img src="/images/dz60_build/finished.jpg" />

It's not as convenient as buying an assembled mechanical keyboard and certainly not cheaper.  What I did get was the ability to custom program the function layers, choose the parts I wanted, and the ability to say "I made that."

{{ post.excerpt }}

## Useful Resources

* [medium article](https://medium.com/@clmyles/building-a-60-keyboard-a-dz60-build-guide-679e98083221)

* [keyboard tester](http://www.keyboardtester.com/)

* [qmk_firmware documentation](https://docs.qmk.fm/#/)

* [qmk_firmware keycodes](https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md)

## Build Process

### Parts

#### DZ60 PCB, Gateron Green Switches, Stainless Steel Plate, Stabilizers

By using a DZ60 I was able to select a USB-C connector and will be able to program it with my desired layout.  I chose the 60% profile since I daily drive a **Vortex Pok3r**.  Anytime I switch to a 'normal' keyboard I end up mashing the caps lock and random keys in an attempt to use my programmed settings.

My other boards use Cherry MX-Clear switches, which are my current favorite.  For this build, I choose to use Gateron Green switches in an attempt to cut cost and test out clicky switches.  They're different, but feel pretty good so far.

I also used the plate and stabilizers that came in the kit rather than ordering custom or original Cherry parts.  I'd consider sanding and painting the plate to customize it further in future builds.  The stabilizers don't feel much different than the ones on my other boards and I expect them to smooth out over time as they break in.

#### Black Aluminum Case

I like the weight of a metal case, however, the one I ordered doesn't take advantage of the DZ60's under glow.  There are dozens of other cases in a range of materials (aluminum, acrylic, wood, plastic, etc) choose from depending on your priorities.

#### Vortex Doubleshot White/Black PBT Keycaps

It took a while to find the right keycaps, but I'm extremely pleased with the quality and love how they look and feel.

#### Cost Breakdown

| ITEM | PRICE |
| ---- | ----: |
| DZ60 Kit | $75.20 |
| Case | $48.78 |
| Keycaps | $39.00 |
| **TOTAL** | **$162.98** |


### Unpack 

The kit was first to arrive!  Which is nice since you can't do much without it.  Also pictured is my **Vortex Pok3r** that I use daily at work.

<img src="\images\dz60_build\kit_package.jpg" />

<img src="\images\dz60_build\kit_unpacked.jpg" />

### Testing the DZ60 PCB

Prior to soldering, I tested the PCB using the [keyboard tester website](http://www.keyboardtester.com/) and a pair of tweezers to confirm that each individual key registered.  This also allowed me to become familiar with the soldering point locations.

<img src="/images/dz60_build/switch_test.jpg" />

Using the [keyboard tester website](http://www.keyboardtester.com/) made it easy to track and confirm each switch was pressed.  You could also test inside a text editor, but the visual feedback made the process very quick.

<img src="/images/dz60_build/keyboard_tester.jpg" />

### Determine Switch Layout

After testing the board, I verified location of switches for the layout I wanted by placing switches on the plate without fully inserting them and resting the keycaps on top.  This allowed me to verify which soldering points to use for the bottom row and wide modifier keys.

### Place Stabilizers

Once I knew where each of the switches would be placed, I installed the stabilizers on the PCB.  The feet of the stabilizers have a tab on one side and clips on the other.  Orient the stabilizers on the PCB such that the tab hooks in the large hole and press it down until it clips expand in the small hole.

<img src="/images/dz60_build/place_stabilizers.jpg" />

### Solder Switches

Time to begin soldering and take the **Hakko FX-888D** on its maiden voyage!  I cleaned up my work area and removed anything that might be flammable or get in the way.  Put on some M.A.S.H. re-runs and got down to it.

<img src="/images/dz60_build/soldering_area.jpg" />

I started by soldering switches in each of the corners and one in the center. This held everything in place and removed a slight bend from the plate.  I then soldered one row at a time, confirmed the positioning of the keycaps, and tested the switches.

<img src="/images/dz60_build/place_switches.jpg" />

<img src="/images/dz60_build/solder_switches.jpg" />

I did a final test once all of the switches were in place to check that all of the pins were properly connected.  I also tried typing on it, it's a lot harder without keycaps.

<img src="/images/dz60_build/test_switches.jpg" />

### Install Keycaps

Installing keycaps is extremely simple:  

* Line up the keycap over the switch's stem

* Firmly press down until fully seated


Ideally, you'd mount the PCB in the case prior to adding keycaps.  However, my case arrived two weeks after the rest of the parts and I was excited to start using the keyboard.

I originally ordered backlit keycaps that came with gray modifiers, but was unhappy with the molding of the sub-legends on the number keys.  Since I knew this would bug me, I decided to return them and kept shopping.

<img src="/images/dz60_build/backlit_keycaps.jpg" />

I considered a number of other custom sets, but finally decided on simple white keycaps with black legends.  I can always add custom modifiers or swap sets in the future.

<img src="/images/dz60_build/new_keycaps.jpg" />

<img src="/images/dz60_build/layout_keycaps.jpg" />

<img src="/images/dz60_build/in_use.jpg" />

### Mount the PCB in the Case

More packages in the mail!  The case is here.

<img src="/images/dz60_build/case_arrives.jpg" />

This case comes with aluminum feet that allow it to be angled.  I personally left them off for ergonomic reasons, but if you want to use them they need to be installed prior to mounting the PCB.

<img src="/images/dz60_build/feet_options.jpg" />

To install the rubber pads, peel the paper from the adhesive and line up with the wells in the base.

<img src="/images/dz60_build/rubber_feet.jpg" />

To prepare the PCB I pulled the keycaps that obscured the mounting holes.

<img src="/images/dz60_build/remove_keycaps.jpg" />

Then I used a pair of tweezers to place the screws and a small (DH1) Philips bit to screw them in.  Before tightening the screws, I made small adjustments by nudging the PCB to make sure it was evenly aligned within the case.

<img src="/images/dz60_build/mount_pcb.jpg" />

<img src="/images/dz60_build/finished_underglow.jpg" />

## Program and Flash the PCB

Being able to fully customize the key mapping is the real reason I wanted to build my own keyboard.  

I used [qmk_firmware](https://github.com/qmk/qmk_firmware) to compile and flash my layout to the PCB.  The process is fairly straightforward, but requires being willing to read the documentation, troubleshoot any mistakes, and comfort with the command line. Other methods, such as using [qmkeyboard.cn and qmk_toolbox](https://medium.com/@armno/customizing-dz60-keyboard-firmware-e6ad7222288f) can be used as well.


```
# Clone the qmk_firmware repository
git clone https://github.com/qmk/qmk_firmware.git

# Run script to install the necessary dependencies
cd qmk_firmware
sudo util/install_dependencies.sh

# Test compiling and flashing the default profile
# The make instruction uses the following pattern: <keyboard>:<keymap>:dfu
sudo make dz60:default:dfu

# "Error: Bootloader not found. Trying again in 5s." displays if the device 
# isn't recognized.  Some DZ60 PCBs have a reset pin, however, the USB-C version
# of the PCB doesn't appear to have this feature.  

# To force it to register as a DFU device:
# unplug and plug it in while holding the <space> + <b> keys.
```

After testing the ability to flash the key mapping, I created my own using my preferred Fn-1 layout and moved the RGB backlighting and LED settings to the Fn-2 layer.

My custom key map can be found on [GitHub](https://github.com/PatrickHenson/dz60_layout).

```
# Copy the key map into qmk_firmware
mkdir ../qmk_firmware/keyboards/dz60/keymaps/custom_keymap
cp keymap.c ../qmk_firmware/keyboards/dz60/keymaps/custom_keymap

# Navigate to the qmk_firmware directory
cd ../qmk_firmware

# Compile and flash the key mapping
sudo make dz60:custom_keymap:dfu
```

### Scrub-a-dub

Since I was in the midst of playing with my keyboards, it was an opportune time to pull the keycaps from my **KUL-ES 87** and **Vortex Pok3r** and give them a good cleaning.

The cleaning process is pretty simple.

Cleaning the keycaps:

* Pull keycaps and place in a large bowl

* Add 1tbsp of dishwasher powder

* Fill the bowl with warm water until the keycaps are covered

* Allow keycaps to soak.  Some say 10+ minutes is enough, I let them sit for a few hours

* Use a colander to strain the soapy water

* Alternate rinsing and straining clean water until the caps are no longer soapy

Cleaning the boards:

* Use compressed air to remove dust and dog hair

* Clean between the switches using q-tips and rubbing alcohol

Here's the keyboards with their caps off.

<img src="/images/dz60_build/cleaning_keyboards.jpg" />

