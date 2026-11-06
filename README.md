# Vision 2 — Lesson 1: "Understanding People" (Grade 11 Book Companion)

A mobile-first, fully interactive Single Page Application (SPA) that acts as a companion to **Vision 2, Lesson 1** (کتاب انگلیسی ۲، پایه یازدهم). Built with plain HTML, CSS and Vanilla JavaScript (no frameworks).

## Structure — the app is the book's Table of Contents

Sections are labelled in the book's own style (`<Section> - Page N`), using the printed page numbers of the textbook:

| Section | Book pages |
|---|---|
| 📖 Warm-up & Vocabulary | Pages 21-23 |
| 💬 Conversation 1 - Mr. Saberian | Pages 19-20 |
| 📑 Reading - Languages of the World | Pages 24-27 |
| 💬 Conversation 2 - Shopping | Page 34 |
| 🗂️ Flashcard Review | saved-words badge |

Each section opens a sub-menu with two modes (the listening drill is part of practice, not a separate mode):

- **🔵 Normal Mode (Read)** — the text exactly as in the book; every word is a tappable `<span>` showing a floating Persian tooltip (from the book's Word Banks) and speaking the word at 0.65× speed. Under every paragraph the **full Persian translation** is shown, and a 🔊 button reads the whole paragraph (twice, 0.65×).
- **🟢 Easy Mode (Practice)** — scaffolded learning: learn each new word once (auto TTS, add to flashcards), then build phrases → full sentences from a shuffled word bank with tap *and* drag-and-drop, instant per-word validation (green = right position, red + shake + buzz = wrong) and a 💡 Hint button that reads the target sentence. When the build steps finish, the **listening fill-in-the-blank questions of the section run at the end of the same flow** (4 options, auto audio, instant green/red feedback). No word is taught twice.
- **🗂️ Flashcards** — one shared 3D-flip review deck for all saved words.

## Audio / TTS

Uses the browser's native `window.speechSynthesis` API. The global helper:

```js
speak(text, repeat = 2, rate = 0.65)
```

Every word, phrase and sentence automatically plays **twice at 0.65× speed**, with 🔊 icons next to every English word, paragraph and sentence.

## Run it

Just open `index.html` in any modern browser (Chrome/Edge recommended for TTS voices) — no build step or server required.

## Adding more sections

Content lives in the `SECTIONS` array: each entry holds the section's `title`, book `pages`, `reading` lines (each with `text` and a Persian `fa` translation), `easySequence` steps and `listeningData` items, parsed from the corresponding book pages. A merged `DICT` object serves tooltips across the whole book.
