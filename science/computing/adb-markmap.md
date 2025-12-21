# ADB Commands

## Setup

### Installation

- Option 1
  - ```bash
    sudo apt install google-android-tools-installer
    ```
  - Google Android SDK tools
- Option 2
  - ```bash
    sudo apt install adb fastboot
    ```
  - Less Google versions
  - May cause permission issues

### Granting permissions

- Add user to plugdev group
  - ```bash
    sudo usermod -aG plugdev $LOGNAME
    ```
- Install platform tools
  - ```bash
    sudo apt install android-sdk-platform-tools-common
    sudo udevadm control --reload-rules
    ```
- Verify rules
  - `/usr/lib/udev/rules.d/51-android.rules`
  - `/etc/udev/rules.d/99-android.rules`
- Manual rules
  - ```bash
    sudo nano /etc/udev/rules.d/99-android.rules
    ```
  - Common vendors
    - HTC: 0bb4
    - Lenovo: 0502
    - Google: 18d1
    - Qualcomm: 05c6
    - Huawei: 12d1

## Basic commands

- Device connection
  - `adb devices`
    - List connected devices
  - `adb connect <ip>:<port>`
    - Connect via TCP/IP
  - `adb disconnect`
    - Disconnect device
- Shell access
  - `adb shell`
    - Interactive shell
  - `adb shell <command>`
    - Execute single command
- File operations
  - `adb push <local> <remote>`
    - Copy to device
  - `adb pull <remote> <local>`
    - Copy from device
- App management
  - `adb install <apk>`
    - Install app
  - `adb uninstall <package>`
    - Uninstall app
  - `adb shell pm list packages`
    - List packages

## Advanced commands

- Logcat
  - `adb logcat`
    - View system logs
  - `adb logcat -c`
    - Clear logs
- Screen recording
  - `adb shell screenrecord /sdcard/demo.mp4`
    - Record screen
- Screenshot
  - `adb shell screencap /sdcard/screen.png`
    - Capture screen
- Port forwarding
  - `adb forward tcp:<local> tcp:<remote>`
    - Forward ports
  - `adb reverse tcp:<remote> tcp:<local>`
    - Reverse forward
- Reboot commands
  - `adb reboot`
    - Normal reboot
  - `adb reboot bootloader`
    - Reboot to bootloader
  - `adb reboot recovery`
    - Reboot to recovery

## Fastboot commands

- Device info
  - `fastboot devices`
    - List devices
  - `fastboot getvar all`
    - Get device info
- Flashing
  - `fastboot flash <partition> <image>`
    - Flash partition
  - `fastboot erase <partition>`
    - Erase partition
- Bootloader
  - `fastboot oem unlock <key>`
    - Unlock bootloader
  - `fastboot oem lock`
    - Lock bootloader
  - `fastboot oem get-bootinfo`
    - Get boot info
- Boot operations
  - `fastboot boot <image>`
    - Boot image without flashing
  - `fastboot reboot`
    - Reboot device

## Debugging

- Process management
  - `adb shell ps`
    - List processes
  - `adb shell top`
    - Monitor resources
  - `adb shell kill <pid>`
    - Kill process
- System info
  - `adb shell getprop`
    - Get system properties
  - `adb shell dumpsys`
    - Dump system services
- Network
  - `adb shell ping`
    - Test connectivity
  - `adb shell netstat`
    - Network status
  - `adb shell ifconfig`
    - Network interfaces
