# HOW TO ADD CONTENT

This is your personal reference for updating the site.
Every task below takes under 5 minutes.
No build step. No framework. Just edit HTML and push.

---

## QUICK REFERENCE

| I want to...                        | File to open                                      |
|-------------------------------------|---------------------------------------------------|
| Add a new blog post                 | `blogs.html`                                      |
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

**File:** `blogs.html`

1. Open `blogs.html`
2. Find this comment:
   ```
   <!-- ===== BLOG POSTS =====
   ```
3. Copy this line:
   ```html
   <li><a href="https://notion.so/your-blog-post-url-here" target="_blank">Title of Blog Post</a></li>
   ```
4. Paste it at the TOP of the `<ul>` list (above all existing entries)
5. Replace the title text and Notion URL
6. Save → push to GitHub

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
