# Anet A8

I bought the Anet A8 arounf July 2020, and it arrived without an aluminium piece which had to hold the extruder+direct drive motor. I contacted the seller which refunded the printer in total to me.

I tried to 3D-print a replacement, but failed miserably. The original hotend also tends to clog up pretty easily, and the direct drive extruder mount tends to generate even more vibrations on the structure when moving, which can only be fixed by slowing down the printer or changing to a bowden setup.

After some experiments trying to get an old E3D-v5 extruder to work, I decided to buy an E3D-v6 extruder with a bowden filament setup, and got a friend to print the mounts for me.

I changed the extruder mount a couple of times and I finally found a solution that satisfies me and works without problems on the printer. I also replaced the 30mm of the extruder with the original 40mm fan that came with the printer.

The Anet A8 is subject to a lot of vibrations, and I had to print (on the now-working anet) a lot of pieces to stiffen the structure.
All of the upgrades here were mounted using included screws and nuts, and I only had to use few screws and nuts that I already had from other projects.

Since I was there, I also upgraded the firmware from Anet's custom one to Marlin 2.x, which has a predefined configuration for the Anet A8. This repo includes by build of Marlin 2.0.9.3, which has the offset definitions for the extruder mount I currently use.
See [Upgrading Firmware](#firmware) for more info on how I upgaded the firmware.


<br>

# Important notes
With my current setup retracting the filament is not possible, because it clogs the extruder, and I still haven't figured out (nor searched for) the correct settings. This means retraction has to be disable in the cura profile and has to be removed from start/end end g-code if present.

<br>

**bold** parts are what I currently use, but some other parts/setups I tried in the past are also listed

<br>

## E3Dv6 hotends
 * https://www.amazon.it/distanziatore-Estrusore-Accessori-estrusore-stampante/dp/B07SJQRKGC/ref=pd_yo_rr_rp_8/262-9324296-5515714?pd_rd_w=xBi6v&pf_rd_p=ef4b4720-9514-470c-af05-06ea9c947edb&pf_rd_r=Y9PW1PF7FXZVBJY0TRNB&pd_rd_r=f3e4cf2a-9ea5-4dfe-95fe-25b2f51c65af&pd_rd_wg=24QNT&pd_rd_i=B07SJQRKGC&psc=1 (currently used)
 * https://www.amazon.it/gp/product/B07MH5KYW9/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1  (bought as a replacement for me, gave it to a friend for his anet a8 and it is working perfectly)

## E3Dv6 extruder mounts (+ carriages)
 * ANET A8 | Customizable E3D v6 Carriage / Bowden Mount: https://www.thingiverse.com/thing:2099577 (x axis endstop problems)
 * Anet A8 E3dv6 Bowden Print Carriage Redux: https://www.thingiverse.com/thing:2077676 (used for a lot of time)
 * **Anet A8 E3Dv6 & BlTouch Support / Carrgiage https://www.thingiverse.com/thing:2843500/files** (currently used)

## Motor bowden mount:
 * **Anet A8 Bowden extruder mount**: https://www.thingiverse.com/thing:2146021 (currently used)
 * Anet A8 Customizable bowden extruder mount: https://www.thingiverse.com/thing:2204941
 
## Fan ducts
 * **Spyra** : https://www.thingiverse.com/thing:2133328/files (currently used)
 * Original, also available here: https://www.thingiverse.com/thing:1438439/files

## 30mm-to-40mm fan adapter
 * https://www.thingiverse.com/thing:2748800 (currently used)

## X-Axis belt tensioner:
 * **Anet A8 improved X-belt tensioner:** https://www.thingiverse.com/thing:1683070 (currently used)

## Y-Axis belt tensioner
 * **Anet A8 Y belt tensioner:** https://www.thingiverse.com/thing:2149867 (currently used) 

## Y-Axis braces
 * **Anet A8 Y-Axis Idler & Motor Brace Upgrades**: https://www.thingiverse.com/thing:2074599

## Frame braces
 * **Hulk frame braces**: https://www.thingiverse.com/thing:2189694 (currently used)

## Glass pane for print bed
 * https://www.amazon.it/gp/product/B0777L4HWS/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1

## Upgrading Firmware to Marlin 2.x {#firmware}
Probably your Anet A8 won't have a bootloader, but you will need one to flash custom firmware. I used Arduino IDE and a USBAsp to do this:
 
 * [Install Arduino IDE](https://www.arduino.cc/en/software) 1.8.x
 * Clone https://github.com/SkyNet3D/anet-board and copy the contents of the "hardware" folder inside the "hardware" folder of your arduino install (the location of this depends on your OS, search for it)
 * Launch Arduino IDE, go to Tools/Board and select Anet 1.0 (optiboot)
 * Go to Tools/Programmer and select your programmer (I used a USBAsp, use what you have, even an Arduino as ISP)
 * Go to Tools/Burn bootloader. This will flash the bootloader to your board and wipe the flash memory. It can take a while. If it fails with some "signature verification error" most likely you have a faulty connection
 * Now you can install Marlin 2.x. There's Marlin 2.0.9.3 sources in the Anet A8/Marlin folder, with Configurations for my current hotend, which has an offset compared to the original. [Read how to build Marlin Firmware here](https://github.com/MarlinFirmware/Marlin)