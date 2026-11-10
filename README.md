# VOCABIFY — free personal vocabulary trainer

This is an offline-first installable web app designed to run on Android. It uses no paid APIs, subscriptions, accounts, analytics or advertising. Word data is stored in the browser's local storage on the device.

## Install on Android

1. Put this folder on a static HTTPS host you control or open it through a local web server on your phone/computer. Service workers (needed for offline install) require HTTPS or localhost.
2. Open the hosted address in Chrome on Android.
3. Open Chrome's menu (⋮) and choose **Install app** or **Add to Home screen**.
4. Launch VOCABIFY from the new home-screen icon. Open it online once so its app shell is cached; then the core app works offline.

A normal `file://` open will show the interface but will not enable PWA installation/offline service-worker caching.

## Features

- Add words and optional meanings/parts of speech.
- Optional free dictionary lookup through dictionaryapi.dev (internet required; no key).
- Offline sentence structure checks: word presence, sentence length, repeated adjacent words and basic capitalization/punctuation hints.
- Human meaning confirmation before a successful recall is recorded.
- Spaced repetition defaults: 1, 3, 7, 14, 21, 30, 60, 90 days.
- Failed recall schedules the word for tomorrow; Hard/Good/Easy adjust the next interval.
- Per-word custom intervals and manual next-review date.
- Streak, progress levels, review statistics and JSON backup/restore.

## Honest checking limitation

There is no general-purpose offline semantic AI in this build. A free, reliable cloud AI would require a service with usage limits or infrastructure; a paid API/token requirement would violate the no-cost requirement. The app therefore uses deterministic local checks and asks the learner to confirm meaning. This prevents claiming that a keyword-overlap heuristic can truly understand every sentence. It does not falsely reject a sentence solely because it differs from an example.

## Privacy and storage

All learning records are stored in this browser's localStorage. Clearing browser/app data may erase them, so export backups regularly. Import/export files remain under your control. The optional dictionary lookup sends only the requested word to dictionaryapi.dev.

## Android APK

This delivery is an installable PWA, not a signed native APK. It can be installed on Android from Chrome. A native APK would require an Android SDK/Gradle build environment and signing; those tools are not present in this build environment.
