# SITREP // DAILY: KWGT widget build (S25 Ultra + Z Fold 7)

Feed:  https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json
App:   https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/

The feed is rebuilt daily at 1645 CT. The widget reads pre-formatted lines from `.widget.*`, so you only build one text module.

## 0. One-time on each phone
1. Open the App URL in Chrome, then ⋮ → **Add to Home screen → Install**. You now have a SITREP app icon that works offline.
2. Install **KWGT** and **KWGT Pro** from the Play Store. Pro is what lets you save a custom widget.

## 1. Place the widget
Long-press the home screen → Widgets → KWGT → pick **4×2** (S25 Ultra / Fold cover screen) or **4×3** (Fold inner screen). Tap the empty widget to open the editor.

## 2. Background
Items → **+** → **Shape** (rectangle)
- Width/height: fill the widget · Corner radius: 18
- Color: `#E60B0B0B` (black at about 90%)
- FX → Border: 2 px, `#C9A227`

## 3. Text: paste this as the formula
Items → **+** → **Text** → tap the Text field → formula editor → paste:

```
[b][c=#C9A227]SITREP // DAILY[/c][/b]   [c=#9B968A]$wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.head")$[/c]
[c=#C9A227]NEXT[/c]  $wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.next")$
[c=#C9A227]FOCUS[/c] $wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.focus")$
[c=#C9A227]PT[/c]    $wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.pt")$
[c=#C9A227]DRY[/c]   $wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.dry")$
[c=#C9A227]COMMS[/c] $wg("https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/sitrep.json", json, ".widget.comms")$
```

Text settings:
- Font: pick a condensed mono font (Roboto Mono and JetBrains Mono both work) · Size about 11–12 on the S25, 13 on the Fold inner screen
- Color: `#ECE9E1` · Lines: unlimited · Align: left
- Padding: 14 on all sides

## 4. Tap actions
Select the text → **Touch** → **+** → Action **Open Link** → `https://rpr0m3th3us6-a11y.github.io/SITREP_Daily/`

Optional deep links if you split the text into separate modules per line:
- PT line → `…/SITREP_Daily/#pt`
- DRY line → `…/SITREP_Daily/#dry`
- FOCUS line → `…/SITREP_Daily/#mission`

## 5. Save and copy to the other phone
Tap 💾 to save. To reuse it, go to the KWGT main screen → Exported → share the `.kwgt` file to the other phone, then import it there and only adjust the font size.

## Notes
- KWGT caches web data and re-fetches on its own schedule. The feed only changes once a day, so a short lag doesn't matter. To force a refresh, reopen the widget in the editor.
- If a line shows blank, check that the JSON path matches `sitrep.json`, including the leading dot.
- Ledger numbers and everything you type in the app stay on that phone (browser storage). Nothing you enter is published.
