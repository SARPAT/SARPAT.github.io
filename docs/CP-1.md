# CP-1 — Shared Style & Navbar

## Goal
Write the complete `style.css` and implement the shared navbar HTML snippet.
This is the design foundation — every page inherits from this.
No page content yet. Just the design system.

---

## Design Decisions (Locked)

| Property | Value |
|----------|-------|
| Background | `#fafaf8` (Warm Paper) |
| Text | `#1a1a1a` |
| Accent / Links | `#2563eb` |
| Muted / Secondary text | `#6b7280` |
| Max content width | `720px` |
| Font | Georgia, 'Times New Roman', serif |
| Base font size | `17px` |
| Line height | `1.7` |

---

## Task 1 — Rewrite `style.css` Completely

Replace the placeholder `style.css` from CP-0 with this full stylesheet:

```css
/* ============ SITE CONFIG REFERENCE ============
   Background  : #fafaf8  (Warm Paper)
   Text        : #1a1a1a
   Links       : #2563eb
   Muted text  : #6b7280
   Max width   : 720px
   Font        : Georgia, serif
   =============================================== */

/* ---- Reset ---- */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

/* ---- Base ---- */
html {
  font-size: 17px;
}

body {
  font-family: Georgia, 'Times New Roman', serif;
  background-color: #fafaf8;
  color: #1a1a1a;
  line-height: 1.7;
  padding: 0;
  margin: 0;
}

/* ---- Layout Container ---- */
.container {
  max-width: 720px;
  margin: 0 auto;
  padding: 0 1.5rem;
}

/* ---- Typography ---- */
h1 {
  font-size: 1.9rem;
  font-weight: bold;
  letter-spacing: -0.01em;
  line-height: 1.2;
  margin-bottom: 0.2rem;
}

h2 {
  font-size: 1.2rem;
  font-weight: bold;
  margin-top: 2.5rem;
  margin-bottom: 0.8rem;
  color: #1a1a1a;
}

h3 {
  font-size: 1rem;
  font-weight: bold;
  margin-top: 1.5rem;
  margin-bottom: 0.4rem;
}

p {
  margin-bottom: 1rem;
  color: #1a1a1a;
}

/* ---- Links ---- */
a {
  color: #2563eb;
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

/* ---- Muted / Secondary Text ---- */
.muted {
  color: #6b7280;
  font-size: 0.9rem;
}

/* ---- Horizontal Rule / Section Divider ---- */
hr {
  border: none;
  border-top: 1px solid #e5e5e0;
  margin: 2rem 0;
}

/* ---- Navbar ---- */
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem 0;
  margin-bottom: 2rem;
}

nav .nav-name {
  font-size: 1rem;
  font-weight: bold;
  color: #1a1a1a;
  text-decoration: none;
}

nav .nav-name:hover {
  text-decoration: none;
  color: #2563eb;
}

nav .nav-links {
  display: flex;
  gap: 1.5rem;
  list-style: none;
}

nav .nav-links a {
  font-size: 0.95rem;
  color: #1a1a1a;
  text-decoration: none;
}

nav .nav-links a:hover {
  color: #2563eb;
  text-decoration: none;
}

nav .nav-links a.active {
  color: #2563eb;
}

/* ---- Footer ---- */
footer {
  margin-top: 4rem;
  padding: 2rem 0;
  border-top: 1px solid #e5e5e0;
  font-size: 0.9rem;
  color: #6b7280;
}

footer .footer-links {
  display: flex;
  gap: 1.2rem;
  flex-wrap: wrap;
  margin-top: 0.5rem;
}

footer .footer-links a {
  color: #6b7280;
  font-size: 0.9rem;
}

footer .footer-links a:hover {
  color: #2563eb;
}

/* ---- Section Labels (for Readings, Projects etc.) ---- */
.section-label {
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #6b7280;
  margin-bottom: 0.5rem;
}

/* ---- List of entries (readings, blogs, projects) ---- */
.entry-list {
  list-style: none;
  margin: 0;
  padding: 0;
}

.entry-list li {
  padding: 0.5rem 0;
  border-bottom: 1px solid #e5e5e0;
}

.entry-list li:last-child {
  border-bottom: none;
}

.entry-list a {
  font-size: 1rem;
  color: #2563eb;
}

/* ---- Tags / Badges (for projects) ---- */
.tag {
  display: inline-block;
  font-size: 0.75rem;
  background-color: #f0f0ec;
  color: #6b7280;
  padding: 0.15rem 0.5rem;
  border-radius: 3px;
  margin-right: 0.3rem;
  font-family: 'Courier New', monospace;
}

/* ---- Responsive ---- */
@media (max-width: 600px) {
  html {
    font-size: 15px;
  }

  nav {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.8rem;
  }

  nav .nav-links {
    gap: 1rem;
  }
}
```

---

## Task 2 — Shared Navbar HTML Snippet

This navbar snippet must be copy-pasted into **every HTML file** in the project.
It is the same across all pages. Only the `active` class changes per page.

```html
<!-- NAVBAR — paste into every page, change active class per page -->
<nav>
  <div class="container" style="display:flex; justify-content:space-between; align-items:center; width:100%;">
    <a href="/" class="nav-name">Saransh Patel</a>
    <ul class="nav-links">
      <li><a href="/" class="active">Home</a></li>
      <li><a href="/readings.html">Readings</a></li>
      <li><a href="/blogs.html">Blogs</a></li>
      <li><a href="https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview" target="_blank">CV</a></li>
    </ul>
  </div>
</nav>
```

> Note on `active` class: On `readings.html`, add `class="active"` to the Readings link and remove it from Home. Same pattern for Blogs. CV never gets the active class since it opens externally.

---

## Task 3 — Update All Placeholder Files with Navbar

Open every HTML file created in CP-0 and add:
1. The navbar snippet inside `<body>`, before any content
2. Wrap all page content in `<div class="container">...</div>`
3. Update stylesheet path if needed (`./style.css` for root files, `../style.css` for files inside `readings/`)

Example structure every page should follow:

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

  <!-- NAVBAR -->
  <nav>
    <div class="container" style="display:flex; justify-content:space-between; align-items:center; width:100%;">
      <a href="/" class="nav-name">Saransh Patel</a>
      <ul class="nav-links">
        <li><a href="/">Home</a></li>
        <li><a href="/readings.html">Readings</a></li>
        <li><a href="/blogs.html">Blogs</a></li>
        <li><a href="https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview" target="_blank">CV</a></li>
      </ul>
    </div>
  </nav>

  <!-- PAGE CONTENT -->
  <div class="container">
    <p>Coming soon.</p>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="container">
      <p>B.Tech Computer Science · ABES Engineering College · Ghaziabad</p>
      <div class="footer-links">
        <a href="mailto:saranshappy@gmail.com">saranshappy@gmail.com</a>
        <a href="https://github.com/SARPAT" target="_blank">GitHub</a>
        <a href="https://x.com/SARAPATEL21" target="_blank">X</a>
        <a href="https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview" target="_blank">CV</a>
      </div>
    </div>
  </footer>

</body>
</html>
```

---

## CP-1 Checkpoint Verification

Before moving to CP-2, confirm all of these:

- [ ] `style.css` is fully replaced with the new stylesheet
- [ ] All pages have the navbar and footer
- [ ] Navbar links work — clicking Readings, Blogs, CV navigates correctly
- [ ] CV link opens Google Drive in a new tab
- [ ] Background color looks warm (not pure white) in browser
- [ ] Site looks correct on mobile (navbar stacks vertically on small screens)
- [ ] Push to GitHub and confirm live site still works at `https://SARPAT.github.io`

---

## Notes
- Do NOT add any page-specific content yet. That comes in CP-2 onwards.
- The footer Education line can be updated anytime by editing the single line in each HTML file.
- All colors, font sizes, and spacing are defined as CSS comments at the top of `style.css` for easy future edits.
