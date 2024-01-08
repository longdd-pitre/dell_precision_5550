# Dell Precision 5550 macOS Monterey ( pitre)

This is an OpenCore EFI that allows you to install and boot macOS Monterey on your Dell  Precision 5550 (2020)


<b>OpenCore Version:</b> 0.7.4

<b>macOS Version:</b> Monterey 12.6.4
---


---

## Functional Status

|Function / Hardware|Status|
|-|-|
|iGPU UHD630 Acceleration|Working|
|CPU Power Management|Working - idles at 800MHz, boosts to max Turbo frequency|
|Laptop Keyboard|Working|
|Laptop Trackpad|Working|
|Laptop Headphones Jack|Working|
|Built-in Speakers|Working|
|Built-in Mic|Working|
|Hotkeys for audio|Working|
|USB 3.x|Working|
|USB 2.0|Working|
|Fingerprint Sensor|Not working|
|Touchscreen|Working|
|SD Card Slot|Not Working|
|Screen brightness|Working, hotkeys fn+S/fn+B to decrease/increase brightness|
|Built-in Wifi|Working|
|Built-in Bluetooth|Semi-working, AirDrop is not currently working|
|Dell USB3.1 dock|Working|
|RTL8153 USB Ethernet on Dell dock|Working|
|Other peripherals on Dell dock|Working|
|Built-in webcam|Working|


---

## BIOS Settings

Disable the following
 - VT-d
 - TPM
 - Secure boot
 - Disable CFG Lock (via modGRUBShell)

---

## Important

This EFI was created from scratch using Dortania's vanilla laptop guide with additional info from the Comet Lake setup https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#starting-point

You are strongly advised to read the guide fully before using the EFI in this repository. Do not use the EFI as is. You will need to learn how to replace the serial number with GenSMBios and disable cfg lock at the very least.

---

## How to disable CFG Lock

This is specific to XPS 15 9500 only (along with its sibling models and previous gen).

Select the modGRUBShell option at startup (OpenCore boot selection page).
At the grub prompt, enter the following commands (the first line unlocks CFG, the second line unlocks overclocking).

```
setup_var CpuSetup 0x3e 0x0
setup_var CpuSetup 0xda 0x0
exit
```

Restart your laptop and boot into the BIOS. Do a factory reset. Now your CFG lock will be disabled. You can confirm that by running the VerifyMSR2 option.

If you update your BIOS, you may need to do this again but so far Dell has been kind to us.

---

## Brightness hotkeys

fn+S and fn+B hotkeys are currently used to adjust brightness.

---

