# GOLAN NotifSaver: feature and use guide

[العربية](GUIDE.ar.md) · [Overview](README.md) · [Downloads and full source](https://github.com/GOLAN2CODE/golan-notification-saver/releases)

## Purpose and setup

Version **1.0.14 / code 15** runs on Android 7/API 24 or newer. It keeps an independent local record of future eligible notifications for VIP names/conversations you configure. Its input is information Android and the messaging app expose in notifications, plus readable media sources; it does not read a messaging service's complete conversation history.

Install the debug APK from Releases after checking its checksum. Manually enable the app's notification access in Android settings, then add the VIP name as it appears in incoming notifications. Choose whether to keep text and media for that entry. The package filters recognize WhatsApp/Business, Telegram/Plus, Messenger, Instagram, Signal and Viber; that list is not a guarantee that every attachment from every listed app can be saved.

Send a harmless new incoming message from another account to test your configuration. Confirm the saved text and open the retained file before deleting anything from the original conversation. Outgoing messages or grouped summary notifications are not a substitute for that test.

## Text, photos, audio and video

The listener separates eligible message items in a notification batch and applies duplicate checks. It attempts to retain image, audio and video attachments offered with readable access. For WhatsApp, it can also look for accessible downloaded media files. A saved row is not proof that its original attachment was copied: inspect the media result and open it.

Notification pictures can be previews rather than originals. Missing URI grants, files that have not finished downloading, Android storage restrictions, hidden notifications and changes in the source app can prevent capture. A fallback search for recent WhatsApp files can associate the wrong file when several arrive together. Verify important photos/audio manually, especially albums and concurrent messages. Support for a notification package does not establish universal video capture or recovery after deletion.

## Permissions and everyday management

Grant optional media access only when you want those functions. On Android 9/API 28, the media-permission shortcut has a known limitation: open Android's App info > Permissions manually to grant storage access. Android 11+ can require optional all-files access for original WhatsApp media. Permission-health information helps identify missing access; granting storage does not replace the separate notification-access setting.

Use VIP/message search and filters to locate records. Open conversations and the media viewer to review saved items, and export text or available media through Android's file picker when you need an independent copy. Confirmed deletion supports individual messages, categories, conversation contents or all messages. Deleting an archive item manages this app's saved data, not the source application's conversation. Retention settings control how long saved media is kept. A biometric lock is also available.

## Backup, limits and costs

The local ZIP backup includes saved records/media; restore checks integrity, merges records and skips duplicates. **The exported ZIP is not encrypted.** Anyone who can read that ZIP may read its messages and media, so choose a private destination and protect any copy you share or upload. Uninstalling or clearing app data removes private saved data; export needed records first.

This is not universal deleted-message recovery: it cannot retrieve old content it never captured or prevent sender deletion. The APK has no Internet permission, and no personal billed API key/payment integration was found in the reviewed source. It runs on the phone without your computer, Codex or this chat. The original messaging apps and mobile data can still have their own costs. Android notification access and background restrictions still determine whether future capture operates.
