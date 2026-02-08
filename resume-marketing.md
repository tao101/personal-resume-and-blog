# Taoufiq Lotfi

**Full Stack Developer & CTO**

Morocco / Moldova (Remote) | admin@taoufiqlotfi.tech
[LinkedIn](https://www.linkedin.com/in/taoufiqlotfi) | [GitHub](https://github.com/tao101) | [Website](https://www.taoufiqlotfi.com)

---

## Summary

Full stack developer and CTO with 10+ years of experience building and shipping web, mobile, and AI-powered products. Promoted three times in six years — from mid-level developer to CTO — at a European digital consultancy serving EU institutions, nonprofits, and startups. Proven ability to own products end-to-end: architected an ML video processing pipeline with 98% accuracy, scaled a platform from 80 to 17,000+ users as a sole developer, and led the technical strategy for an EU-funded platform reaching millions of annual users across 13 languages. Strong track record in self-hosted infrastructure, AI integration, team mentoring, and delivering high-impact products under pressure — including launching a humanitarian platform within 3 days of the 2022 Ukraine invasion.

---

## Skills

**Languages:** TypeScript, JavaScript, Python, PHP, Java, SQL, HTML, CSS
**Frontend:** React, Next.js (SSR/SSG/ISR/Server Actions), React Native, Expo, Tailwind CSS, Shadcn UI
**Backend:** Node.js, Express, NestJS, Next.js API Routes, Python (ML pipelines)
**Databases:** PostgreSQL, MongoDB, Supabase (hosted & self-hosted), Neon, Drizzle ORM, MySQL
**AI / ML:** OpenAI GPT API, RAG pipelines, Embeddings, PyTorch, CUDA, Whisper (speech-to-text), Speaker Diarization, Face Recognition, pgvector
**Infrastructure:** Docker, Coolify (self-hosted PaaS), Vercel, Hetzner Cloud, RunPod (serverless GPU), Traefik, Nginx, n8n, Trigger.dev
**Payments:** Stripe, Stripe Connect
**CMS:** Sanity (v2 & v3), Jamstack
**Testing & Analytics:** Playwright, Jest, PostHog, Sentry
**Tools:** Git, Claude Code, Cursor IDE, MCP (Model Context Protocol)

---

## Experience

### Veedoo — Digital Consultancy (Remote)

#### CTO | Mid 2025 – Present

- Defined and led technical strategy across all client projects and internal infrastructure for a consultancy serving EU institutions and nonprofits
- Built **ParliamentConnect** solo — an ML-powered platform that automatically transcribes and attributes parliamentary speeches to individual MPs with **98% accuracy**, processing 2-8 hour sessions in 30-45 minutes using speaker diarization, face recognition, and GPU computing (NVIDIA RTX PRO 6000 via RunPod)
- Architected a **community/learning platform** (Skool.com-style) with multi-tenant architecture, AI-powered content tools, and Stripe Connect marketplace payments for creator monetization
- Migrated all company infrastructure from SaaS dependencies to **self-hosted Coolify** on Hetzner Cloud (Supabase, Trigger.dev, n8n, Postiz), significantly reducing monthly costs while gaining full control over data residency and scaling
- Established AI-assisted development workflows company-wide: trained developers on Claude Code, Cursor IDE, and MCP tooling; deployed automated AI code review (Cursor BugBot) across all repositories
- Continued leading development on **EUvsDisinfo**, an EU-funded platform with 19,000+ documented disinformation cases and millions of annual users

#### Lead Full Stack Developer | End of 2022 – Mid 2025

- Shifted focus to **High-Level Design (HLD) and Low-Level Design (LLD)** as AI coding tools matured — championed architecture-first thinking where understanding systems from micro (individual service) to macro (full system) became the key differentiator over writing code faster
- Led development on Veedoo's largest client account (**EUvsDisinfo** for the European External Action Service), managing the backend, CMS architecture, and 13-language content infrastructure
- Built an automated **evidence preservation pipeline** for disinformation cases: web scraping, HTML archiving, and blockchain timestamping (OpenTimestamps) to produce immutable, legally defensible proof
- Migrated CMS from Sanity v2 to v3 with zero content loss across 19,000+ documents; built custom editorial tools that streamlined content operations across a distributed international team
- Developed **OptiGen**, an AI-powered CRM and lead generation system for a pharmaceutical client — designed with a **human-in-the-loop philosophy**: AI handles all research (drug approvals, LinkedIn profiles, publications, conference activity) and builds comprehensive dossiers on key decision-makers, but humans write the outreach emails and build the relationships. Deliberately chose NOT to auto-generate emails — genuine personal connections beat AI-generated "slop"
- Built a **natural language database query interface** ("Chat with our DB") for Runday (18,000+ runners, 5,000+ events), allowing non-technical staff to query PostgreSQL using conversational AI
- Began company-wide adoption of self-hosted infrastructure with Coolify, replacing multiple SaaS subscriptions

#### Mid Full Stack Developer | 2019 – End of 2022

- Transitioned from mobile development to full stack web, rapidly building proficiency in React, Next.js, Node.js, and PostgreSQL
- Migrated a client's 500+ blog post website to Next.js SSG, reducing **Time to First Byte from ~2-3s to <100ms** via CDN-served static pages
- Built **Ukraine Shelter** (ukraineshelter.com) within **3 days** of the 2022 Russian invasion — a platform matching refugees with shelter offers, launched under wartime conditions while personally relocating from Kharkiv
- Maintained and scaled **Lifeline Ukraine**, Ukraine's national suicide prevention hotline platform, to handle wartime traffic surges while serving **1,500+ monthly chat users** with GDPR-compliant anonymous support
- Delivered multiple Jamstack websites and mobile apps for clients across nonprofit, humanitarian, and public sectors
- Promoted to Lead Full Stack Developer based on client satisfaction with EUvsDisinfo automation work

---

### Baseloop — Founding Engineer (Part-time, Remote) | Nov 2025 – Present

- Joined as founding engineer alongside the CEO to build and scale the product
- Led migration from SaaS-dependent stack (Trigger.dev, Supabase) to fully **self-hosted infrastructure on Coolify**, eliminating rate limits and reducing costs
- Open-sourced the migration tooling: Docker Compose templates for Trigger.dev and Supabase on Coolify, plus an npm-published CLI tool (`supabase-sync`) for full instance migrations
- Contributing to the web application built with CedarJS (TypeScript, GraphQL)

---

### EveryRun — Product Engineer (Part-time, Remote) | Jul 2023 – Sep 2024

- As **sole developer**, scaled the virtual running events platform from **80 to 17,659 users** (22,000% growth)
- Architected the full stack: Next.js (App Router), React Native Expo (mobile), PostgreSQL (Neon with DB branching), Drizzle ORM, Stripe (payments), PostHog (analytics/A/B testing), and Vercel
- Designed a development workflow using **Neon DB branching + Vercel preview deployments** — each PR got an isolated database branch with production data, enabling rapid iteration with stakeholder review
- Built custom CRM integration with Fibery.io for event management, user cohort analysis, and revenue dashboards
- Delivered charitable donation integrations via Stripe Connect and authored **30-page codebase documentation** for project handover

---

### Freelance Developer | 2014 – 2019

#### React Native Mobile Developer — Kharkiv, Ukraine (2017 – 2019)
- Built cross-platform mobile applications (iOS + Android) for clients while studying Computer Engineering
- Managed full app lifecycle: development, testing, App Store/Play Store submission, and OTA updates via CodePush

#### Android Developer — Morocco (2014 – 2017)
- Built native Android applications using Java, Android SDK, and Firebase while studying at university
- Published apps to Google Play Store with Material Design UI, REST API integrations, and offline-first patterns

---

## Open Source

- **[Self-Hosted Next.js & Supabase Starter Template](https://github.com/tao101/Self-Hosted-Next.js-Supabase-Fullstack-Starter-Template)** — Production-ready fullstack template with Next.js, self-hosted Supabase, RLS security, Sentry monitoring, Playwright/Jest tests, and Coolify deployment guide
- **[Coolify Trigger.dev v4](https://github.com/tao101/coolify-trigger-v4)** — Docker Compose configs for self-hosting Trigger.dev on Coolify with distributed scaling, NVMe-optimized production configs, and 4 server tier presets
- **[Supabase Sync](https://github.com/tao101/supabase-sync-script)** *(npm: `supabase-sync`)* — CLI tool for full Supabase instance migration (schema, data, auth users with preserved passwords, storage files); supports SaaS-to-self-hosted and CI/CD pipelines
- **[Latest Supabase Coolify Template](https://github.com/tao101/latest-supabase-coolify-template)** — Up-to-date Supabase Docker Compose for Coolify with auto JWT generation, production PostgreSQL tuning, and one-click deployment

---

## Education

**B.Sc. Computer Engineering** — Kharkiv National University of Radio Electronics, Ukraine (2017 – 2020)
*Master's degree started; paused due to 2022 war — plans to complete*

**University Studies** — Universit Ibn Zohr, Morocco (2014 – 2017)

---

## Languages

Arabic, French, English
