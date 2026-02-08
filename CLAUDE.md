# Personal Resume & Blog — Taoufiq Lotfi

This repo contains all personal brand content for Taoufiq Lotfi — resume files in multiple formats and blog posts for publishing on his personal blog. No code to build or run — this is a content repo.

## Author Context

**Taoufiq Lotfi** — Moroccan developer, born 1996. Currently **CTO at Veedoo** (European digital consultancy) and **Founding Engineer at Baseloop** (startup, part-time). Based remotely (Morocco/Moldova). 10+ years experience: freelance Android dev in Morocco (2014-2017) → React Native in Ukraine (2017-2019) → full stack at Veedoo (2019-present) → CTO (2025). Key projects: EUvsDisinfo (EU platform, 13 languages), ParliamentConnect (ML video pipeline), EveryRun (solo-scaled to 17K users), Ukraine Shelter (built in 3 days during the 2022 invasion), Lifeline Ukraine (suicide prevention). Strong advocate for self-hosting (Coolify + Hetzner Cloud) and architecture-first thinking (HLD/LLD) in the AI era.

## File Structure

### Root — Resume Files

The resume exists in a pipeline of increasing polish:

| File | Purpose |
|------|---------|
| `resume.md` | **Raw resume** — year-by-year narrative with all details. Source of truth. |
| `resume-elaborated.md` | **Elaborated version** — same structure but with deep technical detail (tech stacks with versions, architecture deep-dives, code-level specifics). For technical audiences. |
| `resume-marketing.md` | **Recruiter-optimized** — concise, impact-focused, bullet-point format. This is what gets sent to recruiters and HR. ~115 lines. |
| `resume.html` | **HTML version** — self-contained HTML with professional CSS styling, generated from `resume-marketing.md`. Used to produce the PDF. |
| `resume-taoufiq-lotfi.pdf` | **Final PDF** — 2-page A4 PDF exported from `resume.html` via Playwright. The file that actually gets sent out. |
| `resume-preview.png` | Screenshot preview of the PDF resume. |

**When updating the resume:** Start with `resume.md` (raw truth), then propagate changes to `resume-elaborated.md`, then `resume-marketing.md`, then regenerate `resume.html` and the PDF.

### `blog-posts/` — Blog Posts

#### 5-Part Career Series (chronological)

Published in this order — each can stand alone but together they tell the full career story:

| # | File | Title | ~Words |
|---|------|-------|--------|
| 1 | `01-moroccan-developer-journey.md` | A Moroccan Developer's Journey — From Android Apps to React Native in Ukraine | 1,200 |
| 2 | `02-veedoo-part-1-war-humanitarian-tech.md` | From Morocco to Ukraine to CTO — My First 4 Years at Veedoo (2019-2022) | 2,200 |
| 3 | `03-everyrun-solo-developer.md` | How I Scaled a Running Platform from 80 to 17,659 Users as the Only Developer | 1,800 |
| 4 | `04-veedoo-part-2-ai-selfhosting-cto.md` | From Lead Dev to CTO — How AI and Self-Hosting Changed Everything (2023-2026) | 2,500 |
| 5 | `05-baseloop-founding-engineer.md` | Joining a Startup as Founding Engineer — My Baseloop Story | 1,800 |

#### 2 Standalone Deep-Dives

Loosely connected to the career series but topic-focused:

| # | File | Title | ~Words |
|---|------|-------|--------|
| 6 | `06-why-i-self-host-everything.md` | Why I Self-Host Everything Now — And Why You Should Too | 2,500 |
| 7 | `07-parliamentconnect-ml-pipeline-architecture.md` | How I Built an ML Pipeline That Identifies Politicians with 98% Accuracy — Solo | 2,800 |

### `docs/brainstorms/` — Planning Documents

| File | Purpose |
|------|---------|
| `2026-02-08-blog-posts-brainstorm.md` | Brainstorm for the 5-part career series. Contains all Q&A answers, story arcs, hooks, technical insights, and cross-cutting themes gathered during planning. |
| `2026-02-08-selfhosting-and-parliamentconnect-brainstorm.md` | Brainstorm for posts 6 and 7. Includes real cost comparisons (Supabase/Trigger.dev SaaS vs Hetzner self-hosted), pipeline architecture details, and design decisions. |

### Other Files

| File | Purpose |
|------|---------|
| `.gitignore` | Ignores `.playwright-mcp/` directory (used for PDF generation). |
| `.claude/settings.local.json` | Local Claude Code settings for this project. |

## Writing Conventions

- **Tone:** Mix of personal storytelling and technical insights. Conversational, not formal. Written as Taoufiq today (age 29/30) looking back.
- **Perspective:** First person. Short paragraphs. Lead with the story, weave in tech naturally.
- **Vulnerability:** Balanced — mention real challenges without oversharing.
- **Length:** Career posts: 1,200-2,500 words. Deep-dives: 2,500-3,000 words.
- **CTAs:** Each post ends with personal reflection/lessons + links to repos/profiles + invitation for readers to connect.
- **Links:** GitHub (tao101), LinkedIn (taoufiqlotfi), Website (taoufiqlotfi.com), Baseloop (baseloop.io).
- **No emojis** unless explicitly requested.
