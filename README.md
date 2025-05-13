# OrangeFox for Nokia 1.3 (particularly broken)

This repository contains the OrangeFox recovery image for Nokia 1.3 and fonts for it. Fonts are necessary to successfully run recovery.

## Usage

To clone the repository, first run

```sh
git clone https://github.com/yesstude/orangefox-nokia1.3.git
```

### Boot to recovery:

```sh
adb reboot bootloader
```
Wait for reboot
```sh
fastboot flash recovery recovery.fox.img
fastboot reboot recovery
```
Wait for the moment when OrangeFox logo starts blinking (bug that happens when building).
```sh
adb push fonts/ /twres/fonts/
```

### When you are done:

```sh
adb reboot bootloader
```
Wait...
```sh
fastboot flash recovery recovery.original.img

fastboot reboot
```
Phone should boot successfully.

If still cannot boot, boot to original recovery and wipe the cache. To boot to original recovery, you need to first hold power and sound+ buttons, then select «Reboot to recovery», and then when the error appears, hold power and fastly press sound+ button once.
