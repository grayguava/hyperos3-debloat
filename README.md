# Debloat HyperOS 3 phones with Android Debug Bridge (ADB)

This repository contains [Android Debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb) lists to remove bloatware from HyperOS Android. Debloating helps remove unwanted system apps to improve performance, battery life, and privacy.

Tested on one phone only: **Xiaomi POCO, HyperOS 3.0.303.0, Android 16** — This repo is specific to **HyperOS 3** and this device/build. Package names and side effects can differ on other phones or builds, so treat this as a reference, not a universal script. For a broader, general-purpose HyperOS debloat list, refer to [https://github.com/matthieu-pierson/debloat-hyperos-adb](https://github.com/matthieu-pierson/debloat-hyperos-adb.).

The lists are categorized into three different profiles:
*   **Safe:** Removes only non-essential bloatware, telemetry and standalone apps with no feature tradeoff (33 packages in `lists/safe.txt`). Very low risk of causing issues.
*   **Balanced:** A superset of Safe (44 packages in `lists/balanced.txt`). Aims for a good balance between debloating and retaining features. Some apps you might use could be removed — each extra entry needs a replacement app or trades a feature (Google Search, Hey Google, Android Auto, Mi Music, GetApps, Google Maps).
*   **Agressive:** A superset of Balanced (53 packages in `lists/agressive.txt`). Adds the nine highest-tradeoff entries: the dialer/SMS swap, Find Device, Personal Safety, the Mi Cloud stack and Theme Manager. Only for users who accept those losses.

Each list is one package name per line. Details for every package (name + description) live in the matching file under `descriptions/` (`safe.md`, `balanced.md`, `agressive.md`).

> [!WARNING]  
> **USE AT YOUR OWN RISK!** While these commands are generally safe and reversible, debloating can have unintended consequences. It might break system functionalities or cause instability. Always back up your important data before proceeding. It's highly recommended to read through the `descriptions/` file for your chosen profile first and drop any apps you want to keep.

---

## Prerequisites

1.  **Android Debug Bridge (ADB):** You need ADB installed on your computer.
    *   **Recommended:** [Minimal ADB and Fastboot](https://xdaforums.com/t/tool-minimal-adb-and-fastboot-2-9-18.2317790/) from XDA forums for a quick setup.
    *   **Official:** Download the official [Android SDK Platform Tools](https://developer.android.com/studio/releases/platform-tools).

2.  **Enable Developer Options on your phone:**
    *   Go to `Settings > About phone`.
    *   Tap on `MIUI version` (or `OS version` on HyperOS) multiple times until you see the message "You are now a developer!".

3.  **Enable USB Debugging:**
    *   Go to `Settings > Additional settings > Developer options`.
    *   Enable `Developer options`.
    *   Enable `USB debugging`.
    *   (Optional but recommended) Enable `Install via USB` if you plan to sideload apps.

---

> [!TIP]
> It is **highly recommended** that you install the replacement apps and set them up before debloating. Also review the matching details file first ([descriptions/safe.md](descriptions/safe.md), [descriptions/balanced.md](descriptions/balanced.md), [descriptions/agressive.md](descriptions/agressive.md)).

## Instructions

1.  **Connect your phone** to your computer with USB debugging enabled.

2.  **Verify the ADB connection** by opening a terminal and running the following command.
    ```shell
    adb devices
    ```
    You should see the device name listed as a "device". If it says "unauthorized", your device should prompt you to accept USB debugging from your computer. Tap "Allow".

3.  **Enter your device's shell** with the following command:
    ```shell
    adb shell
    ```

4.  **Choose and run a debloat profile.** Select one of the files (safe.txt/balanced.txt/agressive.txt).

5.  Run the package names in the list through ADB. From the repo folder on your computer (PowerShell):
    ```powershell
    Get-Content lists\safe.txt | ForEach-Object { adb shell pm uninstall --user 0 $_ }
    ```
    For example, a command from the list would look like this:
    ```shell
    pm uninstall --user 0 com.miui.analytics
    ```
    Start with the Safe profile. Only move to Balanced after reading the tradeoff notes for its 11 extra entries, and to Agressive after reading the 9 highest-tradeoff entries.

---

## Useful commands

### Understanding the debloat commands

This repository uses the `pm uninstall` command, which removes the application for the current user (`user 0`).

*   `pm uninstall -k --user 0 <package_name>`
    *   This command uninstalls the app for the current user (`user 0`). The `-k` flag keeps the app's data and cache. This makes the uninstallation reversible. This is the recommended and safest method.

*   `pm disable-user --user 0 <package_name>`
    *   This command disables the app for the current user. The app is not removed, just disabled. It's a less aggressive alternative to uninstalling.

*   `cmd package uninstall --user 0 <package_name>`
    *   This is another way to uninstall a package. In some cases, it can be more "permanent" but is still generally reversible.

### How to find a package name

To find the package name of an app you want to remove, you can use the following command from within the `adb shell`:

```shell
pm list packages | grep '<query>'
```
Replace `<query>` with a part of the app's name (e.g., to find the music player, you could use `grep 'player'`). To see packages already removed for the user, run `pm list packages -u`.

### How to restore a removed app

If you accidentally removed an app you need, you can reinstall it with the following command from your computer's terminal:

```shell
adb shell pm install-existing --user 0 <package_name>
```
For example, to restore Android Auto:
```shell
adb shell pm install-existing --user 0 com.google.android.projection.gearhead
```

---

## Troubleshooting & common fixes

If something breaks after debloating, see [troubleshooting.md](troubleshooting.md) for restore commands (Android Auto, Bluetooth, OTA updates, Theme Manager, dialer/SMS, Hey Google).

---

## Contributing

You are welcome to contribute to this project! If you find an app that can be safely removed, or if you have improvements for the lists, please open an issue or a pull request. If you fork this for your own device, re-verify `tested`/`present` from your own results rather than trusting mine.

## License

This project is open source and available under the [MIT License](LICENSE).
