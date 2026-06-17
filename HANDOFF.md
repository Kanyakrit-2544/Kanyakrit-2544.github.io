# Portfolio Landing Page — Handoff to Claude Code

## Overview

Rebuild `index.html` (the existing portfolio file) as a full landing page.
Layout inspired by Zola.com structure. Theme and color stay exactly as current file.

---

## Reference files

- `index.html` — existing portfolio (current design, colors, fonts — keep all of it)
- `Zola-1.webp` — layout reference screenshot (structure only, not design)

---

## Color & font — DO NOT CHANGE

```
--bg: #FAFAF9
--surface: #F4F4F2
--border: #E5E5E3
--text: #1A1A1A
--muted: #6B6B68
--accent: #2563EB
--accent-light: #EFF4FF
Font display: DM Sans 500
Font body: Inter 400
```

---

## Page structure — 6 sections in order

### 1. Hero (two-column layout)

**Left column:**
- Small eyebrow label: `IT Support & Web Builder · Bangkok, Thailand`
- Availability badge (green dot + "Available for new projects")
- H1 headline (large, 2–3 lines):
  ```
  I fix problems,
  then build the tools
  that prevent them.
  ```
- Subheading (1–2 lines, muted color):
  `I help small businesses get online faster — AI-assisted web development, network setup, and IT support. Remote-friendly.`
- Two CTA buttons:
  - Primary (dark bg): `See my work` → scrolls to #work
  - Outline: `Get in touch` → scrolls to #contact

**Right column:**
- Mockup card (styled box, no real image needed):
  - Show a fake browser window frame (gray bar + 3 dots)
  - Inside: display "3S Suksonsin" as a mini site preview using simple shapes/text
  - Card has subtle border, border-radius 12px, bg white

**Layout:** CSS Grid, 55% left / 45% right, gap 60px, vertically centered.
On mobile: stack to single column, image below text.

---

### 2. Stats bar (full-width, light surface bg)

3 stats in a row, separated by vertical dividers:

| Number | Label |
|--------|-------|
| Full-stack | Web development |
| 2× faster | With AI tools |
| TH / EN | Bilingual delivery |

Style: `background: var(--surface)`, padding 40px 0, no border-radius (full bleed).

---

### 3. Features — "Why work with me" (3 columns)

Section heading: `Why clients choose me`

3 feature cards, each with:
- Icon (Unicode or simple SVG, accent color)
- Title (bold, 15px)
- Description (13–14px, muted, 2 lines max)

Content:
```
🌐  AI-powered builds
    Websites delivered faster using Claude and modern AI tools — without cutting quality.

🔧  IT Support included
    Network setup, troubleshooting, and ongoing support bundled with every project.

📄  Full documentation
    Every project ships with a Thai-language manual, so you're never dependent on me.
```

Card style: `background: var(--surface)`, border-radius 10px, padding 24px, no border.
On hover: add `border: 1px solid var(--border)`.

---

### 4. Case study showcase (alternating layout — like Zola's feature blocks)

Section heading: `Work`

**Block 1 — 3S Suksonsin** (image left, text right):

Left: mockup placeholder box (aspect ratio ~16:9, bg `var(--surface)`, border-radius 10px, border 1px `var(--border)`) — inside write "3S Suksonsin Website" centered in muted text, monospace font.

Right: text block
- Tags row: `React` `Node.js` `MySQL` `Full-stack` `AI-assisted` — monospace pill tags, bg surface, 11px
- Title: `3S Suksonsin — Corporate Website & Admin CMS`
- Client line: `Suksonsin Limited Partnership · B2B System Integration · 2024`
- 3–4 bullet points (use `→` prefix):
  - Bilingual TH/EN site with 8 pages and 6 service sub-pages
  - Quote form → Database + Google Sheets + Email simultaneously
  - Admin CMS with JWT auth, project management, and image upload
  - Deployed on Windows Server 2022 with full Thai documentation
- Result callout box (bg `var(--accent-light)`, left border 3px `var(--accent)`, blue text):
  `The client now manages their own portfolio and quote pipeline — without needing a developer.`
- Link: `View on GitHub →` (accent color, links to https://github.com/Kanyakrit-2544/3s-website)

On mobile: stack to single column, mockup on top.

> When more projects are added later, alternate layout: odd = image left, even = image right.

---

### 5. Services + pricing cards (3 columns)

Section heading: `Services`

3 cards side by side. Middle card gets `border: 2px solid var(--accent)` as "featured".

**Card 1 — Starter**
- Name: `Website`
- Price: `ติดต่อสอบถาม`
- Features list:
  - Landing page or corporate site
  - Mobile responsive
  - Contact form
  - Delivered with documentation
- CTA button (outline): `Get a quote`

**Card 2 — Full Build** ← featured (accent border + small badge "Most popular")
- Name: `Full Build`
- Price: `ติดต่อสอบถาม`
- Features list:
  - Everything in Website
  - Admin CMS
  - Database + API backend
  - Google Sheets / email integration
  - Thai-language manual included
- CTA button (primary dark): `Get a quote`

**Card 3 — Monthly Care**
- Name: `Monthly Care`
- Price: `ติดต่อสอบถาม`
- Features list:
  - Website maintenance
  - IT Support & network monitoring
  - Priority response
  - Monthly report
- CTA button (outline): `Get a quote`

All "Get a quote" buttons scroll to #contact.

---

### 6. Footer CTA (full-width, dark bg `#1A1A1A`)

- Tagline in white, large italic script feel:
  `Built with AI, shipped with care.`
- Sub line (muted, smaller): `Available for freelance projects and remote IT support.`
- One button (white bg, dark text): `Start a project →` → scrolls to #contact

---

### 7. Contact section (above footer, light bg)

Section heading: `Contact`

Keep exactly as current `index.html` — 4 contact link cards:
- Line (fastest response)
- Email
- GitHub
- Fastwork

---

## Nav (sticky, keep as-is)

- Left: name `Kanyakrit`
- Right links: Services · Work · Skills · Contact
- Backdrop blur, border-bottom on scroll

---

## Technical requirements

- Single HTML file (`index.html`) — no external JS frameworks
- All CSS in `<style>` tag in `<head>`
- Fonts from Google Fonts (DM Sans + Inter) — already in current file
- Smooth scroll: `html { scroll-behavior: smooth; }`
- Responsive: mobile breakpoint at 600px
- `@media (prefers-reduced-motion: reduce)` for animations
- No JavaScript required except optional scroll-triggered nav border

Optional JS (small inline `<script>` at bottom):
```js
// Add border to nav on scroll
window.addEventListener('scroll', () => {
  document.querySelector('nav').style.borderBottomColor =
    window.scrollY > 10 ? 'var(--border)' : 'transparent';
});
```

---

## What NOT to change

- Color variables (exact hex values)
- Font families (DM Sans + Inter)
- Case study content (facts, tech stack, metrics)
- Contact links section
- GitHub link: https://github.com/Kanyakrit-2544/3s-website

---

## Placeholder values to fill in later

These are marked with comments `<!-- TODO -->` in the output file:

- Line ID URL
- Email address
- Fastwork profile URL
- Real screenshot/image of 3S website (replace mockup placeholder)

---

## Output

Single file: `index.html`
Ready to push to `Kanyakrit-2544.github.io` repo root for GitHub Pages deployment.
