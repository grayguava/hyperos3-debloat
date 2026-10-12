# Agressive profile

Detail file for `lists/agressive.txt` (51 packages = all 43 from `balanced.md` plus the 8 highest-tradeoff entries below). Do not apply without replacements for the dialer/SMS entries and without accepting the loss of theft protection and emergency SOS. All entries were removed for user 0 and confirmed absent on 2026-10-12, except where noted.

## Included from Safe and Balanced (47)

See `descriptions/safe.md` (33 no-tradeoff entries) and `descriptions/balanced.md` (10 tradeoff entries). They are all listed in `lists/agressive.txt`.

## Agressive extras (8) — highest tradeoff, apply last

- AOSP Messaging
  - `com.android.mms`
  - Stock SMS app. Only remove with a replacement SMS app set as default (Google Messages holds the SMS role here).
- Contacts and dialer
  - `com.android.contacts`
  - Stock dialer + contacts UI. Only remove with a replacement; Google Dialer/Contacts in use, calling tested.
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
