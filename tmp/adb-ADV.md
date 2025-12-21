# ADB commands Android

## Set up

### Installation

```bash
sudo apt install google-android-tools-installer # Google Android SDK tools
```

OR:

```bash
sudo apt install adb fastboot # Less Google versions, may cause permission issues, your call
```
### Granting permissions:

```bash
# Check if the user is already a member of the plugdev group
if groups $LOGNAME | grep &>/dev/null "\bplugdev\b"; then
    echo "✅$LOGNAME is already a member of the plugdev group."
else
    # Add the user to the plugdev group
    sudo usermod -aG plugdev $LOGNAME
    echo "✅$LOGNAME has been added to the plugdev group."
fi

sudo apt install android-sdk-platform-tools-common
sudo udevadm control --reload-rules
```

Refer to [Android Developers Documentation](https://developer.android.com/studio/run/device?hl=fr) for more information.

If the installing `android-sdk-platform-tools-common` does not work as expected, open the rule files at `/usr/lib/udev/rules.d/51-android.rules` or `/etc/udev/rules.d/99-android.rules` and verify that they are not blank or invalid.

If the files are valid yet you can not figure out what went wrong, you can instead edit permissions manually:

```bash
sudo nano /etc/udev/rules.d/99-android.rules
```
Add:

```bash
# Grant read and write permission to device owner (06xx) and all in group plugdev (GROUP="plugdev; 0x6x) for some common mobile devices
# If your device is not included, run lsusb to find out idVendor. You will likely see something like 123c:c321, the four digits before : is idVendor.
SUBSYSTEM=="usb", ATTR{idVendor}=="0bb4", MODE="0660", GROUP="plugdev" # HTC
SUBSYSTEM=="usb", ATTR{idVendor}=="0502", MODE="0660", GROUP="plugdev" # Lenovo
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", MODE="0660", GROUP="plugdev" # Google
SUBSYSTEM=="usb", ATTR{idVendor}=="05c6", MODE="0660", GROUP="plugdev" # Qualcomm
SUBSYSTEM=="usb", ATTR{idVendor}=="12d1", MODE="0660", GROUP="plugdev" # Huawei
```

```bash
sudo udevadm control --reload-rules
```

> Prefer `android-sdk-platform-tools-common` as it is much more comprehensive.

> If you absolutely cannot figure it out, you can duct tape around by `sudo`ing `fastboot` and `adb`. 

## System

### System information

```bash
adb shell cat /proc/cpuinfo #processor
``

### Root

```bash
adb root
adb unroot
```

Manage permission level of the adb session.

### Mode

```bash
adb reboot [bootloader|recovery|sideload|sideload-auto-reboot]
```
sideload boots into recovery mode and enter adb sideload mode.
sideload-auto-reboot does what sideload does, with the additional auto-reboot after sideloading.

### Shell

```bash
adb shell
```

### System modification

```bash
adb reboot bootloader
```

```bash
fastboot flash <partition-name>
```
Partition name: system/boot/init_boot/recovery...

## File management

>  ```bash
>   push [--sync] [-z ALGORITHM] [-Z] LOCAL... REMOTE
>      copy local files/directories to device
>   --sync: only push files that are newer on the host than the device
>      -n: dry run: push files to device without storing to the filesystem
>      -z: enable compression with a specified algorithm (any/none/brotli/lz4/zstd)
>      -Z: disable compression
>  ``` 
>  ```bash
>  pull [-a] [-z ALGORITHM] [-Z] REMOTE... LOCAL
>      copy files/dirs from device
>      -a: preserve file timestamp and mode
>      -z: enable compression with a specified algorithm (any/none/brotli/lz4/zstd)
>      -Z: disable compression
>  ```
> Advanced option - sync build:
>  ```bash
>  sync [-l] [-z ALGORITHM] [-Z] [all|data|odm|oem|product|system|system_ext|vendor]
>      sync a local build from $ANDROID_PRODUCT_OUT to the device (default all)
>      -n: dry run: push files to device without storing to the filesystem
>      -l: list files that would be copied, but don't copy them
>      -z: enable compression with a specified algorithm (any/none/brotli/lz4/zstd)
>      -Z: disable compression
>   ```
*-Official help menu*

## Package management

```bash
adb devices
adb shell pm list packages -3
```

`-3`: User installed applications only

### F-Droid repository  (with `fdroidcl`)

```bash
if ! command -v fdroidcl &> /dev/null # Check if fdroid CLI client is installed
then
    echo "fdroidcl is not installed. Installing..."
    sudo apt install fdroidcl # Install fdroid CLI client if not yet installed
fi
fdroidcl update  # update local copy of FDroid search index 
```

```bash
fdroidcl --help # the inline help menu is very good
```


