# strugen.com 'Joe Carlsmith' Redesign Implementation Plan

> **For Hermes:** Redesign strugen.com to match the minimalistic, serif-based, academic aesthetic of joecarlsmith.com.

**Goal:** Transform the blog from its current cyberpunk, neon-emerald/gold dark theme with glassmorphism into a highly polished, typography-centric, paper-like light theme (serif-heavy) that mirrors the layout, content organization, and professional intellectual tone of joecarlsmith.com.

**Architecture:** 
- **Style Overhaul:** Replace Inter/Space Grotesk with Georgia/system-serif for all headings and essay prose, coupled with a minimal sans-serif for UI elements. Redefine colors to a warm cream/off-white background and charcoal-black text with an elegant Amethyst Purple accent (`#4A2E80` / `#9966CC`) to tie into the Center for Sentience brand.
- **Content Map & Hero:** Completely restructure the homepage landing page, removing the massive visual hero in favor of a low-profile, high-impact personal statement detailing Jhonatan's background (computational physics, IT consulting, Center for Sentience).
- **Thematic Categorization:** Group articles into distinct sections ("Latest", "Favorites", "Valence & AI Sentience", and "Personal Philosophy & Contemplation") using clean list structures rather than shadowed cards.

**Tech Stack:** Astro, Tailwind CSS, Georgia/system-serif.

---

## 📋 Bite-Sized Implementation Tasks

### Task 1: Redefine CSS variables and theme in `global.css`
**Objective:** Setup the clean paper-like light theme and typography system in Tailwind.
**Files:** 
- Modify: `site/src/styles/global.css`
**Details:**
- Replace the dark theme colors with a light paper background (`#fcfcfc`), dark charcoal text (`#1a1a1a`), and a soft muted gray (`#666666`).
- Define `--font-serif` to use `Georgia, 'Times New Roman', serif` and `--font-sans` to use `'Inter', sans-serif`.
- Remove glowing, neon, and glassmorphism classes, replacing them with a simple, high-quality article container class (`max-w-2xl mx-auto`).

### Task 2: Update the Main Layout (`Layout.astro`)
**Objective:** Apply the new styling, layout container, navigation, and footer globally.
**Files:**
- Modify: `site/src/layouts/Layout.astro`
**Details:**
- Remove the `.grid-bg` and other dark theme classes from `<body>`.
- Overhaul `<nav>` to be ultra-clean: raw text logo "strugen" on the left, and simple text-link menu items (`About`, `Archive`, `Contact`) on the right.
- Strip footer down to a minimalistic, text-only layout with copyright and social links, removing horizontal lines and gradient dividers.

### Task 3: Restructure the Homepage (`index.astro`)
**Objective:** Implement the Joe Carlsmith intro copy and thematic article indexing.
**Files:**
- Modify: `site/src/pages/index.astro`
**Details:**
- Overhaul the hero section with Jhonatan's targeted introduction:
  - *Intro:* "I’m a researcher, consultant, and founder. I lead the Center for Sentience..."
  - *Logical Flow:* "Much of my work is about trying to help us orient wisely towards the nature of sentience and positive valence. This work spans several domains..."
  - *Links:* Learn more about me here. My CV is here. My twitter is @strugen. My email is strugen@proton.me.
- Create distinct sections on the homepage:
  - **Latest** (combining and chronological listing): *Conditional Happiness vs. Equanimity* (draft), *How do you learn to change?*, and *On Being Here*.
  - **Favorites**
  - **Valence & AI Sentience** (e.g. referencing the 12-month technical roadmap, symmetry theory, and any related essays).
  - **Personal Philosophy & Contemplation**
- Replace all article card elements with elegant text links: bold title, thin line break, optional small subtitle/excerpt in muted gray, and a small mono date.

### Task 4: Redesign the Article Page Layout (`ArticleLayout.astro`)
**Objective:** Create a distraction-free, beautiful reading experience for individual blog posts.
**Files:**
- Modify: `site/src/layouts/ArticleLayout.astro`
**Details:**
- Set the article content container to `max-w-2xl mx-auto px-4 py-12`.
- Apply `font-serif` and a larger font size (`text-lg` or `text-[18px]`), with generous line-height (`leading-relaxed` or `leading-8`).
- Headings should be in clean serif, bold, with standard spacings.
- Remove all tags, cards, or glowing buttons, opting for a clean meta-line (date, read time) at the top under the main title.

### Task 5: Redesign the About Page (`about.astro`)
**Objective:** Align the About page with the minimalist light theme.
**Files:**
- Modify: `site/src/pages/about.astro`
**Details:**
- Strip glass cards and background gradients.
- Present Jhonatan's biography, handles, and connection to the Center for Sentience in clean, structured serif prose.

### Task 6: Redesign the Contact Page (`contact.astro`)
**Objective:** Align the Contact form with the light-theme aesthetic.
**Files:**
- Modify: `site/src/pages/contact.astro`
**Details:**
- Change input fields to have a simple white background with thin borders and sharp corners, matching the academic/classic design.
