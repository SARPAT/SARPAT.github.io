# CP-2 — Home Page (`index.html`)

## For Claude Code
You have freedom in implementation details.
Follow the design decisions and content exactly as specified.
Do not introduce new colors, fonts, or layout patterns not listed here.
Prefer clean, readable, minimal code over clever solutions.
If you see a better semantic HTML approach than what is sketched here, use it.

---

## Goal
Build the complete `index.html` home page.
By the end of CP-2, the home page should be fully presentable —
hero, projects, and footer — with research and publications stubbed but hidden.

---

## Page Sections (in order)

### 1. Navbar
Use the shared navbar snippet from CP-1.
The `active` class goes on the **Home** link.

---

### 2. Hero Section
Layout: Photo on the left (circle crop) + text block on the right.
On mobile: photo stacks above text.

**Photo:**
- Filename: `photosara.jpg` (in repo root)
- Shape: circle, approximately 120px diameter
- Float left on desktop, centered above text on mobile

**Text block (use exactly this content):**

```
Saransh Patel
Undergraduate · Computer Science · ABES Engineering College
```

Then the intro paragraphs — use exactly this text, preserve paragraph breaks:

```
I am an undergraduate Computer Science student with a deep interest in
ML Systems and Performance Engineering. I spend most of my time trying
to understand how large language models actually run on hardware, what
makes inference fast, what makes it slow, and what can be done about it.

My research interests are centered on LLM inference optimization, CUDA
kernel engineering, GPU memory systems, and efficient AI deployment. I
am particularly drawn to the intersection of systems and machine learning
— the layer where software meets hardware and where performance decisions
have real consequences.

I am currently building my foundations through a structured self-study
path covering GPU architecture, CUDA programming, distributed training,
and inference systems. Alongside that, I work on hands-on projects
benchmarking and optimizing inference pipelines, profiling GPU kernels,
and experimenting with quantization techniques like INT8 and AWQ.

Outside of technical work, I believe in learning in public — sharing
what I build, what I measure, and what I learn along the way.
```

**CTA connect line** — below the intro text:

```
Go checkout my Readings & Blogs sections.
Let's connect: saranshappy@gmail.com · Twitter/X · GitHub
```

All three are hyperlinks:
- Email: `mailto:saranshappy@gmail.com`
- Twitter/X: `https://x.com/SARAPATEL21`
- GitHub: `https://github.com/SARPAT`

---

### 3. Projects Section

Heading: `Projects` (h2)
Subheading (muted, small): `Present in current build`

**IMPORTANT — Easy Edit Structure:**
Each project must be a self-contained HTML block with a clear comment marker.
Saransh will add or remove projects by simply copying or deleting one block.
The structure must make this obvious — no complex logic, no loops, no JS.

Add this comment before the projects list:
```html
<!-- ===== PROJECTS =====
     To ADD a project : copy one <li> block and paste it as a new <li>.
     To REMOVE a project : delete the entire <li>...</li> block.
     To EDIT a project : update the title, href, description, and tags inside the block.
     ==================== -->
```

Each project block follows this structure:
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

Add these styles to `style.css` for project entries:
```css
/* ---- Project Entries ---- */
.project-entry {
  list-style: none;
  padding: 1rem 0;
  border-bottom: 1px solid #e5e5e0;
}

.project-entry:last-child {
  border-bottom: none;
}

.project-title {
  font-size: 1rem;
  font-weight: bold;
  color: #2563eb;
  display: block;
  margin-bottom: 0.3rem;
}

.project-desc {
  font-size: 0.95rem;
  color: #1a1a1a;
  margin-bottom: 0.4rem;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem;
}
```

**Current projects (use exactly this data):**

Project 1:
```
Title       : RAG Agent — Document Chatbot
Link        : https://github.com/SARPAT/RagAgent_document_chatbot
Description : A Retrieval-Augmented Generation chatbot for querying arXiv research
              papers. Built with LangChain, NVIDIA AI Endpoints, FAISS vector store,
              and Gradio.
Tags        : Python · LangChain · RAG · NVIDIA
```

Project 2:
```
Title       : Chakra — Middleware Framework
Link        : https://github.com/SARPAT/Chakra
Description : Intelligent graceful degradation middleware for Node.js/Express apps.
              Routes requests to reduced-functionality fallbacks under load, using a
              physics-inspired priority model. 583 tests across 12 suites.
Tags        : TypeScript · Node.js · Express · Middleware
```

---

### 4. Research Section (Hidden — Placeholder)

Add this in HTML but hide it. It must not appear on the page at all:

```html
<!-- RESEARCH SECTION — hidden until content is ready. Remove display:none to show. -->
<section style="display:none;">
  <h2>Research</h2>
  <p>Coming soon.</p>
</section>
```

---

### 5. Publications Section (Hidden — Placeholder)

```html
<!-- PUBLICATIONS SECTION — hidden until content is ready. Remove display:none to show. -->
<section style="display:none;">
  <h2>Publications</h2>
  <p>Coming soon.</p>
</section>
```

---

### 6. Footer
Use the shared footer from CP-1 exactly:

```
B.Tech Computer Science · ABES Engineering College · Ghaziabad
saranshappy@gmail.com · GitHub · X · CV
```

CV opens in new tab via:
`https://drive.google.com/file/d/1dKrvHeXV_Ry9O5daPK3I3dcJsuFY_GEu/preview`

---

## Site Config Block
Keep this comment at the top of `index.html` body, just after `<body>`:

```html
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

## What NOT to do
- Do not add animations or hover effects beyond what is already in `style.css`
- Do not add any new colors outside the design system
- Do not add a "Download CV" button — CV is a navbar link only
- Do not show Research or Publications sections — they are hidden placeholders only
- Do not use JavaScript for rendering projects — plain HTML list only

---

## CP-2 Checkpoint Verification

- [ ] Hero section renders correctly — photo circle left, text right on desktop
- [ ] On mobile, photo stacks above text
- [ ] All three connect links (email, X, GitHub) work correctly
- [ ] Both projects display with title, description, and tags
- [ ] GitHub repo links open in a new tab
- [ ] The edit instruction comment block is present in the HTML source above the projects list
- [ ] Research and Publications sections exist in HTML but are invisible on the page
- [ ] Footer links all work — CV opens Google Drive in a new tab
- [ ] Push to GitHub and confirm live at `https://SARPAT.github.io`
