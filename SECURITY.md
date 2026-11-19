# Security Policy

Wavoscribe for Android. Last updated 19 November 2026.

What protects your data, and where each protection stops, written so each claim can be checked.
What data the app holds and sends is in the [privacy policy](PRIVACY.md).

## The design: nothing to send

Speech is recognized on the phone. There is no server of ours, no account and no cloud recognition,
so there is no copy of your audio or text anywhere but your device to be leaked, subpoenaed or
breached. The one network use is downloading speech models (below).

## Data at rest

- Recordings (16 kHz WAV files), the history database, the personal dictionary and the models are kept in the app's private
  storage. Android's sandbox keeps other apps from reading it, and Android's file-based encryption
  encrypts it while the phone is locked.
- The app does not add encryption of its own on top. Someone who can unlock your phone, or a rooted
  phone running hostile software, can read it. If that matters to you, turn off Settings › Recording ›
  *Keep recordings* and delete history you do not need.
- `allowBackup="false"`: the data is excluded from Android's cloud backup and device-to-device transfer.

## The microphone

The microphone is open only while a dictation runs. *Record in the background* (off by default) is
the only way it stays open after you leave the app, and then Android shows a notification for as
long as it does.

## Model downloads

- Models come from Hugging Face over HTTPS (TLS by rustls, checked against Mozilla's root certificates built into the app) and are
  written only inside the app's model folder: a file name that would leave it is refused.
- An interrupted download resumes where it stopped.
- A model is data read by the speech engine, not code. The app does not run anything it downloads.

## Sharing

A recording you share goes out as a read-only content link to the one app you pick, through
Android's FileProvider; the app's folders are not exported otherwise. Shared text carries the
dictation's name, time and text and nothing else.

## Builds

Releases on Google Play are built from a recorded source commit, which Settings › About shows with
the build number, so a build can be traced to its exact source.

## Reporting a problem

Please report security problems privately to [wavoscribe@sshmanagerpro.app](mailto:wavoscribe@sshmanagerpro.app), not in a public issue. Describe what you
found and how to reproduce it; you will get a reply.
