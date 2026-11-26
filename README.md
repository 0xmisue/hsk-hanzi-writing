# HSK Hanzi Writing · 纸想见你 · Tiệm Chữ

**A few words a day: see the pinyin, write the character from memory.**

HSK Hanzi Writing is a small daily study game for learning to *write* Chinese characters, not just recognise them. Each day you get a short lesson of new HSK words. You watch the stroke order, trace it, then write the character from memory in a classic 田字格 (tian zi ge) practice square, the red grid used in Chinese school copybooks.

It is part of **纸想见你 · Tiệm Chữ**, a small brand about words, languages and books.

## Features

- **HSK 1–6 vocabulary:** 4,986 words, with pinyin and Vietnamese meanings.
- **Three-step learning for new words:**
  1. **Watch:** an animation shows the correct stroke order.
  2. **Trace:** you draw over faint strokes, in order.
  3. **Write:** you write the character from memory. After 3 misses on a stroke you get a hint.
- **Spaced repetition:** words you get right come back after 1, 2, 4, 7, 15 and 30 days. Words you miss come back tomorrow, and you retry them later in the same session.
- **Daily goal:** choose 3, 5, 8 or 10 new words per day.
- **Streaks, XP and levels**, plus a weekly calendar that stamps every finished day with a red seal.
- **Word book:** browse every word in a level, colour-coded as new, learning or known. Tap any word to replay its strokes and hear it.
- **Recognition quiz:** a quick 10-question multiple-choice round. You see the pinyin and meaning and pick the right characters.
- **Audio pronunciation**, using the browser's built-in Chinese voice.
- **English / Vietnamese interface** and automatic light / dark mode.
- **Feedback form** for learners to send ratings and comments.

## How it works

This is a static site with no build step and no server:

```
index.html          # the whole app: HTML, CSS and JavaScript
levels/
  hsk3.json … hsk6.json        # word lists for HSK 3–6 (HSK 1–2 are inside index.html)
  strokes3.json … strokes6.json  # stroke data for the characters in each level
```

Level data loads only when a learner opens that level, so the first visit stays light.

Stroke animation and stroke checking use [Hanzi Writer](https://hanziwriter.org/).

### Saving progress

- **On the open web (e.g. Vercel):** progress is saved in the browser's local storage. It stays on that device and browser, and is lost if the learner clears their browser data.
- **Inside Claude:** progress also syncs to the learner's Claude account, and the feedback form and owner inbox are enabled. These features are not available in the standalone web version.

## Run locally

Any static file server works. For example:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open `http://localhost:8000` (or the port shown).

> Opening `index.html` directly from disk (`file://`) won't load the level files, because browsers block `fetch` for local files. Use a local server instead.

## Deploy

The site is deployed on [Vercel](https://vercel.com) as a static project (Framework Preset: **Other**, no build command). Every push to `main` redeploys automatically.

## Credits

- Stroke order data and animation: [Hanzi Writer](https://hanziwriter.org/) and its character data.
- Fonts: [Be Vietnam Pro](https://fonts.google.com/specimen/Be+Vietnam+Pro), [Ma Shan Zheng](https://fonts.google.com/specimen/Ma+Shan+Zheng) and [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC).

---

Made with care by **纸想见你 · Tiệm Chữ**. 加油！
