# HOW TO ADD CONTENT

This is your personal reference for updating the site.
Every task below takes under 5 minutes.
No build step. No framework. Just edit HTML and push.

---

## QUICK REFERENCE

| I want to...                        | File to open                                      |
|-------------------------------------|---------------------------------------------------|
| Add a new blog post                 | drop file in `blogs/` + edit `blogs.html`         |
| Add a new book                      | `readings/books.html` + create new file in `readings/books/` |
| Add a new read to an existing book  | `readings/books/your-book-file.html`              |
| Add a new paper                     | `readings/research-papers.html` + create new file in `readings/papers/` |
| Add a new read to an existing paper | `readings/papers/your-paper-file.html`            |
| Add a new course/lecture source     | `readings/lectures.html` + create new file in `readings/lectures/` |
| Add a new lecture note              | `readings/lectures/your-course-file.html`         |
| Add a new other reading             | `readings/other-readings.html` + create new file in `readings/other/` |
| Add a new read to other readings    | `readings/other/your-source-file.html`            |
| Add a new project                   | `index.html` → find PROJECTS comment block        |
| Update my intro/bio                 | `index.html` → find hero section                  |
| Update my CV link                   | `index.html` → find SITE CONFIG comment block     |
| Update my email/Twitter/GitHub      | `index.html` → find SITE CONFIG comment block     |

---

## 1. ADD A NEW BLOG POST

Blog posts are drafted in **Claude design**, exported as a single HTML file, and
served directly from this repo. No Notion link, no build step — the exported file
*is* the published post.

### Step A — Draft and export

Write the post in Claude design, then click **Export HTML**. Which option you
want depends on whether the post has figures:

| Export option | Use it when | What you get |
|---|---|---|
| **Project archive** | the post has figures/diagrams (the usual case) | a zip containing `blog/index.html`, `blog/styles/`, `blog/assets/` |
| **Standalone HTML** | plain text post, no figures | one self-contained `.html` file |

Both work. The archive keeps figures as separate SVG files, which is *better*
for this site — they stay small, cacheable, and editable. Standalone inlines
everything as base64, which bloats the file fast once images are involved.

### Step B — Put the files in place

**If you exported a Project archive** (folder-per-post — the CacheBlend layout):

1. Unzip it. Everything you need is inside the `blog/` folder.
2. Create `blogs/your-post-slug/` (lowercase, hyphens — see FILE NAMING RULES).
3. Copy **only** these three things into it:
   ```
   blog/index.html    →  blogs/your-post-slug/index.html
   blog/styles/       →  blogs/your-post-slug/styles/
   blog/assets/       →  blogs/your-post-slug/assets/
   ```
   The relative paths inside `index.html` already line up, so nothing needs
   rewriting.

   **Do not copy** `uploads/`, `support.js`, `.thumbnail`, `source/`, `data/`,
   or the `*.dc.html` file. `uploads/` holds your source material (research
   paper PDFs, screenshots) which must not be republished, and `*.dc.html` is
   Claude design's internal editor format — it needs `support.js` and will not
   render as a normal page.

**If you exported Standalone HTML:** rename the file to
`blogs/your-post-slug.html` and skip to Step C. Add the back-link bar from
`blogs/_paste-into-export.html` (paste it just after `<body>`), since a
standalone file has no way back to the site.

### Step C — Fix the export's placeholders

Exports ship with dummy URLs. In `index.html`, search for and replace:

- `href="#"` on the `← Back to blog` link → `href="/blogs.html"`
- every `https://example.com/blog/...` in the `<head>` (canonical, `og:url`,
  `og:image`, `twitter:image`) → the real URL,
  e.g. `https://sarpat.github.io/blogs/your-post-slug/`

Leaving `example.com` in place breaks link previews when the post is shared and
points search engines at a domain that is not yours.

### Step D — Publish

1. Open `blogs.html` and find this comment:
   ```
   <!-- ===== COPY THIS BLOCK FOR A NEW POST =====
   ```
2. Copy the block inside it, paste it at the TOP of the `<ul>` (latest first),
   and uncomment it:
   ```html
   <li>
     <a href="./blogs/cacheblend/">CacheBlend: reusing KV caches for RAG without losing cross-attention</a>
     <div class="entry-meta">14 Aug 2026 · 16 min read</div>
     <p class="entry-desc">One-line summary of what the post covers.</p>
   </li>
   ```
   Folder-per-post links end in a `/`; single-file posts end in `.html`.
3. Use the post's own `<h1>` as the link text and its subtitle as the
   description — `blog/data/metadata.json` in the zip has the title, subtitle,
   date, and reading time already worked out.
4. The `entry-meta` and `entry-desc` lines are optional — delete either if you
   do not want it.
5. Save → push to GitHub.

### Linking an external post instead

Same `<li>` block, but point the href at the full URL and add `target="_blank"`:

```html
<li>
  <a href="https://likeable-mars-1d6.notion.site/your-page" target="_blank">Title</a>
  <div class="entry-meta">21 Apr 2026</div>
</li>
```

---

## 2. ADD A NEW READ TO AN EXISTING BOOK

**File:** `readings/books/your-book-file.html`

1. Open the book's HTML file (e.g. `readings/books/inference-engineering.html`)
2. Find this comment:
   ```
   <!-- ===== READS =====
   ```
3. Copy this line:
   ```html
   <li><a href="https://notion.so/your-page-url-here" target="_blank">Title of Read / Note</a></li>
   ```
4. Paste it at the TOP of the `<ul>` list
5. Replace the title text and Notion URL
6. Save → push to GitHub

---

## 3. ADD A BRAND NEW BOOK

Two steps — create the book's page, then add it to the books list.

**Step A — Create the book page:**
1. Go to `readings/books/`
2. Copy `sample-book.html` → rename it (e.g. `inference-engineering.html`)
   Use lowercase, hyphens instead of spaces, no special characters.
3. Open the new file
4. Update:
   - The `<title>` tag in `<head>`
   - The `← Books` back link (keep it as is, it already points to `../books.html`)
   - The `<h1>` title
   - The About description and author/reference link
   - Delete the sample `<li>` entry — start with an empty `<ul>`
5. Save

**Step B — Add to the books list:**
1. Open `readings/books.html`
2. Find this comment:
   ```
   <!-- ===== TITLES =====
   ```
3. Copy this line:
   ```html
   <li><a href="./books/sample-book.html">Title of Book</a></li>
   ```
4. Paste it at the TOP of the `<ul>` list
5. Update the title text and href to point to your new file
   (e.g. `./books/inference-engineering.html`)
6. Save → push to GitHub

---

## 4. ADD A NEW READ TO AN EXISTING PAPER

**File:** `readings/papers/your-paper-file.html`

Same as adding a read to a book (Section 2 above).
Open the paper's HTML file → find READS comment → copy `<li>` → paste at top → update → push.

---

## 5. ADD A BRAND NEW PAPER

Same as adding a new book (Section 3 above).
- Copy `readings/papers/sample-paper.html` → rename
- Update title, description, authors, reference link
- Add to `readings/research-papers.html` list

---

## 6. ADD A NEW LECTURE NOTE TO AN EXISTING COURSE

**File:** `readings/lectures/your-course-file.html`

Same as adding a read to a book (Section 2 above).
Open the course's HTML file → find READS comment → copy `<li>` → paste at top → update → push.

---

## 7. ADD A BRAND NEW COURSE / LECTURE SOURCE

Same as adding a new book (Section 3 above).
- Copy `readings/lectures/sample-course.html` → rename
- Update title, description, source/instructor, reference link
- Add to `readings/lectures.html` list

---

## 8. ADD A NEW OTHER READING

Same pattern as above.
- Copy `readings/other/sample-other.html` → rename
- Update title, description, source, reference link
- Add to `readings/other-readings.html` list

---

## 9. ADD A NEW PROJECT

**File:** `index.html`

1. Open `index.html`
2. Find this comment:
   ```
   <!-- ===== PROJECTS =====
   ```
3. Copy this block:
   ```html
   <li class="project-entry">
     <a href="GITHUB_LINK" target="_blank" class="project-title">Title of Project</a>
     <p class="project-desc">Short description goes here.</p>
     <div class="project-tags">
       <span class="tag">Tag1</span>
       <span class="tag">Tag2</span>
     </div>
   </li>
   ```
4. Paste it at the TOP of the `<ul>` list
5. Update title, GitHub link, description, and tags
6. Save → push to GitHub

---

## 10. REMOVE ANY ENTRY

Find the `<li>...</li>` block for that entry and delete it entirely.
Save → push to GitHub.

---

## 11. UPDATE PERSONAL DETAILS (email, CV, Twitter, GitHub)

**File:** `index.html`

1. Open `index.html`
2. Find the SITE CONFIG comment block at the top of `<body>`:
   ```
   <!-- ============ SITE CONFIG ============
   ```
3. Update the value in the comment
4. Search the file for the old value and replace it with the new one
5. Save → push to GitHub

---

## 12. PUSH TO GITHUB (reminder)

After any edit, run these commands in your terminal from the project folder:

```bash
git add .
git commit -m "add: brief description of what you added"
git push
```

Site updates go live at `https://SARPAT.github.io` within ~60 seconds.

---

## FILE NAMING RULES

When creating new HTML files, always follow these rules:
- Lowercase only: `inference-engineering.html` not `Inference-Engineering.html`
- Hyphens instead of spaces: `attention-is-all-you-need.html`
- No special characters: no brackets, colons, slashes
- Keep it short but readable

---

## FOLDER STRUCTURE REMINDER

```
SARPAT.github.io/
├── index.html              ← Home page
├── readings.html           ← Readings hub
├── blogs.html              ← Blogs list
├── style.css               ← Shared styles (do not edit unless you know what you are doing)
├── HOW-TO-ADD-CONTENT.md  ← This file
├── docs/                   ← CP markdown files (for reference only)
├── blogs/                  ← Published posts (from Claude design exports)
│   ├── cacheblend/               ← One folder per post (archive export)
│   │   ├── index.html
│   │   ├── styles/
│   │   └── assets/figures/
│   └── _paste-into-export.html   ← Back-link snippet, not a post
└── readings/
    ├── books.html          ← Books list
    ├── research-papers.html
    ├── lectures.html
    ├── other-readings.html
    ├── books/              ← One file per book
    ├── papers/             ← One file per paper
    ├── lectures/           ← One file per course
    └── other/              ← One file per other reading
```
