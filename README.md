# IRONLOG

A self-contained gym workout tracker. One HTML file, no build step, no server, no dependencies.

**Use it:** open the GitHub Pages URL on your phone → Share → **Add to Home Screen**. It launches like a native app.

## Features

- Log exercises by session, organised across Chest / Shoulders / Back / Legs / Biceps / Triceps
- Per-set weight (kg) and reps with quick steppers; add/delete sets and exercises
- "Last time" reference on every exercise so you know what to beat (green ▲ when you beat it)
- Weekly set-volume meters per muscle group (10–20 sets/week growth zone)
- Per-exercise progress chart: top-set weight over session volume
- Export / import your full log as a JSON backup file
- Optional PIN lock (see Security)

## Security model

- **All data stays on your device.** Workouts live in your browser's `localStorage`. Nothing is ever sent to a server — this repo hosts static code only.
- **PIN lock**: optional app lock. The PIN is stored only as a PBKDF2-SHA256 hash (150,000 iterations, random 16-byte salt) via the WebCrypto API — never in plaintext. The app locks on open and re-locks after 5 minutes in the background. Note: a client-side lock deters casual access to the UI; it is not encryption of the underlying data.
- **No secrets exist in this project.** There are no API keys, tokens, or credentials anywhere in the code. `.gitignore` blocks `.env` and key files defensively, and a gitleaks workflow scans every push so nothing secret can land in the repo unnoticed.
- The published Pages site is public code; your data never leaves your phone.

## Backups

Your log is only as safe as your device. Use **Export Backup** (Log tab → Data) regularly; restore anywhere with **Import Backup**.
