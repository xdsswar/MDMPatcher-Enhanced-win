
# MDMPatcher Enhanced
This patcher helps bypass MDM on iOS devices (iOS 15+ and 64-bit devices up to iPhone 13) using macOS (10.13+). It allows the device to skip MDM configuration profiles, often required by corporations or institutions, without triggering errors during device setup.

<img src="https://github.com/fled-dev/MDMPatcher-Universal/blob/601144f6fa640c9d932ab51b52dd8637c32fc2df/screenshots/app.png" style="width:700px;">

## Changes from the Original Repository
In this fork, I’ve made the following improvements and bug fixes:
- **Improved documentation:** Rewrote the instructions for better clarity, including detailed steps for patching and troubleshooting common issues.
- **Bug fixes:**
  - Replaced empty string comparisons with isEmpty: This improves performance by avoiding unnecessary string literal comparisons. 
  - Removed redundant optional initialization: Swift automatically initializes optionals with nil, so explicitly initializing them with nil was redundant and cleaned up.
  - Replaced weak @IBOutlets with strong references: Weak references were causing potential crashes or undefined behavior, so I replaced them with strong references to keep objects alive when needed.
- **Additional troubleshooting section:** Added a "Typical Issues" section to help users troubleshoot errors such as app crashes, permission issues, and patching errors.

## Requirements
- macOS 10.13+ (Intel/M1)
- Compatible iOS device (64-bit, up to iPhone 13)
- MDMPatcher Enhanced App
- IPSW file for your specific device (download from [ipsw.me](https://ipsw.me))

## Instructions
- Download the correct IPSW file for your device from [ipsw.me](https://ipsw.me).
  - To find the correct IPSW file for your iOS device:
    - Look up the model number on the back of your device (e.g., A1567).
    - Match the model number with the device name using a website like [The iPhone Wiki](https://www.theiphonewiki.com/wiki/Models). For example, A1567 corresponds to the iPad Air 2.
    - **Choose between Cellular and Wi-Fi versions:** If your device has a SIM card slot, download the Cellular IPSW; otherwise, download the Wi-Fi only version.
- Put your iOS device into recovery mode.
  - **For iPads without a Home button:** Press and hold the Top button while connecting it to your computer. Keep holding until the recovery mode screen appears.
  - **For iPads with a Home button:** Hold the Home button while connecting it to your computer. Keep holding until the recovery mode screen appears.
  - **For iPhones with Face ID or iPhone 8 and later:** Press and hold the Side Button while connecting it to your computer. Keep holding the button until the recovery mode screen appears.
  - **For iPhone 7 and 7 Plus:** Hold the Volume Down button and connect it to your computer.
  - **For iPhone 6s and earlier:** Hold the Home Button while connecting it to your computer.
- Once in recovery mode, a message will appear on your computer asking if you want to update or restore the device. **Hold the OPTION key** on your keyboard, then click either **Update** or **Restore**. This will allow you to choose the IPSW file you downloaded for your device.
- After restoration, follow initial setup **until you reach the Wi-Fi selection** screen. **Do NOT connect to ANY network!**
- Open the MDMPatcher app on your Mac.
- Disable SIP if the app won’t open (for M1 Macs: use csrutil disable in recovery mode terminal).
  - Read more at [developer.apple.com](https://developer.apple.com/documentation/security/disabling-and-enabling-system-integrity-protection)
- **Important:** Before opening the MDMPatcher app, open Finder, click on your iPad, and wait for it to finish activating (it will show "Get Started"). You may need to unplug and reconnect the cable if you encounter issues.
- When your device info shows in MDMPatcher, click "PATCH" to complete the process.
- After reboot, follow the remaining setup instructions on the device.

## Typical Issues
### Problem: Unable to Open MDMPatcher Enhanced
You might encounter a security warning preventing the app from opening, as shown below.
<br>
<img src="https://github.com/fled-dev/MDMPatcher-Universal/blob/a224cb323b3cc203152437830bdb135ad4548b2d/screenshots/could_not_verify.png" style="height:400px;">
<br>
**Solution:**
1. Right-click the app and select Open.
2. If the app still won’t open, go to **System Settings > Privacy & Security** and under the Security section, allow the app by clicking Open Anyway.
<br>
<img src="https://github.com/fled-dev/MDMPatcher-Universal/blob/a224cb323b3cc203152437830bdb135ad4548b2d/screenshots/settings_blocked.png" style="height:400px;">

---

### Problem: App Instantly Crashes on Launch
If the MDMPatcher Enhanced app crashes immediately upon opening, this is likely due to macOS's System Integrity Protection (SIP) blocking the app.

**Solution:**
1. Boot your Mac into Recovery Mode.
2. Open Terminal in Recovery Mode.
3. Type `csrutil disable` and press Enter.
4. Restart your Mac, then try opening the app again.

Be cautious when disabling SIP, as it reduces system security. Read more about it at [developer.apple.com](https://developer.apple.com/documentation/security/disabling-and-enabling-system-integrity-protection)

---

### Problem: Error Occurs While Patching
If an error occurs during the patching process, it’s often because the device hasn’t fully completed activation.

**Solution:**
1. Before opening MDMPatcher, open Finder on your Mac.
2. Click on your device in the Finder sidebar.
3. Wait for the device to fully activate (it will display "Get Started" when ready).
4. Then, proceed with the patching.

This should resolve most patching errors.

## Final Thoughts
I hope this repository helps some of you save time, as I spent more time than necessary troubleshooting these issues myself. Feel free to reach out if you have any questions or need further assistance!

You can connect with me on [LinkedIn](https://linkedin.com/in/paul-roder/)
