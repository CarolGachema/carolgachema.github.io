# Portfolio Website — Setup Guide
## Caroline Wambui Gachema

Complete step-by-step from zero to live website.

---

## STEP 1 — Install the tools (do this once)

### 1a. Make sure R and RStudio are installed
You already have these. Skip if confirmed.

### 1b. Install the Quarto CLI
This is separate from the R package — it's a command-line tool.

Go to: **https://quarto.org/docs/get-started/**
Download the installer for your OS (Linux/Windows/Mac) and run it.

Verify in your terminal / RStudio Terminal tab:
```bash
quarto --version
# should print something like: 1.4.553
```

### 1c. Install the Quarto R package (optional but useful in RStudio)
```r
install.packages("quarto")
```

---

## STEP 2 — Create your GitHub repository

1. Go to **github.com** and sign in as CarolGachema
2. Click **New repository**
3. Name it exactly: `carolinegachema.github.io`
   *(this special name tells GitHub to host it as a website)*
4. Set to **Public**
5. Tick **Add a README file**
6. Click **Create repository**

Then clone it to your computer:
```bash
git clone https://github.com/CarolGachema/carolinegachema.github.io.git
cd carolinegachema.github.io
```

---

## STEP 3 — Copy these files into your cloned folder

Your folder should look like this after copying:
```
carolinegachema.github.io/
├── _quarto.yml
├── styles.scss
├── index.qmd
├── research.qmd
├── projects.qmd
├── policy.qmd
├── cv.qmd
├── images/
│   └── profile.jpg     ← add your photo here, named exactly this
└── SETUP.md            ← you can delete this once you're set up
```

**Add your profile photo:** Put a square-ish photo of yourself in the `images/` folder, named `profile.jpg`.

---

## STEP 4 — Open in RStudio and preview

1. In RStudio: **File → Open Project** → navigate to your folder → open `carolinegachema.github.io.Rproj`
   *(or just open any .qmd file from that folder)*

2. In the RStudio Terminal tab, run:
```bash
quarto preview
```

3. Your browser will open automatically at `http://localhost:4321`
   You can edit files and the preview updates live.

---

## STEP 5 — Customise the content

Open each `.qmd` file and fill in your details where you see:
- `[YOUR PHOTO]` → replaced by adding `profile.jpg` to images/
- `[FILL IN: ...]` → replace with your actual content
- LinkedIn URL → update to your actual LinkedIn profile URL

Key things to update in `_quarto.yml`:
```yaml
site-url: "https://carolinegachema.github.io"   # ← correct already
```

Key things to update in `cv.qmd`:
- Your full education history
- All experience entries

---

## STEP 6 — Build the site

When you're happy with the preview, build it:
```bash
quarto render
```

This creates a `docs/` folder with your complete website.

---

## STEP 7 — Push to GitHub

```bash
git add .
git commit -m "Launch portfolio website"
git push origin main
```

---

## STEP 8 — Enable GitHub Pages

1. Go to your repo on GitHub: `github.com/CarolGachema/carolinegachema.github.io`
2. Click **Settings** (top menu)
3. Click **Pages** (left sidebar)
4. Under **Source**, select **Deploy from a branch**
5. Branch: `main` · Folder: `/docs`
6. Click **Save**

Wait 2–3 minutes, then go to:
**https://carolinegachema.github.io**

Your website is live. ✓

---

## STEP 9 — Every time you update

```bash
quarto render
git add .
git commit -m "Update: [what you changed]"
git push origin main
```

GitHub Pages updates automatically within 1–2 minutes.

---

## Troubleshooting

**"quarto: command not found"**
→ Restart RStudio after installing Quarto CLI, then try again in the Terminal tab.

**Website shows old content**
→ Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

**Images not showing**
→ Check file names are exact (case-sensitive). `Profile.jpg` ≠ `profile.jpg`

**Fonts not loading**
→ You need an internet connection when rendering. The fonts load from Google Fonts.

---

*Questions? caroline@gachemacarol.gmail.com*
