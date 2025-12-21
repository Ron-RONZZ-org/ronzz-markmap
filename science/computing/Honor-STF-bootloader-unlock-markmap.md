# Bootloader Unlock

## Resources

- [PotatoNV](https://github.com/mashed-potatoes/PotatoNV)
  - Free and open-source solution
  - [Official tutorials](https://linktr.ee/potatonv)
  - [Huawei USB COM 1.0 Driver](https://www.youtube.com/watch?v=A2y8UCoaigg)
- [IFixit Teardown Guide](https://fr.ifixit.com/Vue+%C3%89clat%C3%A9e/Huawei+Honor+9+Teardown/97287?lang=en)
- [Test point shorting on Honor STF](https://www.youtube.com/watch?v=wobm5wfcWKM)
- [LineageOS for EMUI 9 Huawei](https://xdaforums.com/t/rom-huawei-13-leaos-lineage-20-0-for-huawei-device-emui-9-1-version.4560779/)

## Export

- Backup all data
  - Factory reset warning
- List installed packages
  - ```bash
    adb shell pm list packages -3
    ```
  - `-3`: User-installed only

## Unlock procedure

### Hardware preparation

1. Disconnect battery for 3s
2. Plug battery back in
3. Ground testpoint for 3s
4. Plug USB while grounding

### Bootloader unlock

- Reboot to bootloader
  - ```bash
    adb reboot bootloader
    ```
- Check devices
  - ```bash
    fastboot devices
    ```
- Unlock
  - ```bash
    fastboot oem unlock <key>
    fastboot oem get-bootinfo
    ```

### Install custom ROM

- Install LeaOS
- Install custom recovery
  - [TWRP fork by altairfr](https://sourceforge.net/projects/altairfr-huawei/)
- Flash commands
  - ```bash
    fastboot flash system <system.img>
    fastboot flash recovery_ramdisk <twrp.img>
    fastboot reboot recovery
    ```
- [ADB sideload](https://twrp.me/faq/ADBSideload.html)
  - TWRP: Advanced → ADB Sideload
  - ```bash
    adb sideload <patch.zip>
    ```

## Why LineageOS?

- Reliability
- Balance
  - Security vs customizability
- Limitations
  - Based on Android
  - FBE compulsory
- Custom kernels
  - Can disable FBE
  - Trade-offs
    - Security: All files unprotected
    - Flexibility: Complete system access
    - Reliability: Lower data loss risk
