# Google Pixel Windows 11 Troubleshooting

A practical troubleshooting reference for Google Pixel USB connections, Windows 11 device detection, Android Debug Bridge (ADB), and Fastboot.

## Quick USB connection checklist

1. Use a USB-C cable that supports data transfer.
2. Connect the phone directly to the computer.
3. Unlock the Google Pixel.
4. Open the USB notification and select File transfer.
5. Check whether the phone appears in Windows File Explorer.
6. If not, inspect Portable Devices and Other devices in Windows Device Manager.

## Check ADB connectivity

Download Google's official Android SDK Platform-Tools:

https://developer.android.com/tools/releases/platform-tools

Enable USB debugging only when required, and authorize your trusted computer.

In PowerShell, from the Platform-Tools folder, run:

```powershell
.\adb devices
```

Common results:

- device: Connected and authorized
- unauthorized: Check the authorization prompt on your Pixel
- offline: ADB communication is not ready
- Empty list: Check the USB connection, drivers, and debugging settings

## Restart the ADB server

```powershell
.\adb kill-server
.\adb start-server
.\adb devices
```

## Fastboot detection

If your Pixel is already in bootloader mode:

```powershell
.\fastboot devices
```

Do not unlock the bootloader or flash partitions simply to troubleshoot a USB connection.

## Additional troubleshooting

For a detailed guide covering Windows Device Manager, USB drivers, ADB authorization, and Fastboot detection, see:

[Google Pixel Not Detected by Windows 11 — GPixel.pro](https://gpixel.pro/guides/pixel-not-detected-by-windows)

## Official references

- [Android SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools)
- [Google USB Driver](https://developer.android.com/studio/run/win-usb)
- [Pixel file transfer help](https://support.google.com/pixelphone/answer/2840804)

## Disclaimer

This repository provides general troubleshooting information. It is not affiliated with or endorsed by Google. Follow official documentation and back up important data before advanced device operations.
