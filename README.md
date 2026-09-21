# 💌 Personal Letter Website — Editing Guide

Open `index.html` in any browser. No server needed.

---

## How to personalise

All editable content is clearly marked with `<!-- ════ PERSONALISE ... ════ -->` comments inside `index.html`. Open it in any text editor (Notepad, VS Code, etc.) and search for `PERSONALISE` to jump to each spot.

### Quick-find list

| What to change | Search for in the file |
|---|---|
| Recipient name on envelope | `For you, my love` |
| Date on the letter | `September 22, 2026` |
| Greeting | `My dearest,` |
| **Main letter body** | The four `<p>` blocks below `<!-- PERSONALISE: Replace everything -->` |
| Sign-off / your name | `— Your [Name]` |
| Memory cards (titles + text) | Each `<div class="memory-card">` block |
| Timeline dates + events | Each `<div class="timeline-item">` block |
| Open-when messages | Inside each `<div class="ow-message">` block |
| Hidden secret message | Inside `<div class="hidden-reveal">` |
| Final letter | The two `<p class="final-text">` blocks |
| Your signature name | `[Your Name]` near the bottom |

---

## Adding your photos

1. Put your photos inside the `assets/` folder (e.g. `assets/photo1.jpg`)
2. In each `.polaroid` block, **replace** this entire block:
   ```html
   <div class="polaroid-img-placeholder">
     ...
   </div>
   ```
   **with:**
   ```html
   <img src="assets/photo1.jpg"
        class="polaroid-img"
        alt="A short description of the photo" />
   ```
3. Change the caption below: `<p class="polaroid-caption">your caption here</p>`

Photos should ideally be square (1:1) or close to it. JPEG or WebP work best.

---

## Folder structure

```
letter/
├── index.html      ← the whole website
├── assets/         ← put your photos here
│   ├── photo1.jpg
│   ├── photo2.jpg
│   └── ...
└── README.md       ← this file
```

---

## Fonts note

The site loads **Lora** (body) and **Caveat** (handwriting) from Google Fonts.
This requires an internet connection on first open. After that, the browser caches them.

If you want it to work fully offline:
1. Download both fonts from [Google Fonts](https://fonts.google.com)
2. Put the `.woff2` files in `assets/fonts/`
3. Replace the `<link>` tag in `<head>` with local `@font-face` CSS rules

---

## Customising colours

All colours are in the `:root {}` block at the top of the `<style>` tag:

```css
--ivory:    #F4EDD8;
--cream:    #EDE3C8;
--burgundy: #7C3030;
--rose:     #A05050;
--ink:      #2C1A0E;
```

Change any hex value to adjust the palette.

---

*Made with care.*
