# Academic Website — Project Brief

## Overview

Build a clean, minimal personal academic website for a postdoctoral researcher. The design uses a serif + monospace typographic pairing and prioritises whitespace, restraint, and readability over decoration.

---

## Design System

**Fonts**
- Body / headings: `Crimson Pro` (Google Fonts) — weights 300 and 400, italic variant
- Labels / nav / metadata: `DM Mono` (Google Fonts) — weights 300 and 400

**Colour palette**
- All colours via CSS variables for light/dark compatibility
- No decorative gradients, shadows, or background textures
- Borders: 0.5px, hairline only

**Spacing**
- Max content width: 740px, centred
- Generous vertical rhythm (rem-based)
- Narrow essay column on text-heavy pages: 600px max-width

**Navigation**
- Top of every page, full-width, separated by a 0.5px border
- Left: name in DM Mono (e.g. `Y. Surname`)
- Right: page links in DM Mono, uppercase, spaced — active link in primary text colour

---

## Site Structure

Five pages, no more:

| Page | Route | Purpose |
|------|-------|---------|
| Home | `/index.html` | Name, role, institution, photo, short bio, profile links |
| Research | `/research.html` | One flowing essay — no links out, pure text |
| Book | `/book.html` | Cover image, metadata, description, buy links |
| Publications | `/publications.html` | Grouped by type (articles / working papers), chronological, DOI links |
| CV | `/cv.html` | Embedded PDF reader + download link |

---

## Page Specifications

### Home (`index.html`)
- Two-column layout: text left (flex: 1), photo right (132×164px)
- Photo: plain rectangular frame, 2px border-radius, background placeholder until real image added
- Name: Crimson Pro, 36px, weight 300
- Role + institution: DM Mono, 11px, muted, two lines
- Bio: Crimson Pro, 17px, weight 300, line-height 1.85 — READ FROM `content/` folder and draft from the researcher's actual papers and CV
- Profile links row below bio: Email · Google Scholar · ORCID · ResearchGate · LinkedIn — icon + label pairs, separated by hairline dividers

### Research (`research.html`)
- Page label: DM Mono, 10px, uppercase, letterspaced
- Single flowing essay, max-width 600px
- Crimson Pro, 18px, weight 300, line-height 1.9
- No links, no section headers, no sidebar
- DRAFT THIS TEXT from the PDFs in `content/` — summarise research agenda, key arguments, methods, and current projects

### Book (`book.html`)
- Two-column: cover image left (200×280px placeholder), info right
- Metadata block under cover: Publisher, Year, Pages, ISBN — each in DM Mono, label + value
- Buy links below metadata: Publisher · Amazon · Google Books — each a bordered button with external link icon
- Book title: Crimson Pro, 28px, weight 400
- Subtitle: Crimson Pro, 20px, weight 300, italic
- Description: 3 paragraphs, Crimson Pro 17px weight 300 — DRAFT FROM `content/` files

### Publications (`publications.html`)
- Two sections, each preceded by a section label with a trailing hairline rule:
  1. `peer-reviewed articles`
  2. `working papers`
- Within each: newest first
- Each entry on a two-column grid: year (DM Mono, 10px, muted) | publication body
- Publication body: title (Crimson Pro 16px) + authors (DM Mono 10px) + venue in italic + DOI link
- Working papers: add a small status badge (`under review` or `in progress`) next to title
- POPULATE FROM `content/` folder — extract all publications with correct metadata

### CV (`cv.html`)
- Short header row: "Curriculum Vitae" label left, "download pdf" button right
- Embedded PDF viewer: `<iframe>` or `<embed>` pointing to `content/cv.pdf`, height 780px, bordered
- "Last updated: [Month Year]" in DM Mono, 10px, right-aligned below the embed

---

## File Structure to Create

```
my-academic-site/
├── CLAUDE.md
├── index.html
├── research.html
├── book.html
├── publications.html
├── cv.html
├── style.css          ← shared stylesheet
├── content/           ← DROP YOUR FILES HERE before running
│   ├── cv.pdf
│   ├── book.pdf (or book chapters)
│   └── paper-1.pdf, paper-2.pdf, etc.
└── assets/
    ├── photo.jpg      ← your headshot (add later)
    └── book-cover.jpg ← book cover image (add later)
```

---

## CLAUDE.md to create at project root

```markdown
# Academic website project

Personal academic website for [Your Name], postdoctoral researcher in [Field] at [University].

## Design rules
- Fonts: Crimson Pro (body) + DM Mono (labels/nav) — load from Google Fonts
- All colours via CSS variables only — no hardcoded hex values
- Max content width: 740px centred, essay columns 600px
- Borders: 0.5px hairline only, no shadows, no gradients
- Navigation identical across all pages

## Content
- All personal content (bio, research profile, publications, book description) must be
  drafted by reading PDFs in the content/ folder
- Do not invent or hallucinate publication titles, journal names, or dates
- Use placeholder brackets [like this] only where information is genuinely missing

## Structure
- Five pages only: index, research, book, publications, cv
- Shared stylesheet: style.css
- No JavaScript frameworks — plain HTML and CSS only
- Site must work when opened locally (no server required) and be deployable to GitHub Pages
```

---

## How to run this

1. Create the `my-academic-site/` folder on your computer
2. Drop your PDFs into the `content/` subfolder (CV, papers, book)
3. Open the folder in Claude Code Desktop
4. Paste this brief and say:

> "Read all the PDFs in the content/ folder, then build this website according to the brief.
> Start by drafting the bio, research essay, book description, and publications list from
> my actual documents. Then build all five HTML pages using the design spec."

5. Once built, open `index.html` in your browser to preview
6. Iterate in plain English — "make the bio shorter", "add this paper", "change the photo"

---

## Deployment (GitHub Pages — free)

Once happy with the site, tell Claude Code:
> "Help me deploy this to GitHub Pages so it has a public URL."

It will walk you through creating a repository and publishing the site for free.

