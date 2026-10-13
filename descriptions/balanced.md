# Balanced profile

Detail file for `lists/balanced.txt` (44 packages = all 33 from `safe.md` plus the 11 tradeoff entries below). Read the tradeoff note before applying.

## Included from Safe (33)

See `descriptions/safe.md` for the 33 no-tradeoff entries. They are also listed in `lists/balanced.txt`.

## Balanced extras (11) — each trades a feature or needs a replacement

- Xiaomi Service Center
  - `com.miui.miservice`
  - Xiaomi service-center app.
- Xiaomi GLGM
  - `com.xiaomi.glgm`
  - Game/graphics service. Camera tested working after removal.
- Xiaomi HyperAI Engine
  - `com.xiaomi.aicr`
  - Background AI engine. Gallery editor and document effects still worked after removal.
- Google app
  - `com.google.android.googlequicksearchbox`
  - Removes Search, Assistant entry point and At a Glance.
- Hey Google enrollment
  - `com.android.hotwordenrollment.okgoogle`
  - Breaks Hey Google hotword detection.
- Hey Google enrollment (alt)
  - `com.android.hotwordenrollment.xgoogle`
  - Breaks Hey Google hotword detection.
- Android Auto
  - `com.google.android.projection.gearhead`
  - Breaks Android Auto. Reinstall if you use it in the car.
- MIUI Bug Report
  - `com.miui.bugreport`
  - Bug-report feedback app. Only remove if you never file system bug reports.
- Mi Music player
  - `com.miui.player`
  - Stock music player. Only remove if you use another music app.
  - Recommended alternative: [Auxio](https://github.com/OxygenCobalt/Auxio) or [Gramophone](https://github.com/FoedusProgramme/Gramophone)
- GetApps store
  - `com.xiaomi.mipicks`
  - Xiaomi app store (formerly `com.xiaomi.market`). Only remove if you never use it.
- Google Maps
  - `com.google.android.apps.maps`
  - Google Maps navigation app.
  - Recommended alternative: [Organic Maps](https://github.com/organicmaps/organicmaps)

## Not in any list (kept or failed)

- `org.mipay.android.manager` (Mi Pay manager) — removal failed, still installed. Retry manually, do not add to a list until it reports success.
- `com.miui.cleaner`, `com.google.android.apps.wellbeing`, `com.miui.misound`, `com.miui.mediaviewer`, `com.android.stk`, `com.xiaomi.misettings`, `com.miui.securitycenter` — deliberately kept (cleaner and wellbeing actively used; sound EQ, media viewer, SIM toolkit, settings core and security center left alone as risky or core).
