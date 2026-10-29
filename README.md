# GOLAN NotifSaver

[Feature and use guide](GUIDE.md) · [دليل الاستخدام العربي](GUIDE.ar.md) · [Releases: APK and complete source](https://github.com/GOLAN2CODE/golan-notification-saver/releases)

[العربية](README.ar.md)

Android notification archive **1.0.14 / code 15**, package `com.ibngolan.notifsaver`; Android 7/API 24 minimum, SDK/target 36. This is the current source snapshot and unchanged latest delivered debug APK.

## What it does

- Saves future eligible notifications for explicitly configured VIP names/conversations, with text/media choices.
- Recognizes notification packages for WhatsApp/Business, Telegram/Plus, Messenger, Instagram, Signal and Viber. These package filters do not guarantee media support for every app.
- Processes notification message batches, avoids duplicate events, and attempts to retain available images, audio and video from readable notification attachments or accessible WhatsApp media files.
- Offers VIP/message search and filters, media viewing, export through Android's file picker, confirmed per-message/category/all-message deletion and retention settings.
- Exports a local ZIP backup and restores/merges records with duplicate and media-integrity checks; shows permission health and supports a biometric lock.

## Install and set up

Download the debug APK from release assets and verify its SHA-256 against `SHA256SUMS.txt`. Enable installation for its opening app, then install. In Android settings manually enable notification access, add VIP entries matching the names in notifications, choose text/media options, and grant optional media access when needed. On Android 9/API 28, the media-permission shortcut has a known limitation: open Android App info > Permissions manually and grant storage access. On Android 11+ the app can request all-files access for original WhatsApp media; grant only if you want that capability.

Capture begins with new eligible incoming notifications after setup. Send a harmless new message from another account and confirm the retained file before deleting anything in the source app. Updating requires the same signing key; uninstalling/data clearing removes private saved data, so export and protect a backup first. Exported backup ZIPs contain sensitive messages/media and are not encrypted by this backup format.

## Full source and build

Download `golan-notification-saver-1.0.14-source.zip` from release assets and **extract it before building**. The ZIP contains the complete sanitized application code, existing tests, resources and Gradle wrapper. A repository README alone is not the source project.

Install JDK 17 and Android SDK 36. Configure your local SDK through environment variables or an untracked `local.properties` containing `sdk.dir`. Run from the extracted root:

```powershell
.\gradlew.bat :app:assembleDebug
```

Linux/macOS: `chmod +x gradlew && ./gradlew :app:assembleDebug`. The portable source uses the normal `app/build/outputs/apk/debug/app-debug.apk` output location; the original developer-specific output path was removed from this copy only. Network access is needed to download Gradle/Maven dependencies. A locally built debug certificate may differ from the delivered APK. Packaging performed no new build or tests.

## Limits and validation

This is a notification archive, not universal deleted-message recovery. It cannot recover older unseen notifications, prevent sender deletion, read every private app directory or guarantee every attachment. Hidden/muted notifications, name matching, revoked URI grants, Android restrictions and source-app changes affect capture. Fallback searches for recent WhatsApp media can misassociate files during concurrent arrivals; verify important exports. A notification preview can differ from the original file.

The existing 1.0.14 report records successful unit/build/lint checks, 19 emulator instrumentation tests and a user's successful Motorola text/image/audio trial. Those are historical bounded results; this packaging did not repeat them or establish all-app/device/video acceptance. The delivered APK metadata and hash were checked, and source files match the current build-stage source.

No phone backups, personal messages, screenshots, logs, build caches or historical device reports are included. No project-wide license was present or assigned; see [LICENSE-STATUS.md](LICENSE-STATUS.md) and [THIRD_PARTY.md](THIRD_PARTY.md).
