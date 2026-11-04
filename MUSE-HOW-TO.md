# How Muse updates Janet's Mind Map habits

**File to edit:** `mind-map-data/habit-log.json` (repo `janetjohnson527-source/janet.github.io-habit-tracker`, branch `main`).
Do not edit `mind-map.html` to log habits.

## Format

```json
{
  "log": {
    "2026-11-03": { "bank": true, "collagen": true, "clean": true, "nopick": true },
    "2026-11-04": { "water": true, "zoloft": true, "draw": false }
  }
}
```

- One key per date, `YYYY-MM-DD`.
- Inside each date: habit id → `true` (done) or `false` (not done).
- Only list habits you are changing. Leave everything else out. Never delete other dates.
- The exact habit name also works as the key (e.g. `"Collagen": true`), but ids are preferred.

## Habit ids

| id | habit |
|---|---|
| water | Daily water goal |
| vit | Vitamins |
| stretch | Stretching |
| shower | Showering |
| nospend | No spending money |
| nopick | No picking at skin |
| floss | Flossing |
| mouth | Mouthwash |
| teeth | Brushing teeth twice |
| clean | Cleaning something |
| draw | Drawing |
| zoloft | Zoloft |
| bank | Checking bank balance via Money Pals |
| lymph | Lymphatic drainage |
| collagen | Collagen |
| posture | Posture exercises |
| strength | Strength training (weekly, 3x) |
| walk | Walking pad (weekly, 3x) |

For weekly habits, mark `true` on each day it was done; the page counts them toward the 3x target.

Janet can rename or remove habits on the page. Renaming keeps the same id, so always log by **id** (names can change). A habit she removed is ignored if it appears in this file.

## How the page combines Muse + Janet's own taps

One rule, per habit per date: **whichever changed most recently wins.**

- When Muse sets or changes a value in this file, that shows on the page.
- When Janet taps a habit on the page after that, her tap shows (it's saved on her Mac and remembered against the value Muse had set).
- If Muse later changes that same habit/date to a different value, Muse's newer change wins again.

Pushing the same value again does not override Janet's later tap — to undo her tap, set the value Muse means (`true` or `false`) explicitly and make sure it differs from what she tapped.

## Timing

After a push, GitHub Pages takes about 1–2 minutes to publish. The page re-checks the file every time it's opened or brought back into focus.

## Limitation (by design, no paid backend)

The page cannot write back to this file. Janet's own taps are stored only in her browser on that device. Muse will not see her on-page taps in this file.
