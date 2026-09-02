# How Greek Are You? 🇬🇷

A tiny quiz game for the Greek booth at our culture night — Halkidiki, October 2026.

Three questions, drawn from a pool of 23. Get all three right and you get a secret
word to say at the booth to claim a small prize.

**Play it:** open `index.html` in any browser. No install, no internet needed.

---

## How it works

- 3 questions per player, and the answer options are shuffled too
- **No repeats:** the pool works like a deck of cards. Each player is dealt 3 off the
  top, and those questions are out of circulation until the whole deck has been used.
  Two people in a row never share a question. This survives a page refresh.
- Instant feedback after each answer, with a short fun fact
- **3/3** → win screen showing the secret word (currently **FILOXENIA**)
- **0–2/3** → sent back to the booth for a hint and another go
- "Next player" resets it for the next person

## Running it at the booth

Open `index.html` on a tablet or laptop in full screen (`F11`, or Safari's full
screen on iPad) and hand it over. Everything runs locally — no wifi required.

## Publishing it so people can play on their phones

All through github.com, no software needed:

1. Create a new repository called `greek-quiz` — set it to **Public**
   (GitHub Pages needs public on a free account)
2. On the empty repo page, click **uploading an existing file**
3. Drag in `index.html` and `README.md` → green **Commit changes**
4. Repo → **Settings** → **Pages** → Source: **Deploy from a branch**,
   branch `main`, folder `/ (root)` → **Save**
5. A minute later it's live at `https://<your-username>.github.io/greek-quiz/`.
   Make a QR code for that link and print it for the booth.

`index.html` must sit at the top level of the repo, not in a subfolder.

**To update it later:** repo → **Add file → Upload files** → drag in the new
`index.html` → **Commit changes**. It replaces the old one.

## Customising

Everything lives at the bottom of `index.html`, in the `<script>` block.

**The secret word** — two lines near the top of the script:

```js
const WIN_CODE = "FILOXENIA";
const WIN_CODE_NOTE = "φιλοξενία — literally 'love of strangers'. ...";
```

**The questions** — the `POOL` array. Each entry looks like:

```js
{ q:"The question text?",
  o:["Option A","Option B","Option C"],
  a:0,                              // index of the CORRECT option, starting at 0
  f:"The fun fact shown after answering." },
```

Add or delete as many as you like — the deck adapts automatically.

**Questions per player** — change `ROUND_SIZE`. The progress dots and the win
condition both follow it.

## What's in the pool

Mythology, food, geography, language and history, plus a few local ones: Halkidiki's
three peninsulas, Aristotle's birthplace at Stagira, and where Thessaloniki got its
name.
