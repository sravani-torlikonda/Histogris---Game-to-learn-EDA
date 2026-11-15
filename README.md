# Histogris

A falling-block browser game that teaches **Exploratory Data Analysis (EDA)** to someone with zero data science background. Data values fall as blocks; you sort them into histogram columns and make the same calls an analyst makes: which bin, keep or remove, drop or fill, how many bins.

**Play it:** https://YOUR-USERNAME.github.io/histogris/

A full run of 5 levels takes about 15 minutes, followed by an endless mode. It works on laptops and phones, with no install or login.

## Learning objectives

After playing, a learner should be able to:

1. **Histograms:** sort values into bins and explain that column height is frequency.
2. **Mean vs median:** explain why one extreme value drags the mean but not the median, and choose the median for skewed data.
3. **Outliers vs errors:** flag outliers with the box-plot rule (Q1 − 1.5×IQR, Q3 + 1.5×IQR) and tell a rare-but-real value from an impossible one.
4. **Missing values:** handle blanks by dropping or median-filling, and explain why filling too many creates a fake spike.
5. **Bin width:** choose a sensible number of bins, and recognise that too few hide patterns and too many add noise.
6. **Distribution shapes:** recognise bell, right-skewed, left-skewed, uniform and bimodal shapes.

## Levels

| Level | Concept | What the player does |
| --- | --- | --- |
| 1. Class Heights | Histograms | Sorts 16 heights into bins and watches the shape appear |
| 2. Pocket Money | Mean vs median | Predicts, then sees one ₹5,00,000 value drag the mean but not the median |
| 3. City Marathon | Outliers vs errors | Keeps rare-but-real times, trashes impossible ones |
| 4. Sleep Survey | Missing values | Fills blanks with the median or drops the row (max 2) |
| 5. Café Rush | Bin width | Changes bucket count (2/7/14/28) to reveal the lunch and dinner rushes |
| ∞ Shape Shifter | Distribution shapes | Endless waves; names the shape of each one |

## How to play

1. Open the link (or open `index.html` in any browser) and start **Class Heights**.
2. Take the 5-question warm-up test.
3. For each level: read the briefing, play, read the debrief, answer the 2-question check.
4. After Level 5, take the same 5-question test again to see your before/after score.

| Action | Keyboard | Phone |
| --- | --- | --- |
| Move | ← → or A D | Tap a column or swipe sideways |
| Fall faster | ↓ or S | ▼ button |
| Drop now | Space | Tap the same column again or swipe down |
| Trash (Level 3 on) | ↑ or W | Swipe up or TRASH |
| Fewer / more buckets (Level 5) | Q / E | − / + |
| Pause | P or Esc | Pause |

You have 3 hearts per level. Wrong decisions cost a heart. **Relaxed pace** (top bar) slows the blocks for beginners.

## How it works

- One self-contained `index.html`: plain JavaScript, HTML5 Canvas, Web Audio. No libraries, no server, no build step.
- Every statistic is computed live from the blocks on the board: mean, median, quartiles, IQR fences, the median fill column, re-binning, two-peak detection and the Shape Shifter answer (skewness + peak test). Nothing is hard-coded.
- Level data is simulated from realistic distributions with a seeded random generator, so each level plays the same every time.
- Progress is saved in the browser (localStorage), per player.

## Playtesting and evidence of learning

- The game records warm-up and final test scores, per-level checks, tries, time and mistakes by type.
- **Main menu → My results** shows them, and **Copy results** copies one row to paste into a spreadsheet. **New player (reset)** clears progress for the next tester.
- `playtest/histogris_playtest_form.gs` builds the 8-question Google Form and a results sheet that computes each player's gain. Paste it into script.google.com and run `createPlaytestForm`.

## Repository

```
index.html                           the game
README.md                            this file
playtest/histogris_playtest_form.gs  Google Form builder for playtests
```

## Course

Made for the Data Science course game project (Part B: game for learning data science concepts).
