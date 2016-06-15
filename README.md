# ffos_on_zte_openc
update Instructions for ffos 2.6 (Firefox OS 2.6) on Zte Open C

# install ffos 2.6 on zteopen_c


### show adb devices
- adb devices

### show fastboot devices
- sudo fastboot devices

### exit from faastboot
- sudo fastboot reboot

### adb permission denied
1] Add the following lines in /etc/udev/android.rules
SUBSYSTEM=="usb", ATTR{idVendor}=="19d2", ATTR{idProduct}=="1350", MODE="0666", GROUP="plugdev"
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="d00d", MODE="0666", GROUP="plugdev"



## install ffos 2.6 with install script

0] root the phone (Windows required)
- with ./rooting/Open_C_upgrade_Tool.zip, flash the ROM

1] boot into fastboot 
- adb reboot-bootloader
2] use prebuild b2g from The Flame and download it or see folder ./upgrade
- from http://ftp.mozilla.org/pub/mozilla.org/b2g/ 
3] download the install_script or see folder ./upgrade/shallow_flash.sh
- from https://github.com/Mozilla-TWQA/B2G-flash-tool/blob/master/shallow_flash.sh
4] change script-rights
- chmod +x ./upgrade/shallow_flash.sh
5] run script
- ./shallow_flash.sh -ggaia.zip -Gb2g-XX.XX.en-US.android-arm.tar.gz
6] if neseccary reboot
- adb reboot


#### source:
http://paulrouget.com/e/openc
