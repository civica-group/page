# How to add a new article to Civica News

You only ever need to touch TWO things:

---

## Step 1 — Create the article HTML file

Copy `articles/NEW-ARTICLE-TEMPLATE.html` and rename it.
The filename becomes the URL, e.g. `my-new-article.html` → civica.com/articles/my-new-article.html

Fill in all the CHANGE comments in the file. That's it.

---

## Step 2 — Add one entry to articles/manifest.json

Open `articles/manifest.json` and add a new object to the top of the array:

```json
{
  "slug": "my-new-article",
  "title": "Your Article Title",
  "subtitle": "Optional subtitle line",
  "author": "Author Name",
  "date": "2026-06-01",
  "category": "Politics",
  "edition": "Standard",
  "hero": false,
  "image": "images/my-photo.jpg",
  "imageAlt": "Description of the image",
  "tags": ["tag one", "tag two"]
}
```

**slug** — filename without .html (must match exactly)
**date** — YYYY-MM-DD format (used for sorting — newest always appears first)
**category** — Politics, Economy, Culture, Labour, International, Science, Opinion
**edition** — Standard, Now, Review, Special, Live
**hero: true** — makes this the front page hero article (only set one at a time)
**image** — filename inside articles/images/ folder (or leave "" for no image)

The front page updates automatically. Done.

---

## Images

Put image files in `articles/images/` and reference them as `"image": "images/filename.jpg"`.
Supported formats: jpg, png, webp.
If an image is missing, it silently hides — no broken image icons.

---

## Hosting on GitHub Pages

1. Push everything to your GitHub repo
2. Go to repo Settings → Pages → Source: Deploy from branch → branch: main, folder: / (root)
3. Your site is live at https://YOUR-USERNAME.github.io/REPO-NAME/

To update: just push your new article file + manifest.json change. GitHub Pages deploys automatically.

---

## File structure

```
index.html                  ← NEVER EDIT THIS
about.html                  ← Edit once if needed
articles/
  manifest.json             ← Add one entry per new article
  article.css               ← NEVER EDIT THIS
  NEW-ARTICLE-TEMPLATE.html ← Copy this for every new article
  images/                   ← Put article images here
  your-article.html         ← Your articles go here
```
