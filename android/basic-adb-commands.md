## Android ADB Commands Cheatsheet

### ADB Basics:
- `adb devices`: Lists connected devices.
- `adb root`: Restarts ADB with root permissions.
- `adb start-server`: Starts the ADB server.
- `adb kill-server`: Kills the ADB server.
- `adb reboot`: Reboots the device.
- `adb devices -l`: List of devices by product/model.
- `adb shell`: Starts the background terminal.
- `adb help`: List all commands.

### Package Installation:
- `adb shell install <apk>`: Install app.
- `adb shell install <path>`: Install app from phone path.
- `adb shell install -r <path>`: Reinstall app from phone path.
- `adb shell uninstall <name>`: Remove the app.

### File Operations:
- `adb push <local> <remote>`: Copy files from your computer to your phone.
- `adb pull <remote> <local>`: Copy files from your phone to your computer.

### Phone Info:
- `adb get-state`: Print device state.
- `adb get-serialno`: Get the serial number.
- `adb shell dumpsys battery`: Battery status.
- `adb shell pm list features`: List phone features.

### Package Info:
- `adb shell list packages`: List package names.
- `adb shell dump <name>`: List info on one package.

 
 
### Fastboot Basics:
- `fastboot devices`: Lists connected devices in fastboot mode.
- `fastboot reboot`: Reboots the device.
- `fastboot flash <partition> <image>`: Flash an image to a specific partition.
- `fastboot erase <partition>`: Erase a specific partition.
- `fastboot getvar <variable>`: Get variable information.

##### Installing Magisk:
###### Boot into fastboot mode.
- `fastboot flash boot magisk_patched.img`: Flash Magisk to the boot partition.
- `fastboot reboot`: Reboot the device.
*Magisk is now installed.*
##### Installing TWRP:
###### Boot into fastboot mode.
- `fastboot flash recovery twrp.img`: Flash TWRP to the recovery partition.
- `fastboot reboot recovery`: Reboot into TWRP recovery.
*TWRP is now installed.*



adb pull /storage/emulated/0/Download/1.mp4 /home/ignatiys/Downloads/