# Vision 2 — Lesson 1: "Languages of the World" (Grade 11 Book Companion)

A mobile-first, fully interactive Single Page Application (SPA) that acts as a companion to **Vision 2, Lesson 1**. Built with plain HTML, CSS and Vanilla JavaScript (no frameworks). The app currently focuses on understanding the *meaning* of words and sentences; grammar teaching and pronunciation drills are placeholders for later.

## Structure — the app is the book's Table of Contents

The main menu shows section cards mapped to the book's pages:

| Section | Book pages |
|---|---|
| 📖 Warm-up & Vocabulary | Pages 5–7 |
| 💬 Conversation 1: Mr. Saberian | Page 4 |
| 📑 Reading: Endangered Languages | Pages 9–10 |
| 💬 Conversation 2: Shopping | Page 18 |
| 🗂️ Flashcard Review | saved-words badge |

Grammar and pronunciation appear only as "به‌زودی" (coming soon) placeholders for now.

Each section opens a sub-menu with three modes:

- **🔵 Normal Mode (Read)** — the text exactly as in the book; every word is a tappable `<span>` showing a floating Persian tooltip (from the book's Word Banks) and speaking the word at 0.65× speed; a 🔊 button reads each paragraph (twice, 0.65×).
- **🟢 Easy Mode (Practice)** — scaffolded learning: learn each new word once (auto TTS, add to flashcards), then build phrases → full sentences from a shuffled word bank with tap *and* drag-and-drop, instant per-word validation (green = right position, red + shake + buzz = wrong) and a 💡 Hint button that reads the target sentence. No word is taught twice.
- **🎧 Listening Mode** — fill-in-the-blank questions from the section text with 4 options, auto audio playback and instant green/red feedback.
- **🗂️ Flashcards** — one shared 3D-flip review deck for all saved words.

## Audio / TTS

Uses the browser's native `window.speechSynthesis` API. The global helper:

```js
speak(text, repeat = 2, rate = 0.65)
```

Every word, phrase and sentence automatically plays **twice at 0.65× speed**, with 🔊 icons next to every English word and sentence.

## Run it

Just open `index.html` in any modern browser (Chrome/Edge recommended for TTS voices) — no build step or server required.

## Adding more sections

Content lives in the `SECTIONS` array: each entry holds the section's `reading` lines, `easySequence` steps and `listeningData` items, parsed from the corresponding book pages. A merged `DICT` object serves tooltips across the whole book.
