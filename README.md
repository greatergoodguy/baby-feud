# 👶 Baby Feud!

A baby-shower **Family Feud** game that runs in the browser. Show the clean board on the TV,
and quietly run the whole thing from your phone. Built as **one self-contained `index.html`** —
no install, no build, works offline.

## How to play (day-of)

1. **Put the board on the TV.** Connect your laptop to the TV (HDMI or AirPlay from the laptop)
   and open the game. Press **F** for fullscreen.
2. **Pair your phone (optional but nice).** The board shows a **QR code** — scan it with your
   phone camera to open the private **host remote**. Your phone shows the answers and the
   reveal / strike / award buttons; the TV only shows what you reveal. *(Phone + laptop need to
   be on WiFi for this.)*
3. **Or run it from the laptop.** No phone / no WiFi? You can control everything with the mouse
   or keyboard (see shortcuts below). Keep the answer sheet handy at **`#key`** (see below).
4. Set team names, pick a question, and play. **First team to 300 wins.**

## Scoring (real Family Feud rules)

- Reveal answers → their points go into the **round pot**.
- Award the pot to the team that wins the round: they get **pot × the round multiplier**.
- Multiplier ramps up: **Round 1 = ×1, Round 2 = ×2, Round 3 and on = ×3**.
- **First team to 300 points wins.**

## The three views (all the same file)

| Open this URL | You get |
|---|---|
| `index.html` | **Board** — the clean TV view (this is the game) |
| `index.html#key` | **Answer key** — a read-only cheat sheet you can open on your phone or **print** |
| *(scan the QR)* | **Host remote** — the private phone controller |

## Keyboard shortcuts (on the board / laptop)

- **1–8** reveal that answer
- **X** add a strike · **Z** reset strikes
- **R** reveal all remaining
- **[** award pot ▸ Team A · **]** award pot ▸ Team B
- **M** back to the question menu · **F** fullscreen · **H** help

## Editing the answers

All questions and answers live in one place: the **`ROUNDS`** array near the top of the
`<script>` in [`index.html`](index.html). Each entry is `{ q: "question", a: [["Answer", points], ...] }`.
Change any wording or points and save — that's it.

The answers were tallied from **~620 baby-shower survey responses** (`baby-feud-responses.csv`),
merging synonyms, dropping one-off answers, and scaling each board to a 100-point survey.

## Deploying to the web (GitHub Pages)

```bash
# from this folder, after creating a repo:
git add -A && git commit -m "Baby Feud"
git push -u origin main
# then on github.com: Settings → Pages → Source: deploy from branch → main / (root)
```

Your game will be live at `https://<your-username>.github.io/<repo-name>/`.
Because it's a single static file, it also works by just double-clicking `index.html`.
