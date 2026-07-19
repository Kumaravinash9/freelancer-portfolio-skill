---
name: freelancer-portfolio
description: Build a freelancer portfolio — for an individual or a small team/collective/agency — tailored to profiles like Software/Full-Stack, AI/ML, AI Integration, Prompt Engineer, Chatbot/Agent, Data Scientist/Analyst, Data Annotator, WordPress/CMS, Mobile, UI/UX, Graphic Design, AI Video, Copywriting, or Virtual Assistant. Creates a personal or team website with role-appropriate services, projects, case studies, metrics, "meet the team" cards, testimonials, and contact info. Use when the user wants to create, design, or update a portfolio, personal or agency site, "about me" / "our team" page, or case-study page for freelance/contract work.
---

# Freelancer Portfolio

Build a polished, role-specific freelancer portfolio. Ask only for what is missing, then generate the deliverable.

## Step 0 — Individual or Team?

First determine the mode:
- **Individual** — one person's portfolio → continue with Step 1 below.
- **Team / Collective / Agency** — a group (e.g. freelancing with friends) showcasing themselves to clients → **read `team/team-guide.md`** and follow it. It still uses the `profiles/` files (one per member) plus team-level sections (Meet the Team, combined services, credited case studies, team stats, "hire the team" CTA).

## Step 1 — Identify the profile

Ask the user which profile fits (or infer it from context). Then **read the matching file in `profiles/` before doing anything else** — it defines the right services, skills, project types, metrics, and tone for that role.

| # | Profile | File |
|---|---|---|
| 1 | Software & Full-Stack Developer | `profiles/software-fullstack.md` |
| 2 | AI & Machine Learning Engineer | `profiles/ai-ml-engineer.md` |
| 3 | AI Integration Specialist | `profiles/ai-integration.md` |
| 4 | Prompt Engineer & Optimizer | `profiles/prompt-engineer.md` |
| 5 | AI Chatbot & Agent Developer | `profiles/ai-chatbot-agent.md` |
| 6 | Data Scientist | `profiles/data-scientist.md` |
| 7 | Data Analyst | `profiles/data-analyst.md` |
| 8 | AI Data Annotator & Labeler | `profiles/ai-data-annotator.md` |
| 9 | WordPress & CMS Developer | `profiles/wordpress-cms.md` |
| 10 | Mobile App Developer | `profiles/mobile-app.md` |
| 11 | UI/UX & Web Designer | `profiles/ui-ux-web-design.md` |
| 12 | Graphic Designer & Illustrator | `profiles/graphic-designer.md` |
| 13 | AI Video Creator & Editor | `profiles/ai-video-creator.md` |
| 14 | Copywriter & Technical Writer | `profiles/copywriter-technical-writer.md` |
| 15 | Virtual Assistant & Admin | `profiles/virtual-assistant.md` |

If none fit, use `profiles/software-fullstack.md` as a base and adapt.

## Step 2 — Gather the essentials

Collect (ask concisely, accept partial answers). The profile file lists what matters most for this role:
- **Name & title** — e.g. "Avinash · Backend Engineer"
- **Services / skills** — pull the profile's suggested list, confirm/edit with the user
- **Featured projects / case studies** — 2–5 items: title, one-line outcome, role, tools, link
- **Metrics & proof** — the profile file specifies which numbers to highlight (e.g. latency, model accuracy, CSAT)
- **Testimonials** — quote + attribution (optional)
- **Contact** — email + role-relevant links (GitHub, LinkedIn, Dribbble, Behance, Kaggle, etc.)
- **Style** — light/dark, accent color, tone (the profile file suggests a default)

## Step 3 — Choose the format

- **Single-file website** (default) — one self-contained `index.html` with inline CSS. Responsive, opens directly in a browser. No install needed.
- **Frontend framework build** — a full React/Vite (+ Tailwind) project for a richer, component-based, animated portfolio. Requires installing frontend tooling — see Step 3a.
- **Markdown profile** — for a GitHub README or simple doc.
- **PDF-ready one-pager** — printable, resume-style.

## Step 3a — Install the frontend tooling (only for the framework build)

Skip this if the user chose the single-file website. If they want a framework build, first confirm Node.js is available, then scaffold the project.

1. **Check prerequisites:**
   ```bash
   node -v && npm -v
   ```
   If Node is missing, tell the user to install it from https://nodejs.org (LTS) and stop until it's available.

2. **Scaffold a Vite + React project** (in the target directory):
   ```bash
   npm create vite@latest portfolio -- --template react
   cd portfolio
   npm install
   ```

3. **Install the frontend packages** used to build the portfolio UI (Tailwind v4 uses a Vite plugin — no `init` step):
   ```bash
   npm install tailwindcss @tailwindcss/vite   # styling (v4)
   npm install framer-motion                    # animations / transitions
   npm install lucide-react                     # icons
   ```
   Then wire up Tailwind v4:
   - In `vite.config.js`, add the plugin: `import tailwindcss from '@tailwindcss/vite'` and put `tailwindcss()` in `plugins`.
   - At the top of `src/index.css`, add `@import "tailwindcss";` (define custom colors/fonts in an `@theme { … }` block).

4. **Run the dev server** so the user can preview live:
   ```bash
   npm run dev
   ```

5. **Build for production** when ready to deploy:
   ```bash
   npm run build      # outputs static files to dist/
   ```

Only run install commands after the user confirms — package installs modify their machine.

## Step 3b — Use the `frontend-design` skill for the visual direction

For **any** build (single-file or framework), first load the **`frontend-design`** skill and follow it — it drives distinctive, non-templated visual design (palette, typography, layout, a signature element grounded in the subject).

- If it isn't installed, offer to add it:
  ```bash
  npx skills add https://github.com/anthropics/skills --skill frontend-design
  ```
- Ground the design in the freelancer's real world (their projects, tools, domain) — e.g. an AI/backend engineer's site can use a systems/schematic motif.
- Avoid the templated defaults the skill warns about (cream-serif-terracotta, near-black + acid accent, gradient big-number stat tiles, decorative 01/02/03 markers) unless the brief explicitly asks for them.

## Step 4 — Build

Adapt section order to the profile (each profile file gives its recommended emphasis). Baseline order:
**Hero → About → Services → Projects/Case Studies → Metrics → Testimonials → Contact**

Requirements:
- Follow the **`frontend-design`** skill's plan (Step 3b) for palette, type, and the signature element.
- Mobile-first, responsive (flexbox/grid, `max-width` container).
- Accessible: semantic HTML, alt text, sufficient contrast, keyboard-focusable links, `prefers-reduced-motion` respected.
- Real content from Step 2; clearly-labeled placeholders only where info is missing.
- **Single-file build:** no external dependencies — inline all CSS; web-safe or `<link>`-loaded fonts.
- **Framework build:** break the page into components (`Hero`, `TeamCard`, `Services`, `CaseStudy`, `Contact`, …), style with Tailwind v4 (`@theme` tokens), add tasteful Framer Motion entrance/scroll animations.

## Step 5 — Deliver & iterate

- Write file(s) to the user's chosen location (default: current working directory).
- Say how to preview (open the HTML in a browser, or run `npm run dev` for a framework build).
- Offer next steps from the profile file (portfolio platforms, deploy targets, what to add next).
- For a hosted, shareable page, offer to publish as an Artifact instead of a local file.
- After every edit, run `npm run build` (framework build) to catch errors before telling the user it's ready.

## Step 6 — Proficiency patterns (reusable techniques)

Battle-tested patterns for a high-quality build. Apply what fits.

### Source real content — don't invent it
- If the user has a **resume/CV (PDF)**, read it and pull real roles, companies, metrics, and projects verbatim.
- If they give a **GitHub repo/profile URL**, fetch it (README + `requirements.txt`/`package.json`) to describe projects accurately — real stack, not guesses.
- If they give a **demo/artifact URL**, offer to either link it or embed its content in-site (host the HTML under `public/demos/` and load via iframe; strip any external iframe-runtime `<script>` first).
- Mark everything still unknown as an obvious `[bracketed]` placeholder + a visible draft note; fill them as the user supplies details.

### Light/dark theme toggle (framework build)
- Define palette as CSS-variable tokens in `@theme`, then override them under `[data-theme="dark"]` so every utility recolors automatically. Include theme-aware `--color-surface` tokens for translucent cards (never hardcode `bg-white`).
- Toggle via React state → `document.documentElement.dataset.theme`, persisted to `localStorage`, defaulting to `prefers-color-scheme`.
- Re-check hardcoded colors (`bg-white`, `text-white` on `bg-ink`, SVG `fill="#fff"`) — they break in the opposite theme.

### Photos & logos
- **Member/person photos:** drop image files in `public/`, reference by `/name.png`; render round/rounded with `object-cover` and a fallback to initials when absent.
- **Company logos** ("worked at"): render as chips with the real logo via `https://www.google.com/s2/favicons?domain=<domain>&sz=64` + the company name. Note they load at runtime (need network) and are low-res; offer crisp self-hosted SVGs as an upgrade.

### Projects / case studies
- Give each project an optional `demo` link + `demoLabel` (e.g. "View on GitHub", "Live demo") rendered as a button only when present.

### Copywriting (make it convincing, not templated)
- Avoid tired credibility clichés — "battle-tested", "enterprise-tested", "ninja", "rockstar". Prefer specific, active phrasing ("Shipped systems at", "Proven at scale", "Serving 134M+ users").
- Labels above logos should read *into* the content ("Shipped systems at" → logos).
- Keep eyebrows meaningful; drop them if they don't add information (users often ask to remove decorative `// LABEL` eyebrows).
- A short, opinionated positioning line lands well (e.g. "Looking for hard, complex problems worth solving").

### Iterate fast
- The user will request many small, specific tweaks (remove an eyebrow, rename a label, add a link, swap a photo). Make the change surgically, rebuild, and confirm — don't re-architect.
