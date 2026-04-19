# Portfolio — Pages & Sections (Information Architecture)

> **Scope.** This document is the **IA / content map** for the portfolio at `taoufiqlotfi.com`. It defines *which pages the site has*, *which sections each page has*, *what each section is trying to do*, and *what each section contains*.
>
> **Out of scope here.** Visual design, typography, colors, motion, layout — all of that lives in `../design.md` and must be read alongside this file. Author context, tone, and source content live in `../CLAUDE.md`.
>
> **Why this file exists.** The landing page has to work for three very different readers (startup founders, technical recruiters, in-house HR) in three very different scan depths (2–5 min, 30 sec, 20–60 sec). `../design.md` §1 names the audiences; this document translates that into a concrete page/section list that later design passes can style one section at a time.

---

## Audiences (summary — full version in `../design.md` §1)

1. **Startup founders (Seed – Series A)** — 2–5 min scan. Looking for a fractional CTO / founding engineer / senior contractor. Need to believe in 2 minutes that Taoufiq ships solo, has architectural judgment, and is cost-aware.
2. **Technical recruiters** — 30 sec scan. Need years, title, stack, location, availability, and a copy-pasteable email.
3. **In-house HR (ATS-assisted)** — 20–60 sec scan. Need keyword density and clear titles/dates. No forms.
4. **Engineers evaluating collaboration** (secondary) — read the blog and the open source.

---

## Site map (v1)

Seven routes total. Everything not listed here is explicitly out of scope (see `../design.md` §18).

1. `/` — **Landing page** (does ~90% of the conversion work)
2. `/work` — **Work index** (all projects in a scannable grid)
3. `/work/[slug]` — **Case study detail** (one template, parameterized per project)
4. `/blog` — **Blog index**
5. `/blog/[slug]` — **Blog post**
6. `/about` — **Long bio / values / now page**
7. `/uses` *(optional, v1.1 — can ship later)*

Plus non-UI artifacts the spec requires: `sitemap.xml`, `robots.txt`, `rss.xml`, per-page Open Graph images, and a `404` page.

---

## 1. `/` — Landing page

The landing page is a **stratified read**: the top of the page satisfies the 30-second recruiter, the middle rewards the 2-minute founder, and the bottom carries the ATS keyword pass. Sections are ordered to that gradient.

### 1.1 Hero

- **Goal.** Pass the 30-second recruiter bar and hook the 2-minute founder. Communicate *who*, *what*, and *why trust me* before the first scroll.
- **Contents.**
  - Name: "Taoufiq Lotfi".
  - One-line positioning: "Full stack developer & CTO. I ship AI-powered products solo."
  - Location + availability line: "Morocco / Moldova — Remote, available for contracts."
  - 3 proof-stat chips: `98% accuracy` (ParliamentConnect ML), `17,659 users` (EveryRun, solo), `10+ years` (experience).
  - Primary CTA: "Hire me" (mailto with pre-filled subject).
  - Secondary CTA: "See what I've built" (scroll-anchor to the featured case study).

### 1.2 What I can build for you

- **Goal.** Let a founder self-identify the engagement shape in under 15 seconds. Removes the "what exactly is he selling?" friction.
- **Contents.** Three role cards, one short paragraph each (no bullets inside the cards):
  1. **Fractional CTO** — for seed / Series A founders who need architectural judgment, hiring decisions, and tech strategy without a full-time hire.
  2. **Founding engineer** — for early startups where the CEO needs one senior engineer to own product end-to-end (current Baseloop framing).
  3. **Senior full-stack contractor** — project-scoped delivery on AI products, self-hosted infrastructure, or complex migrations.
- Each card ends with a soft link ("Typical engagement →") pointing either to the final CTA or to a relevant case study.

### 1.3 Featured case study — ParliamentConnect

- **Goal.** Deliver the single strongest technical proof point on the page. This is the one case study that earns full width; it's the read a 2-minute founder will actually finish.
- **Contents.**
  - *Problem* (1–2 sentences): parliamentary sessions are long, unsearchable, and hard to attribute to individual MPs.
  - *Approach* (3–4 sentences): speaker diarization + face recognition + Whisper + GPU pipeline on RunPod (NVIDIA RTX PRO 6000).
  - *Headline metric*: 98% accuracy; 2–8 hour sessions processed in 30–45 minutes.
  - *Tech stack chips*: Python, PyTorch, CUDA, pgvector, Whisper, RunPod.
  - *What made it hard* (1 sentence): built solo, production from day one.
  - *Link*: "Read the deep dive →" → `/blog/parliamentconnect-ml-pipeline-architecture` (source: `../blog-posts/07-parliamentconnect-ml-pipeline-architecture.md`).

### 1.4 Supporting case studies

- **Goal.** Show breadth. Prove range (scale, humanitarian, EU-scale) at a glance without padding the page.
- **Contents.** Two compact cards in a row:
  - **EveryRun** — "Scaled a running platform from 80 to 17,659 users as sole developer." Tech: Next.js, Drizzle, Neon, Stripe. Link → `/blog/everyrun-solo-developer` (source: `../blog-posts/03-everyrun-solo-developer.md`).
  - **EUvsDisinfo** — "Led the EU-funded disinformation platform: 19,000 documented cases, 13 languages, millions of annual users." Tech: Sanity v3, Next.js, TypeScript. Link → `/blog/veedoo-part-1-war-humanitarian-tech` or part 2 (sources: `../blog-posts/02-veedoo-part-1-war-humanitarian-tech.md`, `../blog-posts/04-veedoo-part-2-ai-selfhosting-cto.md`).
- Footer link: "All work →" → `/work`.

### 1.5 How I work

- **Goal.** Inoculate against the "is this a code-slinger or a thinker?" doubt. Shows taste and architectural judgment without being preachy.
- **Contents.** 3–4 short principle statements; each is one sentence + one concrete example:
  - *Architecture before code.* HLD/LLD first, even for small projects — it's what AI tools can't replace.
  - *Self-hosting by default.* Coolify + Hetzner. Predictable costs, data residency, no rate limits.
  - *Human-in-the-loop AI.* OptiGen builds dossiers; humans write the outreach. Genuine beats "slop".
  - *Ship under pressure.* Ukraine Shelter went live 3 days into the 2022 invasion.

### 1.6 Skills strip (ATS-friendly)

- **Goal.** Pass the 20-second HR keyword scan and the ATS parser. Dense, scannable, no prose, plain DOM text.
- **Contents.** The exact taxonomy from `../resume-marketing.md`, preserved verbatim, one category per row:
  - **Languages** — TypeScript, JavaScript, Python, PHP, Java, SQL, HTML, CSS.
  - **Frontend** — React, Next.js (SSR/SSG/ISR/Server Actions), React Native, Expo, Tailwind CSS, Shadcn UI.
  - **Backend** — Node.js, Express, NestJS, Next.js API Routes, Python (ML pipelines).
  - **Databases** — PostgreSQL, MongoDB, Supabase (hosted & self-hosted), Neon, Drizzle ORM, MySQL.
  - **AI / ML** — OpenAI GPT API, RAG pipelines, Embeddings, PyTorch, CUDA, Whisper, Speaker Diarization, Face Recognition, pgvector.
  - **Infrastructure** — Docker, Coolify, Vercel, Hetzner Cloud, RunPod, Traefik, Nginx, n8n, Trigger.dev.
  - **Payments** — Stripe, Stripe Connect.
  - **CMS** — Sanity (v2 & v3), Jamstack.
  - **Testing & Analytics** — Playwright, Jest, PostHog, Sentry.
  - **Tools** — Git, Claude Code, Cursor IDE, MCP (Model Context Protocol).

### 1.7 About (short)

- **Goal.** Humanize after the proof. The 2-minute founder reads this; the 30-second recruiter scrolls past.
- **Contents.**
  - One first-person paragraph: Moroccan developer, 10+ years, Morocco → Ukraine → Moldova, CTO at Veedoo, Founding Engineer at Baseloop. Same voice as the blog.
  - Optional one-liner on values (self-hosting, architecture-first).
  - Link: "Read the full story →" → `/blog/moroccan-developer-journey` (source: `../blog-posts/01-moroccan-developer-journey.md`) *and* `/about`.

### 1.8 From the blog

- **Goal.** Prove writing ability and technical depth. Third-party legitimacy for engineer-evaluators without paid-for social proof.
- **Contents.** 3 hand-picked post cards (default pick: the ParliamentConnect deep-dive, the self-hosting post, the EveryRun story). Each card: tag, title, 1-line description, read time + date.
- Footer link: "All posts →" → `/blog`.

### 1.9 Final CTA

- **Goal.** Close the loop. After the full scroll, a founder who is 80% convinced needs a last, friction-free prompt.
- **Contents.**
  - Headline: "The fastest way to work with me is email. I reply within 24 hours."
  - Primary button: "Email me" (mailto with pre-filled subject).
  - Secondary button: "Book a 30-min intro call" → Cal.com (stub for now, wire later).
  - No form, no newsletter, no capture.

### 1.10 Footer

- **Goal.** Minimal close. Contact shortcuts + site self-disclosure (the "built with" line is itself a proof point for the self-hosting story).
- **Contents.**
  - Contact row: email, GitHub (tao101), LinkedIn (taoufiqlotfi), website.
  - "© {year} Taoufiq Lotfi."
  - "Built with Next.js · self-hosted on Coolify + Hetzner."

---

## 2. `/work` — Work index

### 2.1 Page header

- **Goal.** Frame the page and set expectations — this is the portfolio proper, not a résumé list.
- **Contents.** H1 "Work", one-line subhead ("Selected projects from 10+ years shipping AI, web, and mobile products"), optional filter chip row by tag (*AI/ML · Platform · Humanitarian · Infrastructure · Mobile*) with a "Clear filter" affordance when active.

### 2.2 Project grid

- **Goal.** Let a visitor scan every project in under 60 seconds and click into the one that matches their need.
- **Contents.** One card per project, ordered by impact (not chronology):
  1. **ParliamentConnect** — ML video pipeline, 98% accuracy.
  2. **EveryRun** — solo-scaled to 17,659 users.
  3. **EUvsDisinfo** — EU platform, 13 languages, 19,000+ cases.
  4. **Ukraine Shelter** — 3-day humanitarian launch (2022).
  5. **Lifeline Ukraine** — national suicide prevention hotline.
  6. **OptiGen** — AI CRM / lead-generation, human-in-the-loop.
  7. **Baseloop** — founding engineer, fully self-hosted stack.
  8. **Open source** — self-host templates, `supabase-sync` CLI, Coolify Trigger.dev configs.
- Each card contains: tag chip, title, 1-line outcome with the headline metric, tech-stack chips, link → `/work/[slug]` (or direct GitHub for open source).

### 2.3 Not-shown note

- **Goal.** Pre-empt the "is this everything?" question; offer a shortcut for niche needs.
- **Contents.** One line: "A handful of client projects are under NDA. Ask me directly for references." + email link.

---

## 3. `/work/[slug]` — Case study detail

One template, parameterized per project. Launch with full case studies for **ParliamentConnect**, **EveryRun**, and **EUvsDisinfo**; others can be stubs that link to the relevant blog post until they're written.

### 3.1 Hero

- **Goal.** Recruiter / founder orientation in 10 seconds.
- **Contents.** Role, year range, company context, one-line project summary, primary headline metric.

### 3.2 The problem

- **Goal.** Anchor the reader in *why this project existed* so a non-technical reader can still follow.
- **Contents.** 1–3 short paragraphs. Who the user was, what hurt, what the prior state looked like.

### 3.3 What I built

- **Goal.** Show the solution at a product level before going technical.
- **Contents.** 2–4 paragraphs + optional UI screenshot or architecture diagram placeholder. End with a one-line user-facing outcome ("MPs now searchable by name across every session").

### 3.4 How it works (technical)

- **Goal.** Give the engineer-evaluator enough substance to trust the work.
- **Contents.**
  - Architecture overview — one labeled diagram *or* a short bulleted data-flow description.
  - Key decisions with rationale: why this DB, why this deployment target, why self-host vs SaaS, why this model, etc.
  - One or two "what I'd do differently" notes. Honesty is the proof.

### 3.5 Impact / results

- **Goal.** Close the case study with numbers.
- **Contents.** 2–4 stat chips with real numbers (accuracy, users, cost, time saved, languages supported). Source each number or name it (company metric, analytics, etc.).

### 3.6 Tech stack

- **Goal.** Quick-scan reference for ATS / HR.
- **Contents.** Flat chip list of the full stack used for this project.

### 3.7 Links & next steps

- **Goal.** Don't dead-end the reader.
- **Contents.** Link to the related blog post (where one exists), link to the live product (if public), and a scoped CTA ("Have a similar problem? Email me →").

### 3.8 Footer CTA

- **Goal.** Same as landing §1.9 — close every page the same way.
- **Contents.** "Email me" primary + "Book a call" secondary.

---

## 4. `/blog` — Blog index

### 4.1 Page header

- **Goal.** Frame the blog — it's writing about work, not a lifestyle journal.
- **Contents.** H1 "Blog", one-line subhead, tag filter row (`career`, `tech`, `infra`, `ML`), "Clear filter" affordance when active.

### 4.2 Post list

- **Goal.** Reverse-chronological scannable list; every row is a clickable link into `/blog/[slug]`.
- **Contents.** Each row: title, one-line description, metadata (`date · readTime · tag`), thin divider between rows. Pagination at the bottom (`Previous / Next`, 10 posts per page) — no infinite scroll.

### 4.3 RSS hint

- **Goal.** Serve serious readers without adding UI noise.
- **Contents.** One small line at the bottom: "RSS: /rss.xml". `<link rel="alternate">` in `<head>` discoverable by readers.

---

## 5. `/blog/[slug]` — Blog post

### 5.1 Post hero

- **Goal.** Set expectations for the read in 3 seconds.
- **Contents.** Tag chip, title, metadata row (`date · readTime · author`).

### 5.2 Body (MDX)

- **Goal.** A focused long-form reading experience.
- **Contents.** MDX-rendered prose, code blocks, inline code, images. Desktop: sticky table of contents on the right (h2/h3, scrollspy). Mobile: collapsible TOC at the top.

### 5.3 Reading progress

- **Goal.** Micro-signal of progress for long reads; subtle, not decorative.
- **Contents.** Top bar that scales with scroll position.

### 5.4 Author footer

- **Goal.** Convert readers into leads at the moment they finish.
- **Contents.** Square photo, one-liner ("CTO at Veedoo. Founding engineer at Baseloop. Based in Morocco / Moldova."), primary CTA "Hire me →", links to GitHub / LinkedIn / Website.

### 5.5 Related posts

- **Goal.** Keep engaged readers on-site.
- **Contents.** Up to 3 cards, picked by shared tag or by an explicit `related:` override in frontmatter.

---

## 6. `/about` — Long bio page

Thin v1 — absorbs anything that would bloat the landing About section. Can grow later.

### 6.1 Intro

- **Goal.** Humanize at full length for readers who clicked past the landing summary.
- **Contents.** Multi-paragraph first-person story: Morocco (2014) → Ukraine (2017) → wartime relocation (2022) → Moldova → CTO (2025). Same tone as blog post 01, but ~400 words condensed.

### 6.2 What I care about

- **Goal.** Surface values, not buzzwords. Distinguishes a senior-hire candidate from a junior.
- **Contents.** 3–4 short paragraphs on architecture-first thinking, self-hosting, human-in-the-loop AI, and shipping under pressure.

### 6.3 Now

- **Goal.** Tell the reader what's current. A "now" section signals a living site, not a stale portfolio.
- **Contents.** 2–3 short lines: "CTO at Veedoo. Founding engineer at Baseloop. Writing about self-hosting and ML pipelines. Available for one more contract engagement in {quarter/year}." Update on every commit that changes status.

### 6.4 Elsewhere

- **Goal.** Cross-link profiles for recruiters who audit across platforms.
- **Contents.** GitHub (tao101), LinkedIn (taoufiqlotfi), Baseloop (baseloop.io), email. No Twitter / X unless actively used.

### 6.5 CTA

- **Goal.** Close every page the same way.
- **Contents.** Same primary CTA block as §1.9.

---

## 7. `/uses` *(optional, v1.1)*

Low conversion value, high credibility among peers. Ship if there is time.

### 7.1 Hardware & environment

- **Goal.** Signal to engineer-evaluators.
- **Contents.** Machine, OS, editor (Cursor + Claude Code + MCP), terminal, shell, font.

### 7.2 Self-hosted stack

- **Goal.** Be the canonical reference for "what does Taoufiq actually run?" — directly ties to the self-hosting blog post.
- **Contents.** Coolify on Hetzner, Supabase self-hosted, Trigger.dev self-hosted, Postiz, n8n, Traefik. Monthly cost ballpark.

### 7.3 Go-to libraries

- **Goal.** Opinion, not an exhaustive list.
- **Contents.** Next.js, Drizzle, Neon (or self-hosted Postgres), Tailwind, Shadcn, PostHog, Sentry, Playwright.

---

## Cross-page concerns

- **Top nav** — present on every page. Links: `Work`, `Blog`, `About`. Theme toggle. Primary CTA button on desktop.
- **Footer** — same on every page (see §1.10).
- **Mobile CTA bar** — present on every page; automatically hidden while any page-level primary CTA is in the viewport.
- **No forms anywhere.** Email (mailto) + Cal.com are the only contact methods.
- **No dead-ends.** Every page ends with a CTA or a forward link.
- **One primary CTA, reused everywhere.** Destination = `mailto:admin@taoufiqlotfi.tech?subject=Hiring%20Taoufiq`.

---

## Content inventory — what exists vs what needs to be written

| Needed | Source today | Gap |
|---|---|---|
| Hero stats (3) | `../resume-marketing.md` summary | None — pick 3. |
| Role cards (§1.2) | Implicit in resume | **Write** — 3 short paragraphs. |
| Featured case study blurb (ParliamentConnect) | `../blog-posts/07-parliamentconnect-ml-pipeline-architecture.md` + resume | **Write** — landing-length condensation. |
| Supporting case study blurbs (EveryRun, EUvsDisinfo) | `../blog-posts/02-…`, `03-…`, `04-…` + resume | **Write** — landing-length blurbs. |
| "How I work" principles (§1.5) | Resume + blog posts | **Write** — 3–4 principle statements. |
| Skills strip (§1.6) | `../resume-marketing.md` §Skills | None — reuse verbatim. |
| About (short, §1.7) | Resume summary + `../blog-posts/01-moroccan-developer-journey.md` | **Write** — 1 paragraph. |
| About (long, `/about`) | `../blog-posts/01-moroccan-developer-journey.md` | Condense/rewrite for portfolio voice. |
| Blog post content | `../blog-posts/*.md` | None — already written (7 posts). |
| Case study detail pages (`/work/[slug]`) | Blog posts + resume | **Write** — at least ParliamentConnect, EveryRun, EUvsDisinfo. |
| Open Graph images | — | Generate at build from `{title, tag}` per `../design.md` §14. |
| Cal.com booking link | — | Create account and wire secondary CTA. |

---

## Verification — checks to run against this IA before implementing

1. **30-second recruiter test.** Starting at `/`, can a recruiter get name, title, location, 3 proof numbers, and a copy-pasteable email without scrolling past the first viewport? If no, §1.1 is wrong.
2. **2-minute founder test.** Can a founder land on `/`, skim role cards (§1.2), read one case study (§1.3), and click into a deep-dive blog post — all in under 2 minutes? If no, the fold order is wrong.
3. **ATS test.** Does §1.6 include every keyword from `../resume-marketing.md` as plain DOM text? Grep the rendered HTML for "TypeScript", "PostgreSQL", "Stripe Connect", etc.
4. **No-dead-end test.** Walk every page top to bottom — does each one end with a CTA or a forward link?
5. **Cross-link coverage.** Every case study card on `/` links to either a blog post or a `/work/[slug]` page, and nothing else. Every blog post ends with a visible `mailto:` in the author footer.
6. **Scope guard.** Nothing on the site violates `../design.md` §18 (no i18n, no comments, no newsletter, no carousels, no 3D, no autoplay video).

---

## References

All paths are relative to this file (`website-plan/portfolio.md`); the siblings below live one level up in the repo root.

- `../design.md` — visual spec (colors, typography, motion, components, performance).
- `../CLAUDE.md` — author context, resume pipeline, blog-post inventory, writing conventions.
- `../resume-marketing.md` — source of truth for skills taxonomy and project metrics.
- `../blog-posts/*.md` — 7 posts already on disk; provide cross-link targets.
