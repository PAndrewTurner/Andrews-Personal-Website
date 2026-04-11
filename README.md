# P. Andrew Turner — Personal Website

Personal portfolio and professional website for **Paul Andrew Turner Jr.**, a Corporate Financial Consultant at Verizon working at the intersection of applied AI, data science, and corporate finance.

**Live site:** _add your GitHub Pages URL here once deployed_

---

## About the site

A single-page personal website covering:

- **Hero** — Introduction, tagline, and headshot
- **About** — Narrative bio and parallel Education / Career timelines
- **Skills** — Technical toolkit grouped by category
- **Projects** — Selected work from Verizon and graduate research
- **Writing** — Link to the [Substack newsletter](https://pandrewturner.substack.com)
- **Contact** — Email, LinkedIn, Substack, Instagram

---

## Tech stack

- **HTML5** — Semantic, accessible markup
- **CSS3** — Custom properties, CSS Grid, Flexbox, no frameworks
- **Vanilla JavaScript** — Intersection Observer for scroll reveals, smooth scroll, mobile nav

No build step. No dependencies. Just three files plus assets.

---

## File structure

```
.
├── index.html        # Main page
├── styles.css        # All styles
├── script.js         # Scroll reveal, navbar, mobile menu
├── 404.html          # Custom 404 page
├── .gitignore
├── README.md
└── assets/
    ├── Headshot.jpg
    ├── UF Seal.png
    ├── FSU Seal.png
    ├── FSU Law.jpg
    └── UCF Seal.png
```

---

## Local development

No build tools required. Just open `index.html` in a browser.

For a local server (recommended for testing relative paths):

```bash
# Python 3
python3 -m http.server 8000

# Node
npx serve
```

Then visit `http://localhost:8000`.

---

## Deployment (GitHub Pages)

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set source to **Deploy from a branch**.
4. Choose branch `main` and folder `/ (root)`.
5. Save. The site will be live at `https://<username>.github.io/<repo>/` within a minute.

---

## Design

**Palette:**
- Background: `#0a0f1c` (deep dark navy)
- Surfaces: `#0d1b2a` (Prussian blue tone) / `#162032`
- Primary accent: `#002FA7` (International Klein Blue)
- Highlight: `#f0b429` (gold — for achievements and academic highlights)

**Typography:**
- Inter (300 / 400 / 500 / 600 / 700 / 800)
- JetBrains Mono (for technical labels and tags)

---

## Contact

- **Email:** PAndrewTurner@outlook.com
- **LinkedIn:** [in/pandrewturner](https://www.linkedin.com/in/pandrewturner/)
- **Substack:** [pandrewturner.substack.com](https://pandrewturner.substack.com)
- **Instagram:** [@PAndrewTurner](https://instagram.com/PAndrewTurner)
