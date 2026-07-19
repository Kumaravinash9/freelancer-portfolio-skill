# freelancer-portfolio — Claude skill

A [Claude](https://claude.com/claude-code) skill that builds a polished **freelancer or team/agency portfolio** — tailored to the profile, grounded in real content, and designed to actually convince clients.

It supports **individual** portfolios and small **team/collective** showcases, across 15 popular freelance profiles, and pairs with Anthropic's `frontend-design` skill for a distinctive (non-templated) look.

## What it does

- **Asks individual or team**, then follows the right flow.
- **15 profiles**, each with role-specific services, skills, case-study framing, metrics, and links:
  Software/Full-Stack · AI/ML Engineer · AI Integration · Prompt Engineer · Chatbot/Agent · Data Scientist · Data Analyst · Data Annotator · WordPress/CMS · Mobile · UI/UX · Graphic Design · AI Video · Copywriting · Virtual Assistant.
- **Team mode** — "meet the team" cards, combined services, credited case studies, a merged "worked at" logo strip, and a "hire the team" CTA.
- **Two build formats** — a zero-dependency single-file `index.html`, or a full **React + Vite + Tailwind v4 + Framer Motion** project.
- **Proficiency patterns** — sources real content from resumes / GitHub repos, light/dark theming, member photos, company logos, anti-cliché copywriting.

## Install

### Option A — with the `skills` CLI (recommended)

```bash
npx skills add https://github.com/Kumaravinash9/freelancer-portfolio-skill --skill freelancer-portfolio
```

### Option B — manual (Claude Code)

Clone into your Claude skills directory:

```bash
# personal (all projects)
git clone https://github.com/Kumaravinash9/freelancer-portfolio-skill.git /tmp/fps \
  && cp -R /tmp/fps/freelancer-portfolio ~/.claude/skills/freelancer-portfolio

# — or project-scoped (shared via git) —
cp -R /tmp/fps/freelancer-portfolio .claude/skills/freelancer-portfolio
```

## Use

- Type `/freelancer-portfolio` in Claude Code, **or**
- Just ask: *"build me an AI/ML freelancer portfolio"* / *"make a portfolio for my freelance team"* — it triggers automatically.

## Example built with this skill

**InnoAI Labs** — a two-person AI/backend team portfolio built in team mode (React + Vite + Tailwind + Framer Motion): animated hero schematic, "meet the team" cards, credited case studies, and a company logo strip.

- Source: https://github.com/Kumaravinash9/portfolio-web

## Structure

```
freelancer-portfolio/
├── SKILL.md              # main workflow (individual vs team, build steps, patterns)
├── profiles/             # 15 role-specific reference files
└── team/team-guide.md    # team/agency showcase guide
```

## License

MIT
