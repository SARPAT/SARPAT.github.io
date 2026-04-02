# CP-3 — Readings Hub (`readings.html`)

## For Claude Code
You have freedom in implementation details.
Follow the design decisions and content exactly as specified.
Do not introduce new colors, fonts, or layout patterns not listed here.
Prefer clean, readable, minimal code over clever solutions.
If you see a better semantic HTML approach than what is sketched here, use it.

---

## Goal
Build the `readings.html` page — the central hub for all of Saransh's reading content.
This page introduces the Readings section and links out to four sub-sections.
No actual reading entries live here — those are in CP-4.

---

## Page Sections (in order)

### 1. Navbar
Use the shared navbar from CP-1.
The `active` class goes on the **Readings** link.

---

### 2. Page Heading

```
Readings
```

Use `<h1>`.

---

### 3. About Blurb

Use exactly this text:

```
This section contains all my readings from various sources — Books, Research Papers,
Lectures, and Other Readings. I prefer handwritten notes, so each entry has a
handwritten note embedded within a blog post.
```

---

### 4. Sub-section Links

Four sub-sections, each displayed as a clean block with:
- Sub-section name as a bold heading (links to its own page)
- One line of muted description text below it
- A thin divider between each block

Use exactly this content and these internal links:

```
Books
→ /readings/books.html
Description: Books I am currently reading or have read, with notes on key ideas.

Research Papers
→ /readings/research-papers.html
Description: Papers I have read, summarized with handwritten notes.

Lectures
→ /readings/lectures.html
Description: Lecture notes from courses and talks I follow.

Other Readings
→ /readings/other-readings.html
Description: Blog posts, articles, documentation, and anything else worth noting.
```

**Structure for each sub-section block:**

```html
<!-- Each block follows this exact pattern. Do not change the structure. -->
<div class="reading-section-block">
  <a href="/readings/books.html" class="reading-section-title">Books</a>
  <p class="muted">Books I am currently reading or have read, with notes on key ideas.</p>
</div>
<hr>
```

Add this CSS to `style.css`:

```css
/* ---- Reading Section Blocks (readings.html hub) ---- */
.reading-section-block {
  padding: 1rem 0;
}

.reading-section-title {
  font-size: 1.1rem;
  font-weight: bold;
  color: #2563eb;
  display: block;
  margin-bottom: 0.3rem;
}
```

---

### 5. Footer
Use the shared footer from CP-1 exactly.

---

## CP-3 Checkpoint Verification

- [ ] Page heading "Readings" renders correctly
- [ ] About blurb is present with exact text
- [ ] All four sub-section blocks are visible — Books, Research Papers, Lectures, Other Readings
- [ ] Each sub-section title is a working hyperlink to its respective page
- [ ] Muted description text appears below each title
- [ ] Clicking each link navigates to the correct page (will show "Coming soon" from CP-0 for now)
- [ ] Navbar "Readings" link is highlighted with active class
- [ ] Footer renders correctly
- [ ] Push to GitHub and confirm live at `https://SARPAT.github.io/readings.html`
