# Site Redesign: "The Ledger" — Design Spec

**Date:** 2026-07-01
**Scope:** Full visual redesign (restyle, not rebuild) of all three pages: `index.html`, `personal.html`, `404.html`
**Status:** Approved by Andrew via visual companion session

## Concept

**"A ledger with margin notes."** Swiss-poster structure — flat color blocks, hard rules, oversized grotesque type — softened by handwritten-style serif annotations in Andrew's voice, and his photos, seals, and emoji kept at full weight. Professional discipline with a visible human inside it.

Validated through iterative mockups: Ledger Light base → Full Alternation blue/white rhythm → Archivo-leads type pairing → contained hero layout → personal-touch layer (v2 board) → Beyond Work + 404 treatments. All approved.

## Design System

### Palette

| Token | Value | Use |
|---|---|---|
| Canvas | `#FAFAF7` | Warm off-white page background (white sections) |
| Ink | `#0A0A0A` | Text, hard rules, footer background |
| Klein Blue | `#002FA7` | Full-bleed section canvas; accent/link color on white sections |
| Gold | `#F0B429` | Accent on blue sections only: key words, stat numbers, section labels, margin-note rules |
| Card white | `#FFFFFF` | Card faces on white sections |

- No gradients, no glows, no background grid, no rounded corners, no box shadows.
- Flat color blocks; borders are `1px` or `2px` solid ink (white/translucent-white on blue).

### Typography

| Face | Weights | Role |
|---|---|---|
| **Archivo** | 400 / 700 / 900 | Leads. All headlines (900, tight letter-spacing −0.02 to −0.04em), body text (400) |
| **Fraunces** (incl. italic) | 400 / 600 / 900 + italics | Accent only: single accent words inside headlines, pull quotes, margin notes, wink captions, book authors |
| **IBM Plex Mono** | 400 / 600 | Section numbers/labels, dates, stats labels, tags, status lines. Replaces JetBrains Mono |

Google Fonts load. Type scale increases substantially: hero headline `clamp(56px, 9vw, 120px)`; section titles `clamp(40px, 5vw, 64px)`.

### Structural motifs

- **Section rhythm (full alternation):** sections alternate white → blue → white → blue down every page. Where two white sections are adjacent (e.g., Projects then Beyond Work teaser), a `2px` black ledger rule separates them. Footer is black.
- **Ledger rules:** `2px solid #0A0A0A` section dividers on white; `1px rgba(255,255,255,0.35)` rules on blue.
- **Margin notes:** Fraunces italic asides in Andrew's first-person voice, set off by a gold left rule (`2–3px solid #F0B429`) or placed in a side column on wide viewports.
- **Cards:** square-edged, `1px solid #0A0A0A` on white / `1px solid rgba(255,255,255,0.4)` on blue. Featured cards get a `4px` Klein Blue top bar. Hover: blue border + small translateY lift, no shadow.
- **Section headers:** mono number + label (`01 — ABOUT`) in Klein Blue on white / gold on blue, then Archivo 900 title.

## Page Designs

### index.html

1. **Nav (white):** `#FAFAF7` bar, `2px` black bottom rule, Archivo 900 logo, mono nav links. No blur/transparency. Sticky.
2. **Hero (BLUE):** contained max-width layout, text and headshot adjacent with fixed gap (no floating to screen edge — explicitly approved fix). Mono kicker `PAUL ANDREW TURNER JR. — ORLANDO, FL`; Archivo 900 headline "Finance, modeled *forward.*" with "forward." in Fraunces gold italic; Fraunces italic tagline "— analyst by training, builder by instinct, wonk by choice"; white-rule divider; inline stats (8,400+ HRS AUTOMATED / 5 DEGREES / gold Archivo 900 numbers, mono labels) replacing floating stat chips; white solid + white outline CTAs. Headshot: real photo, larger presence, `3px` white border, Fraunces caption "that's me ↑".
3. **About (WHITE):** current copy unchanged. Fraunces pull-quote of the force-multiplier thesis with gold rule. Margin note: "I'm the person my team comes to when something needs automating." Education + Career timelines restyled: mono dates in Klein Blue, black rule column headers, university seals and Verizon V images kept. Fraunces teaser under career: "…and before finance? I was a police officer. Long story — good one." Certifications row keeps structure, restyled square cards.
4. **Toolkit (BLUE):** six categories as white-outlined tiles; tags as outlined mono chips; Python/Swift/R/Claude logos in white inset squares for legibility.
5. **Honors (WHITE):** two-column, badges/emblem images kept, black-rule list separators.
6. **Projects (WHITE):** square black-bordered cards on white card faces; featured cards get blue top bar; badges become solid squares (gold = in progress, blue = featured, outlined = academic/Verizon). Content unchanged.
7. **Beyond Work teaser (NEW, WHITE):** headline "Not just spreadsheets. *A fuller picture →*" + emoji chip row (📷 Airshow photographer · 🏳️‍🌈 Orlando Pride volunteer · 🦅 Eagle Scout · 🐕 German Shepherd dad · 🌍 EN·DE·JP), links to personal.html.
8. **Writing (BLUE):** Archivo 900 "On Substack", Fraunces italic subline "where I write honestly about the economy and the world", Substack logo, two recent-article tiles white-outlined.
9. **Contact (WHITE):** "Let's build something *that matters.*" (Fraunces blue italic accent); contact links as 2×2 black-bordered squares; existing links/rel attributes preserved.
10. **Footer (BLACK):** Archivo 900 name left; Fraunces gold italic right: "built with rigor and care — and a dog at my feet".

### personal.html

Same alternation: Hero (BLUE, "A fuller *picture.*", italic tagline "— reader, writer, photographer, advocate") → At a Glance (WHITE, six square tiles, mono labels, content unchanged) → Craft & Hobbies (BLUE, emoji kept, white-outlined tiles) → Community & Advocacy (WHITE, three photo cards kept — Orlando.jpg, BSA.png, Pride Progress Flag.png — black borders, blue top bars) → Languages & World (BLUE) → Bookshelf (WHITE, ledger lists: black rule rows, Archivo titles, Fraunces italic authors) → Looking Forward (BLUE, "Policy, finance, technology — *eventually, public service.*") → black footer.

### 404.html

Full-bleed Klein Blue page. Gold mono tag `⚠ RECONCILIATION FAILED`; giant Archivo 900 "404"; Fraunces gold italic "This page didn't balance."; white rule; mono status line `STATUS: HTTP 404 · VARIANCE: 1 PAGE · ACTION: INVESTIGATE`; white CTAs. Inline styles updated to match system.

## Technical Approach

- **`styles.css`: full rewrite** (~new file). Design tokens as CSS custom properties. Keep class names where structure survives so HTML edits stay minimal.
- **HTML: light-touch edits.** Content, copy, links, images, meta/OG tags, favicon, skip-to-content, `rel="me"` all preserved. New elements: hero tagline, margin notes, police teaser, Beyond Work teaser band, footer sign-off. Fonts link swaps to Archivo + Fraunces + IBM Plex Mono.
- **`script.js`: keep** scroll-reveal, mobile nav, active-link, footer year. Navbar scroll behavior simplifies (solid bar always; may drop `scrolled` class logic).
- **Favicon:** regenerate `favicon.svg` to match (Klein Blue square, Archivo-style "PT", gold).
- **Accessibility:** all blue/white and gold-on-blue text combinations must meet WCAG AA contrast (gold `#F0B429` on Klein Blue passes for large text; verify small-text uses).
- **Responsive:** hero stacks (text above headshot) under 768px; grids collapse 3→2→1; type scale clamps down.
- **Cache busting:** bump `?v=` strings on CSS/JS references.
- **Dual-directory sync:** every changed file copies to `~/Documents/GitHub/Andrew-s-Personal-Website/` per project requirement.

## Out of Scope

- No photography gallery (explicitly deferred)
- No resume download (declined — contact via LinkedIn/email)
- No analytics (deferred)
- No content rewrites beyond the new personal-voice microcopy listed above
- No build tools; site stays plain HTML/CSS/JS

## Success Criteria

1. All three pages render the new system with zero legacy dark-theme remnants
2. All existing content, images, links, and SEO/a11y improvements survive
3. Mobile layouts clean at 375px, 768px, 968px breakpoints
4. WCAG AA contrast maintained
5. Both directories in sync
