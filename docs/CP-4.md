# CP-4 — Reading Category Pages (Level 2)

## For Claude Code
You have freedom in implementation details.
Follow the design decisions and content exactly as specified.
Do not introduce new colors, fonts, or layout patterns not listed here.
Prefer clean, readable, minimal code over clever solutions.
If you see a better semantic HTML approach than what is sketched here, use it.

---

## Goal
Build all four reading category pages. These are **level 2** pages — they sit between
the Readings hub and the individual title pages.

Each category page shows a flat list of titles (books, papers, courses, sources).
Clicking a title goes **deeper into the site** — to that title's own page (built in CP-5).
No Notion URLs exist on these pages.

Pages to build:
- `readings/books.html`
- `readings/research-papers.html`
- `readings/lectures.html`
- `readings/other-readings.html`

---

## 3-Level Structure (for context)

```
readings.html                          ← hub (CP-3)
    ↓
readings/books.html                    ← THIS CP (category list)
    ↓
readings/books/inference-engineering.html  ← individual title page (CP-5)
    ↓
Notion page (opens in new tab)         ← end destination
```

---

## DAILY WORKFLOW — How Saransh Adds a New Title
When Saransh starts reading a new book, paper, or course:

1. He creates a new HTML file in the correct subfolder
   (e.g. `readings/books/new-book-title.html`) — this is done in CP-5.
2. He opens the relevant category page (e.g. `readings/books.html`).
3. He finds the edit comment block.
4. He copies the sample `<li>` line.
5. He pastes it at the TOP of the list (latest on top).
6. He updates the title text and the href to point to his new file.
7. He saves and pushes.

That is it. One line added to this file, one new file created in CP-5 template.

---

## Page Template (same for all four pages)

### Navbar
Use the shared navbar from CP-1.
Active class goes on **Readings** on all four pages.

### Stylesheet path
All four files are inside `readings/` folder. Use `../style.css`.

### Page Structure

```
Heading (h1) — e.g. "Books"
About line (muted, one sentence)
────────────────────────────────
Entry list (titles, latest on top)
────────────────────────────────
Footer
```

### Entry List Structure

```html
<!-- ===== TITLES =====
     To ADD a new title   : copy the sample <li> and paste it at the TOP (latest first).
     To REMOVE a title    : delete the entire <li>...</li> line.
     To EDIT a title      : update the text and href inside the <li>.
     href format          : ./books/your-file-name.html  (relative path to the title page)
     ==================== -->
<ul class="entry-list">

  <!-- SAMPLE — replace title text and href with your real content -->
  <li><a href="./books/sample-book.html">Title of Book</a></li>

</ul>
```

Each `<li>` is one line. Title is the link. Clicking goes to the title's own page inside the site.
Latest title always goes at the TOP.

---

## Page-by-Page Content

### books.html

```
Heading  : Books
About    : Books I am currently reading or have read, with notes on key ideas.
Sample   :
  Title  : Inference Engineering
  href   : ./books/sample-book.html
```

---

### research-papers.html

```
Heading  : Research Papers
About    : Papers I have read, summarized with handwritten notes.
Sample   :
  Title  : Attention Is All You Need
  href   : ./papers/sample-paper.html
```

---

### lectures.html

```
Heading  : Lectures
About    : Lecture notes from courses and talks I follow.
Sample   :
  Title  : CS336 — Language Modeling from Scratch (Stanford)
  href   : ./lectures/sample-course.html
```

---

### other-readings.html

```
Heading  : Other Readings
About    : Blog posts, articles, documentation, and anything else worth noting.
Sample   :
  Title  : The Illustrated Transformer
  href   : ./other/sample-other.html
```

---

## CSS — No new styles needed
The `entry-list` class is already defined in `style.css` from CP-1.
No additional CSS required for this checkpoint.

---

## What NOT to do
- Do not add Notion URLs on these pages — links go to internal site pages only
- Do not add dates, tags, or descriptions to list items — title link only
- Do not use JS for rendering — plain HTML list only
- Do not add search or filter

---

## CP-4 Checkpoint Verification

- [ ] All four pages exist with correct headings and about lines
- [ ] All four use `../style.css`
- [ ] Each page has the edit comment block above the entry list
- [ ] Each page has exactly one sample `<li>` entry pointing to its sample file
- [ ] Clicking a sample entry navigates to the correct sample file (shows "Coming soon")
- [ ] Navbar "Readings" has active class on all four pages
- [ ] Back navigation to `readings.html` works
- [ ] Footer renders correctly on all four pages
- [ ] Push to GitHub and confirm all four pages load at:
      - `https://SARPAT.github.io/readings/books.html`
      - `https://SARPAT.github.io/readings/research-papers.html`
      - `https://SARPAT.github.io/readings/lectures.html`
      - `https://SARPAT.github.io/readings/other-readings.html`
