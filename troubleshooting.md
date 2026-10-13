# Troubleshooting & common fixes

If you use the balanced or agressive debloat lists, some features might break. Here are some common fixes to restore essential functionality by running these commands from your computer's terminal.

*   **To fix Android Auto issues:**
    ```shell
    adb shell pm install-existing --user 0 com.google.android.projection.gearhead
    ```

*   **To fix Bluetooth functionality:**
    ```shell
    adb shell pm install-existing --user 0 com.xiaomi.bluetooth
    ```

*   **To re-enable OTA Updates:**
    ```shell
    adb shell pm install-existing --user 0 com.miui.cloudservice
    adb shell pm install-existing --user 0 com.xiaomi.micloud.sdk
    adb shell pm install-existing --user 0 com.miui.micloudsync
    adb shell pm install-existing --user 0 com.miui.cloudbackup
    ```
    Then reboot and check for updates in Settings.

*   **To restore Theme Manager:**
    ```shell
    adb shell pm install-existing --user 0 com.android.thememanager
    ```

*   **Dialer/SMS issues after Agressive:** it removes the AOSP dialer/SMS in favor of alternative dialer/SMS apps. Confirm the alternative SMS app holds the SMS role and the alternative dialer handles calls; if not, reinstall the stock apps or re-check default-app settings.

*   **Hey Google stopped working:** expected — Balanced removes both hotword enrollment packages. Reinstall `com.android.hotwordenrollment.okgoogle` and `com.android.hotwordenrollment.xgoogle` to get it back.

*  **OTA updates:** The 4 Mi Cloud packages listed in the agressive profile generally don't break OTA updates on some HyperOS builds. If after an agressive debloat your OTA updates stop working, you should consider restoring them. You can check whether you have any new updates available at Settings > About Phone > tap the HyperOS logo > Check for updates.
