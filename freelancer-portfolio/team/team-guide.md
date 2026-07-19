# Team / Collective Portfolio Guide

Build a portfolio that showcases a small freelance team (2–4 people) to potential clients — one site that sells the group, not just one person. Use this when the user says they freelance *with friends / a team / a collective / an agency*.

## Step T1 — Gather team info

Ask concisely:
- **Team name & tagline** — e.g. "Nova Collective · We build AI products for early-stage startups"
- **What the team does together** — one-line pitch and target client
- **Members** (2–4) — for each: name, role/profile (map to one of the 15 individual profiles), 3–5 key skills, photo (optional), links (GitHub/LinkedIn/Dribbble/etc.)
- **Combined services** — the union of services across members (dedupe overlaps)
- **Team case studies** — 2–4 projects: outcome + **who did what** (credit each member)
- **Team stats** — combined years of experience, projects delivered, clients served, tech covered
- **Proof** — client testimonials, notable clients/logos
- **Contact** — one "hire the team" CTA (email / form / Calendly)
- **Style** — accent color + light/dark (pick one shared brand look)

For each member, **read that member's individual profile file** (`profiles/<x>.md`) to pull the right skills, services, and terminology.

## Step T2 — Recommended section order

**Team Hero → What We Do → Meet the Team → Combined Services → Case Studies (with credits) → Why Hire Us → Team Stats → Testimonials/Clients → Contact (Hire the Team)**

## Step T3 — Build notes (2–4 person layout)

- **Meet the Team** = a responsive card grid. With 2–4 people, feature everyone prominently (large cards, 2-up or 3-up grid). Each card:
  - Photo (or initials avatar placeholder) · Name · Role/title
  - 3–5 skill chips · one-line bio · social links
- **Case studies** should credit members by name/role ("Backend & AI by Avinash, UI by Sara") — this is what makes a team portfolio convincing.
- **Team stats** as a row of tiles (e.g. "3 members · 40+ projects · 5+ yrs combined · 12 clients").
- Keep ONE shared brand: single accent color, consistent type scale, unified card style — the team should look cohesive, not like 3 different portfolios stitched together.
- **Combined services**: merge each member's `profiles/<x>.md` service list, remove duplicates, group logically (e.g. "Design", "Development", "AI").

## Step T4 — Deliver

- Same formats as individual (single-file HTML default, or framework build).
- Offer a "hire the team" CTA and, optionally, per-member deep-link to their individual portfolio.
- For a shareable link to send clients, offer to publish as an Artifact.

## Proven team-build techniques

Learned patterns that make a team site convincing (see the main SKILL.md "Step 6" for the full list):

- **Real content per member:** read each person's resume/CV and GitHub (repo README + deps) to fill their card and credit real projects — don't invent skills or metrics.
- **Member photos:** put each headshot in `public/` and render round with `object-cover`, falling back to initials when a photo is missing. Ask for each member's photo.
- **"Shipped systems at" logo row:** under each member, show the companies they worked at as logo chips (`https://www.google.com/s2/favicons?domain=<domain>&sz=64` + name). This is strong social proof for a small team.
- **Credited projects:** the team's case studies can note who led each one — but only if the user wants it (some prefer no per-project names). Attach `demo`/GitHub links per project when available.
- **Combined "worked at" hero strip:** a single row merging every member's companies (Google · eBay · Oracle · Microsoft · …) is one of the most persuasive elements — lead with it.
- **"Connect with us" block:** near the contact CTA, list each member with their GitHub/LinkedIn/email so a client can reach either person directly.
- **One shared brand + theme:** single accent, one type scale, and a light/dark toggle (CSS-variable tokens overridden under `[data-theme="dark"]`). The team must look cohesive, not like stitched-together individual sites.
- **Confident, specific copy:** avoid "battle-tested/enterprise-tested" clichés; use active, concrete phrasing. A positioning line like "Looking for hard, complex problems worth solving" reads well for a senior team.

## Member card — reference snippet (single-file HTML)

```html
<article class="member-card">
  <img class="avatar" src="" alt="Member name">
  <h3>Member Name</h3>
  <p class="role">AI & ML Engineer</p>
  <ul class="chips"><li>Python</li><li>PyTorch</li><li>LLMs</li></ul>
  <p class="bio">One-line bio.</p>
  <div class="links"><a href="#">GitHub</a> · <a href="#">LinkedIn</a></div>
</article>
```
Style `.member-card` in a responsive grid: `display:grid; grid-template-columns:repeat(auto-fit,minmax(240px,1fr)); gap:1.5rem;`
