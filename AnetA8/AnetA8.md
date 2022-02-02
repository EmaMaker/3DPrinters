# Anet A8

I bought the Anet A8 arounf July 2020, and it arrived without an aluminium piece which had to hold the extruder+direct drive motor. I contacted the seller which refunded the printer in total to me.

I tried to 3D-print a replacement, but failed miserably. The original hotend also tends to clog up pretty easily, and the direct drive extruder mount tends to generate even more vibrations on the structure when moving, which can only be fixed by slowing down the printer or changing to a bowden setup.

After some experiments trying to get an old E3D-v5 extruder to work, I decided to buy an E3D-v6 extruder with a bowden filament setup, and got a friend to print the mounts for me.

I changed the extruder mount a couple of times and I finally found a solution that satisfies me and works without problems on the printer. I also replaced the 30mm of the extruder with the original 40mm fan that came with the printer.

The Anet A8 is subject to a lot of vibrations, and I had to print (on the now-working anet) a lot of pieces to stiffen the structure.
All of the upgrades here were mounted using included screws and nuts, and I only had to use few screws and nuts that I already had from other projects.

Since I was there, I also upgraded the firmware from Anet's custom one to Marlin 2.x, which has a predefined configuration for the Anet A8. This repo includes by build of Marlin 2.0.9.3, which has the offset definitions for the extruder mount I currently use.
See [Upgrading Firmware](#firmware) for more info on how I upgaded the firmware.
[Read how to build Marlin Firmware here](https://github.com/MarlinFirmware/Marlin)

<br>

# Important notes
With my current setup retracting the filament is not possible, because it clogs the extruder, and I still haven't figured out (nor searched for) the correct settings. This means retraction has to be disable in the cura profile and has to be removed from start/end end g-code if present.

<br>

**bold** parts are what I currently use

<br>

## E3Dv6 hotends
 * (currently used)
 * (bought as a replacement for me, gave it to a friend for his anet a8 and it is working perfectly)

## E3Dv6 extruder mounts (+ carriages)
 * ANET A8 | Customizable E3D v6 Carriage / Bowden Mount: https://www.thingiverse.com/thing:2099577
 * 
 * **Anet A8 E3Dv6 & BlTouch Support / Carrgiage https://www.thingiverse.com/thing:2843500/files** (currently used)

## Motor bowden mount:
 * Bowden extruder mount: https://www.thingiverse.com/thing:2146021

## Fan ducts
 * **Spyra** : https://www.thingiverse.com/thing:2133328/files (currently used)
 * Original, also available here: https://www.thingiverse.com/thing:1438439/files

## 30mm-to-40mm fan adapter
 * https://www.thingiverse.com/thing:2748800 (currently used)

## X-Axis tensioner

## Y-Axis tensioner

## Y-Axis braces

## Hulk frame braces

## Glass pane for print bed

## Upgrading Firmware {#firmware}
Probably your Anet A8 won't have a bootloader, but you will need one to flash custom firmware. I used Arduino IDE and a USBAsp to do this
(WIP)