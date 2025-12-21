# Rooting Android&Derivative Mobile Phone with Magisk

```plantUML
@startuml

<style>

activity {
    BackGroundColor #A9DCDF;
    ' BorderColor #A9DCDF
    }

</style>

start

:Install Magisk APK;

if (Determines whether Ramdisk exists?) then (Yes)
    :Locate `boot.img` or `init_boot.img`;
else (No)
    :Locate `recovery.img`;
endif

:Copy `.img` to target device;
:Patch `.img` with Magisk APK;
:Pull `patched.img` into your PC;
:Flash `patched.img` to your device;
:Reboot and activate Magisk in the APK;

end

@enduml
```

> Magisk APK: The Magic Mask, com.topjohnwu.magisk  

Follow [ official step-by-step instruction](https://topjohnwu.github.io/Magisk/install.html)  