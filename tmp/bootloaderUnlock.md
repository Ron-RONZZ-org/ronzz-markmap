# Commands

[potatoNV's impressive free and open-source solution](https://github.com/mashed-potatoes/PotatoNV)
[potatoNV's official tutorials](https://linktr.ee/potatonv)
[potatoNV: installing Huawei USB COM 1.0 Driver](https://www.youtube.com/watch?v=A2y8UCoaigg)
[IFixit Teardown Guide](https://fr.ifixit.com/Vue+%C3%89clat%C3%A9e/Huawei+Honor+9+Teardown/97287?lang=en)
[Test point shorting on Honor STF series](https://www.youtube.com/watch?v=wobm5wfcWKM)
[LineageOS for EMUI 9 Huawei Devices](https://xdaforums.com/t/rom-huawei-13-leaos-lineage-20-0-for-huawei-device-emui-9-1-version.4560779/)

## Export

Backup all data: factory reset warning

List of installed packages

```bash
adb shell pm list packages -3
```

`-3`: Use installed packages only

Disconnect battery for 3s
Plug battery back in
Ground testpoint for 3s
Plug USB in while grounding

```bash
adb reboot bootloader
```

```bash
fastboot devices
fastboot oem unlock <key>
fastboot oem get-bootinfo
```

Now after it has been done, put your phone case back together and boot into fastboot mode again.
You will now need to install LeaOS and a custom recovery, such as the [TWRP fork](https://sourceforge.net/projects/altairfr-huawei/) by altairfr.  

```bash
fastboot flash system 
fastboot flash recovery_ramdisk <twrp.img-path>
fastboot reboot recovery
```

For the patch, you can also [sideload](https://twrp.me/faq/ADBSideload.html) it by setting the device into ADB sideload mode (TWRP: Advanced> ADB Sideload) then run `adb sideload <patch.zip-path>`


Why LineageOS?
Reliability
Compromise between security and customizability
Not the most permissive: Based on Android systems, FBE compulsory. Some kernels allow disabling file-based encryption (FBE). 
Good reason to disable FBE? Reliability and security trade-off. If disabled, all files are stored without protection, and whoever has the phone can access all data, yet chance of data loss lower and complete flexibility in modifying the system is granted to the user.

