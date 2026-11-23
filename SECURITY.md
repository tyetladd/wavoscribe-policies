# Security Policy

Wavoscribe for Android. Last updated 23 November 2026.

What protects your data, and where each protection stops, written so each claim can be checked.
What data the app holds and sends is in the [privacy policy](PRIVACY.md).

## The design: nothing to send

Speech is recognized on the phone. There is no server of ours, no account and no cloud recognition,
so there is no copy of your audio or text anywhere but your device to be leaked, subpoenaed or
breached. The one network use is downloading speech models (below).

## Data at rest

- Recordings (16 kHz WAV files), the history database (including the coordinates *Add location*
  keeps), the personal dictionary and the models are kept in the app's private storage. Android's sandbox keeps other apps from reading it, and Android's file-based encryption
  encrypts it while the phone is locked.
- The app does not add encryption of its own on top. Someone who can unlock your phone, or a rooted
  phone running hostile software, can read it. If that matters to you, turn off Settings › Recording ›
  *Keep recordings* and delete history you do not need.
- `allowBackup="false"`: the data is excluded from Android's cloud backup and device-to-device transfer.

## The microphone

The microphone is open only while a dictation runs. *Record in the background* (off by default) is
the only way it stays open after you leave the app, and then Android shows a notification for as
long as it does.

With Settings › Recording › *Microphone* on *Car or headset when connected* (off by default), the
audio comes over the Bluetooth hands-free link from the car or headset, the same link a phone call
uses, and is protected only as well as that link is. The link is opened when a dictation starts and
released when it pauses or stops; your audio and text are never sent the other way. If the car or headset goes away
mid-dictation, the recording stops there and what was recorded is kept.

## Model downloads

- Models come from Hugging Face over HTTPS (TLS by rustls, checked against Mozilla's root certificates built into the app) and are
  written only inside the app's model folder: a file name that would leave it is refused.
- An interrupted download resumes where it stopped.
- A model is data read by the speech engine, not code. The app does not run anything it downloads.

## Models you add

A model file you add yourself is untrusted input: the app cannot know who made it. Before it is kept,
the app checks that it is a GGUF file of version 3 in wavo's format, that it is a Whisper, Parakeet,
GigaAM or Moonshine model, and that it is at most 2.5 GB; a file that fails the check is refused and
deleted, but its row, with the reason, stays in Settings › Models until you delete it; the app keeps a small record there with the name you gave it and the original file's name. The file is copied into the app's own model folder and read as data by the speech
engine, which runs on the phone with the app's own permissions and nothing more. These checks are
on the file's format and size; they do not tell you that a model is accurate or that its maker can
be trusted, so add only files from sources you trust. Adding a model uses no network connection.

## Sharing

A recording you share goes out as a read-only content link to the one app you pick, through
Android's FileProvider; the app's folders are not exported otherwise. Shared text carries the
dictation's name, time and text — and, when *Add location* was on, the time-and-place line the text
ends with — and nothing else.

## Builds

Releases on Google Play are built from a recorded source commit, which Settings › About shows with
the build number, so a build can be traced to its exact source.

## Reporting a problem

Please report security problems privately to [wavoscribe@sshmanagerpro.app](mailto:wavoscribe@sshmanagerpro.app), not in a public issue. Describe what you
found and how to reproduce it; you will get a reply.
