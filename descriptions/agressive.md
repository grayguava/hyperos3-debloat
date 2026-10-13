# Agressive profile

Detail file for `lists/agressive.txt` (53 packages = all 44 from `balanced.md` plus the 9 highest-tradeoff entries below). Do not apply without replacements for the dialer/SMS entries and without accepting the loss of theft protection and emergency SOS.

## Included from Safe and Balanced (47)

See `descriptions/safe.md` (33 no-tradeoff entries) and `descriptions/balanced.md` (11 tradeoff entries). They are all listed in `lists/agressive.txt`.

## Agressive extras (9) — highest tradeoff, apply last

- AOSP Messaging
  - `com.android.mms`
  - Stock SMS app. Only remove with a replacement SMS app set as default (Google Messages holds the SMS role here).
  - Recommended alternative: [Fossify Messages](https://www.fossify.org/apps/messages/)
- Contacts and dialer
  - `com.android.contacts`
  - Stock dialer + contacts UI. Only remove with a replacement ready.
  - Recommended alternative: [Fossify Phone](https://www.fossify.org/apps/phone/) and [Fossify Contacts](https://www.fossify.org/apps/contacts/)
- Xiaomi Find Device
  - `com.xiaomi.finddevice`
  - Theft protection (locate/lock/wipe). Delete at your own risk. Not function-tested after removal.
- Personal Safety
  - `com.google.android.apps.safetyhub`
  - Removes emergency SOS/crash detection. Built-in power-button SOS still works.
- Xiaomi Cloud
  - `com.miui.cloudservice`
  - General Xiaomi Cloud wrapper, also used by Find Device. Part of the Mi Cloud/OTA stack.
- Mi Cloud SDK
  - `com.xiaomi.micloud.sdk`
  - Mi Cloud SDK. Part of the Mi Cloud/OTA stack.
- Mi Cloud Sync
  - `com.miui.micloudsync`
  - Mi Cloud sync engine. Part of the Mi Cloud/OTA stack.
- Mi Cloud backup
  - `com.miui.cloudbackup`
  - Mi Cloud full-device backup.
- MIUI Theme Manager
  - `com.android.thememanager`
  - You may lose homescreen and lockscreen customisation features. No impact on usability at all. Wallpapers work fine if done through Gallery or a third-party app. To keep it but hide it from the launcher: Settings > Apps > three dots > Other settings > Manage home screen shortcuts > disable Theme Manager.
