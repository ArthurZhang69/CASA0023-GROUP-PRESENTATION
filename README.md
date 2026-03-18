# CASA0023 Group Presentation
**Remotely Sensing Cities and Environments · UCL 2026**

🌐 **Live Presentation:** `https://arthurzhang69.github.io/CASA0023-GROUP-PRESENTATION/`

---

## 📁 Repo Structure

```
CASA0023-GROUP-PRESENTATION/
│
├── index.Rmd          ← ⭐ Main presentation file (maintained by Arthur)
├── index.html         ← Generated after Knit; rendered by GitHub Pages
├── custom.css         ← Shared theme stylesheet (root-level CSS: do NOT modify unless you are Arthur ⚠;
                         sync your personal folder's CSS with the root CSS periodically)
├── .gitignore         ← Ignores large files on GitHub — never push files >100MB
├── README.md
│
├── Content From HaoYu Jiang/
├── Content From JianShu Wu/
├── Content From Li Sheng/
├── Content From ShiYao Zhang/
└── Content From ZheXiang Zhou/
```

---

## ✍️ How to Use Your Folder

### Step 1 · Confirm Your Files Are in Place

Each person's folder already contains:

```
Content From [Your Name]/
├── preview.Rmd    ✅ Already set up — contains your assigned slides
└── custom.css     ✅ Already set up — shared theme stylesheet
```

No setup needed. Jump straight to Step 2.

### Step 2 · Write Your Slides in preview.Rmd

Open `preview.Rmd` and add your slides at the end of the file using this format:

```rmd
---

## Your Slide Title

.slide-label[Slide XX · Your Name]

Content goes here...

.footnote[References]
```

Separate each slide with `---`.

### Step 3 · Preview Locally

Open `preview.Rmd` in RStudio and click **Knit**. Your browser will automatically open a preview.

The styling is identical to the final version — what you see is what you get.

### Step 4 · Store Images in Your Own Folder

```
Content From [Your Name]/
├── preview.Rmd
├── custom.css
├── fig_01_map.png       ← Images go here
└── fig_02_chart.png
```

When referencing images, use:

```r
knitr::include_graphics("Content From [Your Name]/fig_01_map.png")
```

> ⚠️ Write paths from the **repo root** — do not use `./`

### Step 5 · Push to GitHub

```bash
# Sync before starting
git pull

# After editing
git add "Content From [Your Name]/"
git commit -m "Brief description, e.g.: Add slide 3 vulnerability diagram"
git push
```

**Only add your own folder** — do not touch other people's folders or root-level files.

---

## 🔀 Final Integration (Arthur only)

Once everyone has finished their content, Arthur follows these steps to merge:

### Step 1 · Verify Each Person's preview.Rmd Knits Successfully

Open each person's `preview.Rmd` and Knit it one by one. Make sure there are no errors.

### Step 2 · Import Each Person's Content into index.Rmd in Order

### Step 3 · Knit index.Rmd to Generate the Final File

Open the root-level `index.Rmd` in RStudio and click **Knit** to generate `index.html`.

If errors occur, they are usually caused by incorrect image paths — check each `include_graphics()` call.

### Step 4 · Push — GitHub Pages Updates Automatically

```bash
git add index.html libs/
git commit -m "Final presentation build"
git push
```

The live page will update within a few minutes.

---

## ⚠️ Common Issues

| Issue | Cause | Fix |
|-------|-------|-----|
| Knit error: image not found | Path uses `./` or a relative path | Rewrite as a full path from the repo root |
| Styles not applying | `custom.css` not in the same directory | Confirm your folder contains `custom.css` |
| Push rejected | Forgot to pull first | Run `git pull` before pushing |
| Image too large to push | File exceeds 100MB | Store large files on Google Drive; only push exported chart screenshots to the repo |
| Push returns 403 / Permission denied | Local Git is cached with someone else's GitHub account | Run `git remote set-url origin https://YOUR_USERNAME@github.com/ArthurZhang69/CASA0023-GROUP-PRESENTATION.git`, then push again. When prompted for a password, enter your Personal Access Token (GitHub → Settings → Developer Settings → Personal Access Tokens → generate one with `repo` scope) |

---

*Built with [Xaringan](https://github.com/yihui/xaringan) · R · ggplot2 · All EO data via Google Earth Engine*