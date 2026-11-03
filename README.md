# Photobesok Booth OS — Offline Trial v0.2

Independent Android Java prototype. No login, QRIS, server, analytics, subscriptions, or external HTTP calls. `INTERNET` Android permission is used solely to test local printer TCP port 515; it does not require internet access.

## Included
- Android camera intent with a 3-second delay before launching the camera app (the camera app's own shutter is still manual).
- Flexible output presets: 4R portrait/landscape, 945×2126 strip, square, or custom pixel dimensions.
- Optional transparent PNG overlay selected from local files, scaled to canvas size.
- Image preview and local PNG save via MediaStore.
- Printer IP / TCP 515 connectivity check (NOT a functional LPR print driver).
- Android Print Framework PDF print flow. Requires a separately installed/configured Android print service compatible with your printer. Paper sizing/margins are controlled by the print service and may differ from pixel dimensions.

## Important limitations
This is source code, not a compiled APK. Build with Android Studio and Android SDK 35. Not tested on Xiaomi Pad 7 or Epson L8050. Camera intent often returns a low-resolution thumbnail; production app should use CameraX/Camera2 with full-resolution capture, timer and kiosk session state. Only a single photo is composed, with optional PNG overlay; multi-slot JSON templates and automatic LPR/LPD printing are future work. Wi-Fi Direct pairing is done in Android Wi-Fi settings; the app uses the resulting local IP connection.

## Build
Open this directory in Android Studio, install Android SDK 35, sync Gradle, then Build > Build APK(s). The resulting APK is normally `app/build/outputs/apk/debug/app-debug.apk`. A PC or cloud Android build environment is needed unless you have a working Android-based Gradle toolchain.

## Security
No embedded credentials or telemetry. This is not a reverse-engineered copy of proprietary OurBooth code or artwork.
