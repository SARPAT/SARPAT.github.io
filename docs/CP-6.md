# CP-6 — Blogs Page (`blogs.html`)

## For Claude Code
You have freedom in implementation details.
Follow the design decisions and content exactly as specified.
Do not introduce new colors, fonts, or layout patterns not listed here.
Prefer clean, readable, minimal code over clever solutions.
If you see a better semantic HTML approach than what is sketched here, use it.

---

## Goal
Build the `blogs.html` page — a flat, clean list of technical blog posts.
Each blog title is a hyperlink that opens the published Notion blog page in a new tab.
No sub-levels here — this is intentionally flat. Latest post always on top.

---

## Structure (flat — only 2 levels)

```
blogs.html                          ← THIS CP
    ↓
Notion blog page (opens in new tab) ← end destination
```

Unlike the Readings section, Blogs has no sub-categories and no individual title pages.
One list. One click. Opens Notion.

---

## DAILY WORKFLOW — How Saransh Adds a New Blog Post

1. He writes and publishes a blog post on Notion (gets a public Notion URL).
2. He opens `blogs.html`.
3. He finds the edit comment block.
4. He copies the sample `<li>` line.
5. He pastes it at the TOP of the list (latest post always on top).
6. He updates the title text and the Notion URL.
7. He saves and pushes.

One line. That is the entire workflow.

---

## Page Sections (in order)

### 1. Navbar
Use the shared navbar from CP-1.
The `active` class goes on the **Blogs** link.

---

### 2. Page Heading

```
Technical Blogs
```

Use `<h1>`.

---

### 3. About Line

One line of muted text below the heading:

```
Writing about ML systems, GPU programming, inference optimization, and things I learn along the way.
```

---

### 4. Blog Entry List

```html
<!-- ===== BLOG POSTS =====
     To ADD a new post    : copy the sample <li> and paste it at the TOP (latest first).
     To REMOVE a post     : delete the entire <li>...</li> line.
     To EDIT a post       : update the title text and the Notion URL in href.
     Notion URL format    : paste your published Notion page URL directly as the href.
     target="_blank"      : always keep this — opens Notion in a new tab.
     ======================== -->
<ul class="entry-list">

  <!-- SAMPLE — replace title and href with your real Notion blog post -->
  <li><a href="https://notion.so/your-blog-post-url-here" target="_blank">Title of Blog Post</a></li>

</ul>
```

Each `<li>` is one line. Title is the hyperlink. Opens Notion in a new tab.
Latest post always at the TOP.
No dates, no tags, no descriptions — just the title as a clean hyperlink.

---

### 5. Footer
Use the shared footer from CP-1 exactly.

---

## CSS — No new styles needed
The `entry-list` class is already defined in `style.css` from CP-1.
No additional CSS required for this checkpoint.

---

## What NOT to do
- Do not add dates or tags to blog entries — title link only
- Do not embed Notion content in an iframe — links open in a new tab only
- Do not add sub-categories or filters
- Do not use JS for rendering — plain HTML list only
- Do not add a "Read more" button or excerpt — title only

---

## CP-6 Checkpoint Verification

- [ ] Page heading "Technical Blogs" renders correctly
- [ ] About line is present with exact text
- [ ] Edit comment block is present above the entry list
- [ ] One sample `<li>` entry exists with placeholder Notion URL
- [ ] Sample entry opens in a new tab (`target="_blank"`)
- [ ] Navbar "Blogs" link has the active class
- [ ] Footer renders correctly
- [ ] Push to GitHub and confirm live at `https://SARPAT.github.io/blogs.html`
