# LineageOS

## Open-source apps

### Essential apps

- F-Droid
  - Open-source app store
  - `com.fdroid.fdroid`
  - All apps are FOSS
- Aurora
  - Google Playstore without Google
  - `com.aurora.store`
  - Optional Google Login
- Heliboard
  - FOSS Keyboard
  - `helium314.keyboard`
  - No Gboard dependency
- Thunderbird
  - Email Client
  - `net.thunderbird.android`
  - Multi-account support
- Nextcloud
  - Open-source cloud
  - `com.nextcloud.client`
- Organic maps
  - FOSS map
  - `app.organicmaps`
  - OSM frontend
- Fossify series
  - Simple FOSS apps
  - `org.fossify.xxx`
  - By Naveen Singh, Agnieszka C. et al.
- Signal
  - Whatsapp alternative
  - `org.thoughtcrime.securesms`
  - No server message log
- Firefox
  - FOSS browser
  - `org.mozilla.firefox`

### Developer tools

- Expo Go
  - Expo framework testing
  - `host.exp.exponent`
  - USB connection via `adb reverse`
- Transcribro
  - Voice recognition
  - OpenAI Whisper frontend
  - English only
- Trime IME
  - Chinese Keyboard
  - `com.osfans.trime`
  - RIME framework
  - Customizable
- Magisk
  - Root management
  - `com.topjohnwu.magisk`
  - Select devices only

## Debloating

- Remove bloatware
  - ```bash
    adb shell pm uninstall --user 0 com.android.providers.partnerbookmarks
    ```
- Android = Google
  - Expected bloat

## Fossifying LineageOS

- Replace system apps
  - Fossify series
  - Consistency
- Script automation
  - Batch replacement

## Why LineageOS?

- Reliability
- Security vs customizability balance
- Based on Android
  - FBE compulsory
- Custom kernels
  - Can disable FBE
- Flexibility: Complete system access
- Trade-offs
  - cannot pass Google Playsafe
    - most banking apps, etc. will NOT work
