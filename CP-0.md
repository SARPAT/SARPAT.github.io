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
saranshpatel.github.io/
├── index.html
├── readings.html
├── blogs.html
├── style.css
├── photosara.jpg          ← placeholder for now, real photo added later
├── readings/
│   ├── books.html
│   ├── research-papers.html
│   ├── lectures.html
│   └── other-readings.html
└── CP-0.md                ← can be deleted after setup, just for reference
```

---

## Task 1 — Create All Files (Empty)

Create every file listed above. All HTML files except `index.html` should contain only this boilerplate for now:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Saransh Patel</title>
  <link rel="stylesheet" href="../style.css" />
</head>
<body>
  <p>Coming soon.</p>
</body>
</html>
```

> Note: Files inside `readings/` folder must use `../style.css` for the stylesheet path.
> Files at root level (`readings.html`, `blogs.html`) must use `./style.css`.

---

## Task 2 — Placeholder `index.html`

Create `index.html` with the SITE CONFIG comment block at the top, then this minimal placeholder body:

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

Create `style.css` with only a reset and base font for now. Full styling comes in CP-1.

```css
/* ============ BASE RESET ============ */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Georgia, 'Times New Roman', serif;
  background-color: #ffffff;
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

## Task 4 — GitHub Pages Setup Instructions

Do the following steps manually (Claude Code cannot do this for you):

1. Create a new GitHub repository named exactly: `saranshpatel.github.io`
   - Make it **public**
   - Do NOT initialize with README (you will push from local)

2. In your terminal, inside the project folder:
```bash
git init
git add .
git commit -m "CP-0: initial scaffold"
git branch -M main
git remote add origin https://github.com/SARPAT/saranshpatel.github.io.git
git push -u origin main
```

3. Go to the repo on GitHub → Settings → Pages → Source: **Deploy from branch** → Branch: `main` → Folder: `/ (root)` → Save.

4. Wait ~60 seconds, then visit: `https://saranshpatel.github.io`
   You should see "Saransh Patel — Site under construction."

---

## CP-0 Checkpoint Verification

Before moving to CP-1, confirm all of these:

- [ ] All files and folders exist locally as listed in the structure above
- [ ] `index.html` loads in browser locally (just open the file)
- [ ] Site is live at `https://saranshpatel.github.io`
- [ ] The placeholder text "Saransh Patel — Site under construction" is visible
- [ ] No 404 errors on GitHub Pages

---

## Notes for Future CPs
- `style.css` will be fully written in CP-1. Do not add more styles here.
- `photosara.jpg` is a placeholder filename. The real photo will be added before CP-2.
- Research and Publications sections are planned but will NOT be built until content is ready.
- CV opens via Google Drive preview link — no PDF stored in the repo.
