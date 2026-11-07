# Vision 2 — Grade 11 English Book Companion

A mobile-first, fully interactive Single Page Application (SPA) companion to **Vision 2** (کتاب انگلیسی ۲، پایه یازدهم), built with plain HTML, CSS and Vanilla JavaScript (no frameworks).

## Home: the book's three lessons

The homepage lists the three lessons of the book; the student picks the lesson to study:

| Lesson | Book pages | Status |
|---|---|---|
| 1️⃣ Lesson 1 - Understanding People | Pages 15-47 | ✅ built |
| 2️⃣ Lesson 2 - A Healthy Lifestyle | Pages 49-79 | ✅ built |
| 3️⃣ Lesson 3 - Art and Culture | Pages 81-107 | ✅ built |

## Lesson path: Duolingo-style chunks in book order

Opening a lesson shows its chunks as a numbered path, ordered exactly like the textbook, each with its printed page number so the student can jump straight to the part they need:

| # | Chunk | Book pages | Status |
|---|---|---|---|
| 1 | 🗺️ Get Ready | Pages 15-18 | ✅ آماده |
| 2 | 💬 Conversation - Mr. Saberian | Pages 19-20 | ✅ آماده |
| 3 | 📖 New Words & Expressions | Pages 21-23 | ✅ آماده |
| 4 | 📑 Reading - Languages of the World | Pages 24-26 | ✅ آماده |
| 5 | 🔁 Vocabulary Development - Synonyms | Pages 27-28 | ✅ آماده |
| 6 | 🔤 Grammar - Countable & Uncountable Nouns | Pages 28-31 | ✅ آماده (آموزش + آزمون) |
| 7 | 🛒 Listening & Speaking - Shopping | Pages 34-35 | ✅ آماده |
| 8 | 🎙️ Pronunciation - Ten/Teen Numbers | Page 36 | به‌زودی |
| 9 | ✍️ Writing - Simple Sentences | Pages 37-45 | ✅ آماده |
| 10 | 🏁 What You Learned | Page 47 | ✅ آماده |

### Lesson 2 chunks (Pages 49-79)

| # | Chunk | Book pages | Status |
|---|---|---|---|
| 1 | 🗺️ Get Ready | Pages 49-52 | ✅ آماده |
| 2 | 💬 Conversation - A Couch Potato | Pages 53-54 | ✅ آماده |
| 3 | 📖 New Words & Expressions | Pages 55-57 | ✅ آماده |
| 4 | 📑 Reading - Having a Healthier and Longer Life | Pages 58-60 | ✅ آماده |
| 5 | 🔁 Vocabulary Development - Prefixes & Suffixes | Pages 61-63 | ✅ آماده |
| 6 | 🔤 Grammar - Present Perfect | Pages 64-67 | ✅ آماده (آموزش + آزمون) |
| 7 | 🎧 Listening & Speaking - Past Experiences | Pages 69-70 | ✅ آماده |
| 8 | 🎙️ Pronunciation - (Emergencies) Phrasal Verbs | Page 71 | به‌زودی |
| 9 | ✍️ Writing - Gerunds | Pages 72-76 | ✅ آماده |
| 10 | 🏁 What You Learned | Page 79 | ✅ آماده |

### Lesson 3 chunks (Pages 81-107)

| # | Chunk | Book pages | Status |
|---|---|---|---|
| 1 | 🗺️ Get Ready | Pages 81-84 | ✅ آماده |
| 2 | 💬 Conversation - Iranian Handicrafts | Pages 85-86 | ✅ آماده |
| 3 | 📖 New Words & Expressions | Pages 87-89 | ✅ آماده |
| 4 | 📑 Reading - Art, Culture and Society | Pages 90-92 | ✅ آماده |
| 5 | 🔁 Vocabulary Development - Antonyms | Pages 93-94 | ✅ آماده |
| 6 | 🔤 Grammar - Conditional Type I | Pages 95-98 | ✅ آماده (آموزش + آزمون) |
| 7 | 🎧 Listening & Speaking - Conditions & Future | Pages 99-100 | ✅ آماده |
| 8 | 🎙️ Pronunciation - Intonation of Conditionals | Page 101 | به‌زودی |
| 9 | ✍️ Writing - Infinitives | Pages 102-105 | ✅ آماده |
| 10 | 🏁 What You Learned | Page 107 | ✅ آماده |

Each lesson keeps its own path, so the home screen switches between them and the progress path always shows the chosen lesson's chunks.

Ready chunks open a sub-menu with two modes (listening is part of practice, not a separate mode):

- **🔵 Normal Mode (Read)** — the text exactly as in the book; every word is a tappable `<span>` showing a floating Persian tooltip (from the book's Word Banks) and speaking the word at 0.65× speed. Under every paragraph the **full Persian translation** is shown, and a 🔊 button reads the whole paragraph (twice, 0.65×).
- **🟢 Easy Mode (Practice)** — scaffolded learning: learn each new word once (auto TTS, add to flashcards), answer multiple-choice questions with instant correction, a Persian “why?” and audio, then build phrases → full sentences from a shuffled word bank with tap *and* drag-and-drop, instant per-word validation (green = right position, red + shake + buzz = wrong) and a 💡 Hint button that reads the target sentence. When the build steps finish, the **listening fill-in-the-blank questions of the chunk run at the end of the same flow** (4 options, auto audio, instant green/red feedback). No word is taught twice.
- **📚 Grammar Mode** — 8 teaching cards (rule + English examples with 🔊 and Persian translation) covering countable/uncountable nouns, *much/many*, *a lot of*, *How much/How many*, partitives (*a bag of*, *two slices of*…) and *some/any*; every card is followed by **2 mini-tests** with instant correction and a “why?” explanation, and the unit ends with a **10-question test** that scores the student and offers retry/review.
- **↩️ Back to the path** — a button under the mode cards returns to the lesson path.
- **🗂️ Flashcards** — one shared 3D-flip review deck for all saved words (reachable from the header and the homepage).

## Audio / TTS

Uses the browser's native `window.speechSynthesis` API. The global helper:

```js
speak(text, repeat = 2, rate = 0.65)
```

Every word, phrase and sentence automatically plays **twice at 0.65× speed**, with 🔊 icons next to every English word, paragraph and sentence.

## Run it

Just open `index.html` in any modern browser (Chrome/Edge recommended for TTS voices) — no build step or server required.

## Adding more lessons / chunks

`LESSONS` holds the three lessons (flip `ready` to true once built); `SECTIONS`, `SECTIONS_L2` and `SECTIONS_L3` hold the chunks of each lesson in book order, each with a `title`, printed `pages`, Persian description and a `ready` flag. A ready chunk carries `reading` lines (each with `text` and a Persian `fa` translation), `easySequence` steps (`word`, `choice`, `build`) and `listeningData` items. A merged `DICT` object serves tooltips across the whole book.
