# Contributing

Contributions are welcome — especially **new freelancer profiles** and improvements to the build patterns.

## Add a new profile

1. Create `freelancer-portfolio/profiles/<your-profile>.md`. Copy an existing profile and keep the same section schema:
   - **Suggested services** — what this role offers
   - **Core skills** — the right tools/tech
   - **Case-study framing** — how to present their work
   - **Metrics to highlight** — the numbers that matter for this role
   - **Portfolio emphasis** — recommended section order / what to lead with
   - **Links & platforms** — where this role publishes
   - **Default style** — a sensible palette/tone starting point
2. Register it in the profile table in `freelancer-portfolio/SKILL.md`.
3. Keep it concise and specific — the value is role-tailored guidance, not generic advice.

## Improve the workflow

- `freelancer-portfolio/SKILL.md` — the main flow (individual vs team, build steps, "Step 6" proficiency patterns).
- `freelancer-portfolio/team/team-guide.md` — the team/agency showcase guide.

## Guidelines

- Match the existing tone and structure; small, focused PRs are easiest to review.
- Don't hardcode any one person's details — profiles are templates.
- Prefer real, specific guidance over filler.

## Test locally

Copy the skill into your Claude skills dir and try it:

```bash
cp -R freelancer-portfolio ~/.claude/skills/freelancer-portfolio
```

Then run `/freelancer-portfolio` in Claude Code, or ask it to build a portfolio for the profile you added.
