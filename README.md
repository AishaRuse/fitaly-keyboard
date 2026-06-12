# Fitaly Keyboard PWA

One-finger text entry using the FITALY keyboard layout (textware.com), with
sliding for capitals, accents, digits and delete. Installable as a PWA on
iPhone and iPad.

## Files
- `index.html` — the whole app (HTML + CSS + JS)
- `manifest.json` — PWA manifest
- `sw.js` — service worker (offline support)
- `icon-192.png`, `icon-512.png`, `icon-512-maskable.png`, `apple-touch-icon.png`

## Swipe typing
Draw a continuous path through a word's letters without lifting your finger
(an amber trail follows). The best match is inserted with a space; the
suggestion bar shows alternates — tap one to swap the word. Your personal
dictionary words are favoured. Short straight flicks still give capitals;
very short words (it, at, to) are quicker to tap. Swiping is available on
the letter panel only.

## Sliding reference
- Slide a **letter** in any direction = **capital**
- Slide a **punctuation key** (any direction) = the digit shown in its corner
- Slide a **digit** on the 123 panel = its punctuation counterpart
- Slide **⌫ up** = forward delete; slide **⌫ down** = delete previous word;
  hold **⌫** to auto-repeat (accelerates)
- Slide **sideways on a space bar** = cursor trackpad (move the caret);
  double-tap space = ". " ready for the next sentence
- **Auto-capitalisation** at the start of text, after . ! ? and new lines
  (tap shift to cancel; caps lock overrides)
- **Draft auto-save**: the text survives closing the app
- **Shift** is one-shot; **caps** locks; shift also gives alternate punctuation
- **Share** opens the iOS share sheet — tap **Notes** there to create a new
  note pre-filled with the text (or Messages, Mail, etc.)
- **Word suggestions**: the bar above the keyboard completes the word at the
  caret from a 20,000-word frequency dictionary, and learns the words you
  type — your own vocabulary rises to the top over time (stored on-device).
  Between words, it predicts the next word from your own writing (a personal
  bigram table). Long-press a suggestion to remove a learned word.
  Settings (… button) exports/imports the learned dictionary as a file —
  AirDrop it between iPhone and iPad to carry your vocabulary across.
- **Keyboard height**: Settings > Resize handle > Show reveals a slim drag
  bar above the suggestions on any device — drag to set the keyboard height
  (persisted), then Hide it to reclaim the space. Reset returns to automatic.
- **iPad**: anchor the keyboard Left/Full/Right in Settings for one-handed
  use.
  Smart punctuation: typing . , ! ? : ; immediately after an accepted
  suggestion pulls the punctuation back before the auto-space
- **2-finger scroll** is on by default (one finger places the cursor / selects);
  the toolbar button switches back to native one-finger scrolling

## Deploy on GitHub Pages
1. Create a new public repository, e.g. `fitaly-keyboard`
2. Upload all files in this folder to the repository root
3. Settings → Pages → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save
4. After ~1 minute the app is live at
   `https://<your-username>.github.io/fitaly-keyboard/`

## Install as a PWA
- **iPhone / iPad (Safari):** open the URL → Share button → *Add to Home
  Screen* → Add. Launch from the home screen icon; it runs full-screen and
  works offline.

## Updating
When you change `index.html`, also bump the `CACHE` version string in `sw.js`
(e.g. `fitaly-v2`) so installed devices pick up the new version.
