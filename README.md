# important-prompts

I use this repository to store the **most important system prompts** I rely on across projects — the ones worth versioning, reusing, and keeping stable over time.

This is not a dump of every prompt I ever wrote. Only prompts that materially shape how an agent or workflow behaves belong here.

## What's inside

| Path | Description |
|------|-------------|
| [`prompts/hiring_expert_system_prompt.md`](prompts/hiring_expert_system_prompt.md) | IT hiring advisor — CV analysis, Germany market, shortcuts, human voice + XYZ bullet rules |
| [`prompts/personal_branding_expert_system_prompt.md`](prompts/personal_branding_expert_system_prompt.md) | Personal branding strategist + portfolio/blog builder — CV-driven design, advisory and build modes |

---

## 1. Hiring Expert

**Role:** Senior IT hiring advisor for CV review, Germany market positioning, and interview prep.

**Default market:** Germany (2025–2026) — Data Engineering, Backend, DevOps, Cloud, AI/ML, Solutions Architect tracks.

### Shortcuts

| Shortcut | Purpose | Output (local project) |
|----------|---------|------------------------|
| `/analyse` | Full profile analysis + Germany market comparison | `reports/profile_analysis_*.pdf` |
| `/improve` | Before/after CV fixes | `improvements/cv_improvements_*.md` + `.pdf` |
| `/interview` | Strict recruiter mock interview | `interview_simulation/interview_sim_*.pdf` |
| `/market [arg]` | Deep Germany job market brief for requested domain | `market/[Field]_Market_YYYY-MM-DD.pdf` |
| `/add` | Add cert, role, project, or skill | `cv_additions/cv_addition_*.md` + `.pdf` |

### Key rules

- Human voice — no robotic AI buzzwords
- Google **XYZ formula** for bullets: outcome + metric + method
- Never invent experience; conservative metrics when unknown
- Germany market alignment on every analysis

Full behaviour: [`prompts/hiring_expert_system_prompt.md`](prompts/hiring_expert_system_prompt.md)

---

## 2. Personal Branding & Online Portfolio Expert

**Role:** Senior personal-branding strategist and full-stack portfolio builder. Turns expertise into a credible, discoverable online presence — blogs, portfolios, and content hubs.

**Core question every recommendation answers:** *Does this make this person more credible, discoverable, and memorable?*

### CV-driven workflow

When a CV is uploaded (PDF, DOCX, or pasted text), the agent:

1. **Extracts** — role, skills, experience, projects, education, implicit industry signals
2. **Decides** — project-focused vs niche specialist vs generalist vs creative vs academic layout
3. **Gets inspired** — tagline, sections, visual tone, colors, blog topics all derived from the CV
4. **Presents a plan** — positioning, site structure, design direction, gaps to fill

Never invents roles or achievements not on the CV.

### Two modes

| Mode | When | What you get |
|------|------|--------------|
| **Advisory** | Ideas, strategy, feedback | Brand audit, taglines, content pillars, portfolio structure, blog topics |
| **Build** | "Create my portfolio/blog" | Full deployable site (Next.js, Astro, etc.) — not wireframes |

### Design philosophy

- **No generic templates** — no cookie-cutter hero + three cards + footer
- Purpose-built per profession, seniority, and industry
- Distinctive typography, layout, motion, color
- Mobile-first, accessible, fast, SEO basics (Open Graph, sitemap)

### Hosting recommendations (tiered)

| Tier | Options | Cost |
|------|---------|------|
| Free | Vercel, Netlify, Cloudflare Pages, GitHub Pages | $0 |
| Free + domain | Above + Namecheap/Porkbun | ~$10–15/yr |
| Low-cost CMS | Sanity/Contentful + Vercel | $0–20/mo |
| Budget VPS | Hetzner, DigitalOcean, Linode | ~$4–6/mo |

**Default:** static site on Vercel or Cloudflare Pages + custom domain.

### What it covers

- Positioning, content pillars, credibility (metrics, certs, timeline)
- Blog structure (MDX/Markdown, tags, RSS)
- Portfolio sections: hero, about, projects, experience, articles, contact
- Deploy guidance after every build

Full behaviour: [`prompts/personal_branding_expert_system_prompt.md`](prompts/personal_branding_expert_system_prompt.md)

---

## How I use this repo

1. Copy a prompt into **Cursor rules** (`.cursor/rules/`), **Custom GPT** instructions, or an API `system` message.
2. Keep project-specific assets (CV, reports, built sites) **local** — not in this repo.
3. When a prompt changes meaningfully, commit and push so all environments stay in sync.

### Cursor setup (example)

```
.cursor/rules/hiring-expert.mdc      → points to hiring_expert_system_prompt.md
.cursor/rules/personal-branding.mdc  → points to personal_branding_expert_system_prompt.md
```

---

## License

Personal use. Adapt freely for your own career and branding tooling.
