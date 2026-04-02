# CP-0 — Repo & Scaffold Setup

## Goal
Create the complete folder structure, all empty files, and a working placeholder homepage.
By the end of CP-0, the site must be **live on GitHub Pages** with a bare-bones index page.
No real content yet — just confirm the deployment pipeline works.

---

## Site Config (Single Source of Truth)
Every file that references personal details must pull from this block.
To update any detail in the future, change it here and update the corresponding hardcoded value below it.

```
<!-- ============ SITE CONFIG ============
  Name        : Saransh Patel
  Email       : saranshappy@gmail.com
  Twitter/X   : https://x.com/SARAPATEL21
  GitHub      : https://github.com/SARPAT
  CV Link     : https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview
  Photo       : photosara.jpg
  ======================================= -->
```

---

## Folder Structure to Create

```
SARPAT.github.io/                         ← repo root (local folder can be named anything)
├── index.html
├── readings.html
├── blogs.html
├── style.css
├── photosara.jpg                          ← real photo added before CP-2
├── docs/                                  ← holds all CP markdown files for reference
│   ├── CP-0.md
│   ├── CP-1.md
│   ├── CP-2.md
│   ├── CP-3.md
│   ├── CP-4.md
│   ├── CP-5.md
│   ├── CP-6.md
│   ├── CP-7.md
│   └── claude.md
└── readings/
    ├── books.html                         ← list of all books
    ├── research-papers.html               ← list of all papers
    ├── lectures.html                      ← list of all courses/sources
    ├── other-readings.html                ← list of all other readings
    ├── books/                             ← one file per book
    │   └── sample-book.html
    ├── papers/                            ← one file per paper
    │   └── sample-paper.html
    ├── lectures/                          ← one file per course or lecture source
    │   └── sample-course.html
    └── other/                             ← one file per other reading source
        └── sample-other.html
```

> Note: The `sample-*.html` files are placeholders. Real files will be added in CP-5 when
> Saransh adds his first real entries. The folders must exist now so GitHub Pages serves them correctly.

---

## Task 1 — Create All Files (Empty)

Create every file listed above. All HTML files except `index.html` should contain only this boilerplate:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Saransh Patel</title>
  <link rel="stylesheet" href="../../style.css" />
</head>
<body>
  <p>Coming soon.</p>
</body>
</html>
```

> Stylesheet path rules:
> - Root files (`readings.html`, `blogs.html`): use `./style.css`
> - Files inside `readings/`: use `../style.css`
> - Files inside `readings/books/`, `readings/papers/`, `readings/lectures/`, `readings/other/`: use `../../style.css`

---

## Task 2 — Placeholder `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Saransh Patel</title>
  <link rel="stylesheet" href="./style.css" />
</head>
<body>

<!-- ============ SITE CONFIG ============
  Name        : Saransh Patel
  Email       : saranshappy@gmail.com
  Twitter/X   : https://x.com/SARAPATEL21
  GitHub      : https://github.com/SARPAT
  CV Link     : https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview
  Photo       : photosara.jpg
  ======================================= -->

  <main>
    <h1>Saransh Patel</h1>
    <p>Site under construction. Coming soon.</p>
  </main>

</body>
</html>
```

---

## Task 3 — Minimal `style.css`

```css
/* ============ BASE RESET ============ */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Georgia, 'Times New Roman', serif;
  background-color: #fafaf8;
  color: #1a1a1a;
  line-height: 1.6;
  padding: 2rem;
}

a {
  color: #2563eb;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}
```

---

## Task 4 — GitHub Pages Setup

> IMPORTANT: The GitHub repository name must exactly match your GitHub username.
> For account SARPAT, the correct repo name is `SARPAT.github.io`.
> Using any other name (e.g. `saranshpatel.github.io`) will result in a 404.
> The local project folder name does not matter — only the remote repo name matters.

1. Create a new GitHub repository named exactly: `SARPAT.github.io`
   - Make it **public**
   - Do NOT initialize with README

2. In your terminal inside the project folder:
```bash
git init
git add .
git commit -m "CP-0: initial scaffold"
git branch -M main
git remote add origin https://github.com/SARPAT/SARPAT.github.io.git
git push -u origin main
```

3. Go to repo on GitHub → Settings → Pages → Source: **Deploy from branch**
   → Branch: `main` → Folder: `/ (root)` → Save.

4. Wait ~60 seconds, then visit: `https://SARPAT.github.io`

---

## CP-0 Checkpoint Verification

- [ ] All files and folders exist locally as listed in the structure above
- [ ] `index.html` loads in browser locally
- [ ] Site is live at `https://SARPAT.github.io`
- [ ] Placeholder text "Saransh Patel — Site under construction" is visible
- [ ] No 404 errors on GitHub Pages

---

## Notes
- `style.css` will be fully written in CP-1. Do not add more styles here.
- `photosara.jpg` is a placeholder filename. Real photo added before CP-2.
- Research and Publications sections planned but built later when content is ready.
- CV opens via Google Drive preview link — no PDF stored in the repo.
- `docs/` folder holds all CP markdown files for reference during development.
