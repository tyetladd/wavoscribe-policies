# Privacy Policy

Wavoscribe for Android. Last updated 22 November 2026.

**The short version.** Wavoscribe recognizes your speech on your phone. Your voice, your recordings
and the text made from them never leave it unless you share them yourself. The app has no account,
no analytics, no advertising, no crash reporting and no tracking of any kind. It uses the network for
one thing only: downloading the speech models you choose, from Hugging Face.

## 1. Who this is about

Wavoscribe ("the app") is a smart voice recorder and dictation app for Android, published on Google Play as
`com.wavoscribe.app`. This policy explains what the app does with your data. Contact: see section 9.

## 2. What stays on your device

All of the following is kept in the app's private storage, which other apps cannot read, and is
never sent anywhere by the app:

- **Microphone audio.** It is recorded only while a dictation runs and is processed on the phone. With
  Settings › Recording › *Microphone* on *Car or headset when connected* (off by default), it comes
  from a connected car's or headset's Bluetooth microphone instead, as a hands-free call's would; it
  is still recorded and processed on the phone. Your audio and text are never sent to the car or
  headset; only the app's spoken phrases and whether a dictation is recording or paused may reach it
  (section 3).
- **Recordings.** With Settings › Recording › *Keep recordings* (on by default), each dictation's audio
  is saved as a WAV file so you can play it back or transcribe it again. While a dictation runs, its
  audio is written to a file on the phone as it is recorded, so a long recording doesn't fill the
  memory. Beside each kept recording the app stores when it started and when it resumed after each
  pause, to stamp turns with the time of day, and the words each model heard in it with their times,
  so *Process…* can tell the speakers apart without transcribing it again; both are deleted with the
  recording. Turn the setting off and only the text is kept: the file is deleted when the dictation
  ends, or the next time the app starts if it closed during one.
- **History.** The text of each dictation, its name, the model used, how long it took and when it was
  made.
- **Downloaded models**, your personal dictionary and your settings.
- **Model files you add.** A speech model file you add yourself (Settings › Models › *Add a model…*, or
  *Open with* / Share from another app) is copied into the app's private storage, with the name you
  give it, and stays there until you delete it. The file you picked stays where it was; the app does
  not change or delete it. A file that fails the app's check is deleted from the app, but a small
  record stays in Settings › Models, with the name you gave it, the original file's name and the
  reason, until you delete it. Adding a model uses no network connection: you download the file yourself,
  with your own browser.

The app sets `allowBackup="false"`, so none of this is copied into Android's cloud backup.

## 3. What leaves your device, and when

| Data | Goes to | When |
|---|---|---|
| A request for a model file (the file's name; your IP address, as with any download) | Hugging Face (`huggingface.co`) | Only when you tap *Download* for a speech model in Settings › Models, or turn on Settings › Conversation, which downloads its two speaker models once. No audio, text or identifier of yours is sent. |
| Text or a recording you share | The app you pick in Android's share sheet | Only when you tap *Share text* or *Audio*. The app you choose then handles it under its own policy. |
| Text you copy | Android's clipboard | Only when you tap *Copy* or tap a dictation in History. Other apps you use may read the clipboard. |
| Whether a dictation is recording or paused (no title, no text, no audio) | Android, which passes it to a connected car or headset | Only while a dictation runs with *Record in the background* on, so the steering wheel's or headset's play/pause button can pause and resume it. |

Hugging Face's handling of download requests is described in
[its privacy policy](https://huggingface.co/privacy). The downloads use HTTPS.

Nothing else is sent: no audio, no transcripts, no usage statistics, no device identifiers. The
"Start recording" shortcut on the app's icon only opens the app; it sends nothing.

## 4. Permissions

- `RECORD_AUDIO` — to hear you while a dictation runs. The microphone is never opened at any other time.
- `INTERNET` — only to download speech models (section 3).
- `MODIFY_AUDIO_SETTINGS` — only with Settings › Recording › *Microphone* on *Car or headset when
  connected*: to record from a car's or headset's Bluetooth microphone while a dictation runs. Using it
  may pause the car's music, as a call would.
- `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_MICROPHONE`, `POST_NOTIFICATIONS` — only with Settings ›
  Recording › *Record in the background* (off by default): they keep a dictation going after you leave
  the app, and show a notification with its time and pause and stop while it does.

## 5. What we do not do

- No accounts and no sign-in
- No analytics, advertising or tracking SDKs, and no advertising identifiers
- No crash reporting or telemetry
- No cloud speech recognition: every model runs on the phone
- We do not collect, sell, rent or share personal data, because the app sends us none

## 6. Retention and deletion

Everything is on your phone and stays until you delete it. Delete a dictation from History and its
text is removed; deleting the last version of a recording also deletes its audio file. Models, including the
ones you added, can be deleted in Settings › Models; for a model you added, the original file you
picked is not touched. Clearing the app's storage in Android's settings, or uninstalling the app,
removes all of it. We hold no copy, so there is nothing for us to delete.

## 7. Children

The app is not directed at children under 13, and it collects no personal data from anyone.

## 8. Changes

If this policy changes, the new version is published at this address with a new date at the top. A
change to what leaves the device will be stated in the app's release notes too.

## 9. Contact

Questions about this policy: [wavoscribe@sshmanagerpro.app](mailto:wavoscribe@sshmanagerpro.app).
