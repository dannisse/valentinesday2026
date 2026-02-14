# Be My Valentine 💘 (Evasive “EW NO” Button + Meme Storm)

A tiny Valentine prank site built with **HTML/CSS/JavaScript** where the **“ew no (╥﹏╥)o”** button is *alive* and dodges your cursor.  
If someone manages to click **EW NO**, they get sent to a separate page that can play audio and unleash a ridiculous storm of spinning memes.

---

## Features

### ✅ Main page (`index.html`)
- Cute Valentine prompt
- **YES** button redirects to `thankyou.html`
- **EW NO** button:
  - dodges the cursor (proximity + hover)
  - avoids getting “stuck” in corners (so it stays annoying)
  - redirects to the NO page **only if you successfully land a click**

### ✅ NO page (`no.html`)
- Plays an audio clip (user interaction friendly)
- Shows a bunch of spinning images/memes (configurable)
- You can add as many meme images as you want

---

## Project structure

This repo contains the site inside a subfolder (example name):

```
valentinesDay2026/
  ├─ index.html
  ├─ no.html
  ├─ thankyou.html        (optional)
  ├─ please.png
  ├─ jumpscare.mp3        (or any audio file you want)
  ├─ memes/
  │   ├─ meme1.png
  │   ├─ meme2.png
  │   └─ ...
  └─ css/
      ├─ valentine.css
      └─ no.css           (if you made a separate css file for the no page)
```

> Tip: GitHub Pages is **case-sensitive**, so folder/file names must match exactly.

---

## Run locally

### Option A: VS Code Live Server (recommended)
1. Open the project folder in VS Code
2. Right-click `valentinesDay2026/index.html`
3. Click **Open with Live Server**

### Option B: Just open the file
Double-click `valentinesDay2026/index.html`  
(Works, but audio can be inconsistent in some browsers.)

### Option C: Python mini-server
From the repo folder:

```bash
python -m http.server 8000
```

Then open:
- `http://localhost:8000/valentinesDay2026/`

---

## Deploy as a shareable link (GitHub Pages)

### 1) Enable GitHub Pages
Repo → **Settings** → **Pages**

Under **Build and deployment**:
- Source: **Deploy from a branch**
- Branch: `main`
- Folder: `/(root)`

Save.

### 2) Share the correct URL

Because the site files are inside the `valentinesDay2026/` folder, your live homepage will be:

```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/valentinesDay2026/
```

The NO page will be:

```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/valentinesDay2026/no.html
```

> If you move the site files to the repo root later, your URL becomes:
> `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

---

## Customization

### Change the text inside the HTML files
Edit:
- `valentinesDay2026/index.html`
- `valentinesDay2026/no.html`

### Make the NO button harder/easier to click
In your JS (inside `index.html`), these control difficulty:

- `dangerRadius` (higher = runs away sooner = harder)
- `step` (higher = jumps farther = harder)
- `minDist` (higher = refuses to stay near cursor = harder)
- `edgeBuffer` (higher = avoids corners more = fewer “free clicks”)
- `avoidPad` (higher = stays away from YES more)

Example “hard but doable”:
- `dangerRadius ~ 140`
- `step ~ 200`
- `minDist ~ 130`
- `edgeBuffer ~ 35`

### Add more memes
1. Put images into:
   - `valentinesDay2026/memes/`
2. Update the `memeFiles` array in `no.html` to include your filenames.

### Add/change audio
1. Put your audio file in the folder (example):
   - `valentinesDay2026/jumpscare.mp3`
2. Update the `<audio src="...">` path in `no.html`

> Note: Most browsers block autoplay audio unless the user interacts.  
> This project is designed to play audio after a click/tap to avoid that.

---

## Troubleshooting

### “It opens my README instead of the site”
That’s the **repo link** (`github.com/...`), not the GitHub Pages link.

Use the **Pages** URL:
`https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/valentinesDay2026/`

### “404 Not Found”
Common causes:
- GitHub Pages hasn’t finished deploying (wait 1–2 minutes)
- Wrong folder name in the URL (case-sensitive!)
- `index.html` isn’t inside the folder you’re visiting

### Images/CSS/audio not loading on GitHub Pages
- Check paths are **relative**, not `C:\...`
- Check capitalization matches exactly (GitHub Pages is case-sensitive)

---

## License
MIT
