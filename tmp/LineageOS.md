# LineageOS

## Some useful open-source apps


| Name | Description | Package name (FDroid) | * |
| :---: | :---:| :---:| :---:|
| F-Droid | Open-source app store | com.fdroid.fdroid | Rest assured every app on Fdroid is FOSS |
| Aurora | Google Playstore without Google | com.aurora.store | optional Google Login |
|  Heliboard | FOSS Keyboard without Gboard dependency | helium314.keyboard | The default keyboard on Lineage OS is as functional, although less pretty |
| Thunderbird | Open-source Email Client | net.thunderbird.android | multi-account support |
| Nextcloud | Open-source cloud | com.nextcloud.client | * |
| Organic maps | FOSS map | app.organicmaps | OSM frontend. Public transport data not yet included. |
| Fossify series | Simple FOSS app series | org.fossify.xxx |  By Naveen Singh, Agnieszka C. et al.|
| Signal | FOSS whatsapp altnerative | org.thoughtcrime.securesms | No server message log |
| Firefox | FOSS browser | org.mozilla.fenix (Nightly) org.mozilla.firefox (standard) | * |
| Transcribro | FOSS voice-recognition | [Github release](https://github.com/soupslurpr/Transcribro/releases/tag/v0.3.1) | Open-source frontend for OpenAI Whisper. Excellent speech recognition. Currently supports English only. |


## For developers

| Name | Description | Package name (FDroid) | * |
| :---: | :---:| :---:|:---:|
| Expo Go | Expo framework testing | host.exp.exponent | Wireless connection can be buggy. Consider connecting via USB, bridge ports via `adb reverse tcp: 8081 tcp:8081` then access via `localhost:8081`|
| Trime IME | FOSS Chinese Keyboard | com.osfans.trime | Steep learning curve. Documentation insufficient ATOW. Extensively customizable with the RIME framework, can support numerous input methods for multiple Han Chinese variants, Wu, Mandarin, Cantonese, etc. |
|  Magisk | Twinkler's dream: Root management and more | com.topjohnwu.magisk | function on select devices only, install at your own risk. |


### Debloating

LineageOS is based on Android. Android is developed by Google. What do you expect?

```bash
adb shell pm uninstall --user 0 com.android.providers.partnerbookmarks
```

### Fossifying LineageOS

The system apps on LineageOS are clean and handy. However, if you, like me, prefer the fossify series for consistency, you can search on F-Droid for each individual app, or modify and use this script to fossify your lineageOS