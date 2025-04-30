# tk11-firmware-custom
Open reimplementation of the Quansheng TK11 Firmware

# Current status

At this stage of my research, the path ahead appears long and uncertain.
It’s difficult to find reliable information about the AP8048 microcontroller.
From what I’ve gathered so far, it seems to have 128 KB of SRAM, which is good news.

However, I still don’t know the size of its internal Flash memory, which would be needed to store a potential bootloader and, more importantly, the firmware itself.

In addition, no external EEPROM has been identified on the TK11’s PCB — unlike on the Quansheng K5.
This suggests that calibration data, persistent settings, and the 999 memory channels are likely stored directly within the AP8048’s internal memory.

But this remains to be confirmed — these are still just hypotheses.

The technical architecture of the TK11 therefore appears to be quite different from that of the K5.

# Challenges in Obtaining Information About the AP8048 (MVSilicon)

## 1. No Public Documentation  
MVSilicon does **not provide any complete public datasheet** for the AP8048 on its website or through typical semiconductor distribution platforms.

## 2. NDA-Restricted Access  
Technical details such as **datasheets, pinouts, and application examples** are usually only available **under NDA (Non-Disclosure Agreement)** to selected industrial partners — most often Chinese OEMs and manufacturers.

## 3. No SDK or Developer Tools  
Unlike general-purpose microcontrollers (like STM32 or ESP32), there is **no public SDK or programming toolchain** available.  
These chips are designed for **pre-programmed, fixed-function applications** such as audio modules, toys, and embedded sound systems.

## 4. Locked-Down, Application-Specific Use  
The AP8048 is meant to execute **factory-burned firmware only**, with **no external interface** for programming or debugging.  
It is used as a **black-box SoC** in mass-produced consumer products.

## 5. Extremely Limited Community Resources  
There's **very little community documentation** available.  
Most technical insights come from **reverse engineering**, **photos of PCBs**, or discussions on **Chinese and Russian electronics forums**, or seller pages on Taobao/AliExpress.

---

# Conclusion (for the moment...)

> The AP8048 is a **closed, proprietary chip** designed for tightly integrated mass-market products — **not for independent development or open use**.  
> Accessing meaningful technical information requires a combination of **hardware inspection, reverse engineering**, and a good dose of patience due to the **lack of open resources**.
