# English Lesson 1 — The Value of Knowledge (Grade 11)

A mobile-first, fully interactive Single Page Application (SPA) for English language learning, built with plain HTML, CSS and Vanilla JavaScript (no frameworks).

## Features

- **🏠 Main Menu (RTL Persian UI, 4 modes)** — Easy, Normal (Reading), Listening, and Flashcards (badge shows saved-word count).
- **🟢 Easy Mode** — Scaffolded learning: learn each new word (auto TTS), then build phrases and full sentences from a shuffled word bank with tap *and* drag-and-drop, instant per-word validation (green = correct position, red + shake + buzz = wrong), and a 💡 Hint button that reads the full sentence.
- **🔵 Normal Mode (Reading)** — The story + dialogue, every word tappable with a floating Persian tooltip and spoken pronunciation, plus a TTS button for each paragraph.
- **🎧 Listening Mode** — Fill-in-the-blank questions generated from the reading text with 4 multiple-choice options, auto audio playback and instant audio feedback.
- **🗂️ Flashcard Review** — 3D flipping cards for words saved to `localStorage`.

## Audio / TTS

Uses the browser's native `window.speechSynthesis` API. The global helper:

```js
speak(text, repeat = 2, rate = 0.65)
```

Every word, phrase and sentence automatically plays **twice at 0.65× speed**. Speaker buttons (🔊) appear next to every English word and sentence.

## Run it

Just open `index.html` in any modern browser (Chrome/Edge recommended for TTS voices) — no build step or server required.

## Adding more lessons

The content is parsed into three plain JavaScript structures at the top of the `script` block:

- `dict` — vocabulary word → Persian meaning
- `easySequence` — scaffolded word → phrase → full-sentence steps
- `reading` — story + dialogue lines
- `listeningData` — fill-in-the-blank items (audio text, display text, correct answer, 4 options)
