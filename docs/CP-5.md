# CP-5 — Individual Title Pages (Level 3)

## For Claude Code
You have freedom in implementation details.
Follow the design decisions and content exactly as specified.
Do not introduce new colors, fonts, or layout patterns not listed here.
Prefer clean, readable, minimal code over clever solutions.
If you see a better semantic HTML approach than what is sketched here, use it.

---

## Goal
Build the individual title page template — the deepest level of the Readings section.
This is where a book, paper, course, or other reading source gets its own page.

Each title page has:
- A title heading
- An About block (description, author/source, reference links)
- A reads list — each entry is one Notion URL (one read/note session)
  listed latest on top, like connected threads showing reading progress

Build **one sample page per subfolder** as a template.
Saransh will copy and fill in real content for each new title he adds.

Sample pages to build:
- `readings/books/sample-book.html`
- `readings/papers/sample-paper.html`
- `readings/lectures/sample-course.html`
- `readings/other/sample-other.html`

---

## 3-Level Structure (for context)

```
readings.html                              ← hub (CP-3)
    ↓
readings/books.html                        ← category list (CP-4)
    ↓
readings/books/inference-engineering.html  ← THIS CP (title page)
    ↓
Notion page (opens in new tab)             ← end destination
```

---

## DAILY WORKFLOW — How Saransh Adds a New Read to an Existing Title

When Saransh finishes a reading session and has a new Notion note ready:

1. He opens the relevant title page
   (e.g. `readings/books/inference-engineering.html`).
2. He finds the edit comment block inside the reads list.
3. He copies the sample `<li>` line.
4. He pastes it at the TOP of the list (latest read always on top).
5. He updates the title text and the Notion URL.
6. He saves and pushes.

One line. That is the entire workflow for adding a new read.

---

## WORKFLOW — How Saransh Adds a Brand New Title

When Saransh starts something completely new (new book, new paper, new course):

1. He copies the relevant sample file
   (e.g. copy `sample-book.html` → `inference-engineering.html`).
2. He updates the title, about section, and clears the sample entry from the reads list.
3. He adds the new file to the category page (`books.html`) — one `<li>` line (CP-4 workflow).
4. He saves and pushes.

---

## Page Template

### Navbar
Use the shared navbar from CP-1.
Active class goes on **Readings**.

### Stylesheet path
Files are two levels deep inside `readings/books/` etc. Use `../../style.css`.

### Back link
Just below the navbar, add a simple back link:

```html
<a href="../books.html" class="back-link">← Books</a>
```

Add this CSS to `style.css`:
```css
/* ---- Back Link ---- */
.back-link {
  display: inline-block;
  font-size: 0.9rem;
  color: #6b7280;
  margin-bottom: 1.5rem;
}

.back-link:hover {
  color: #2563eb;
  text-decoration: none;
}
```

The back link text and href must match the parent section:
- Books pages → `← Books` linking to `../books.html`
- Papers pages → `← Research Papers` linking to `../research-papers.html`
- Lectures pages → `← Lectures` linking to `../lectures.html`
- Other pages → `← Other Readings` linking to `../other-readings.html`

---

### Page Structure

```
← Back link
Title (h1)
────────────────────────────────
About block
────────────────────────────────
Reads (h2)
Entry list (Notion URLs, latest on top)
────────────────────────────────
Footer
```

---

### About Block

```html
<!-- ===== ABOUT =====
     Update title, description, author/source, and links for this entry.
     ==================== -->
<section class="about-block">
  <h1>Title of Book / Paper / Course</h1>
  <hr>
  <p class="about-desc">Short description about this book, paper, or course.</p>
  <p class="muted">Author / Source · <a href="#">Reference Link</a></p>
</section>
```

Add this CSS to `style.css`:
```css
/* ---- About Block (title pages) ---- */
.about-block {
  margin-bottom: 2rem;
}

.about-desc {
  margin-top: 0.8rem;
  margin-bottom: 0.4rem;
}
```

---

### Reads List

This is the core of the page — the list of reading sessions/notes, each linking to a Notion page.
Think of them as connected threads — each entry is one session of reading, shown latest on top.

```html
<h2>Reads</h2>

<!-- ===== READS =====
     To ADD a new read    : copy the sample <li> and paste it at the TOP (latest first).
     To REMOVE a read     : delete the entire <li>...</li> line.
     To EDIT a read       : update the title text and the Notion URL in href.
     Notion URL format    : paste your published Notion page URL directly as the href.
     target="_blank"      : always keep this — opens Notion in a new tab.
     ==================== -->
<ul class="entry-list">

  <!-- SAMPLE — replace title and href with your real Notion page -->
  <li><a href="https://notion.so/your-page-url-here" target="_blank">Title of Read / Note</a></li>

</ul>
```

---

## Sample Pages to Build

Build one sample page per subfolder. All four follow the same template above.
Use this placeholder content — Saransh will replace it when he creates real pages.

### readings/books/sample-book.html
```
Back link   : ← Books  →  ../books.html
Title       : Title of Book
Description : Short description about this book.
Author      : Author Name
Ref link    : #
Sample read : Title of Read
Notion URL  : https://notion.so/your-page-url-here
```

### readings/papers/sample-paper.html
```
Back link   : ← Research Papers  →  ../research-papers.html
Title       : Title of Paper
Description : Short description about this paper.
Author      : Author Name · Year
Ref link    : #
Sample read : Title of Read
Notion URL  : https://notion.so/your-page-url-here
```

### readings/lectures/sample-course.html
```
Back link   : ← Lectures  →  ../lectures.html
Title       : Title of Course / Lecture Series
Description : Short description about this course.
Source      : Institution / Instructor
Ref link    : #
Sample read : Lecture 1 — Title
Notion URL  : https://notion.so/your-page-url-here
```

### readings/other/sample-other.html
```
Back link   : ← Other Readings  →  ../other-readings.html
Title       : Title of Source / Topic
Description : Short description about this reading.
Source      : Author / Website
Ref link    : #
Sample read : Title of Read
Notion URL  : https://notion.so/your-page-url-here
```

---

## What NOT to do
- Do not embed Notion content in an iframe on these pages — links open in a new tab only
- Do not add dates to reads list entries — title link only
- Do not add JS — plain HTML list only
- Do not add images or diagrams — content only, clean and minimal

---

## CP-5 Checkpoint Verification

- [ ] All four sample pages exist in their correct subfolders
- [ ] All four use `../../style.css`
- [ ] Each page has a working back link to its parent category page
- [ ] Each page has the About block with title, description, and reference
- [ ] Each page has the Reads section with edit comment block
- [ ] Each page has exactly one sample `<li>` entry with placeholder Notion URL
- [ ] Sample Notion links open in a new tab (`target="_blank"`)
- [ ] Navbar "Readings" has active class
- [ ] Footer renders correctly
- [ ] Back link navigates correctly to parent category page
- [ ] Push to GitHub and confirm sample pages load at:
      - `https://SARPAT.github.io/readings/books/sample-book.html`
      - `https://SARPAT.github.io/readings/papers/sample-paper.html`
      - `https://SARPAT.github.io/readings/lectures/sample-course.html`
      - `https://SARPAT.github.io/readings/other/sample-other.html`
