# From Lead Dev to CTO — How AI and Self-Hosting Changed Everything at Veedoo (2023-2026)

In 2023 I was writing GROQ queries for a CMS. By 2025 I was training a neural network to recognize politicians' faces on GPU-powered servers. Here's how that happened.

---

## The GPT Moment

When OpenAI dropped the GPT-3.5 API in early 2023, the hype was everywhere. Every startup was "AI-powered." Every product was adding a chatbot. Everyone was talking about how AI would replace developers by next Tuesday.

I didn't love the hype. Honestly, I think it hurt AI more than it helped. Non-technical people started expecting AI to do things it fundamentally couldn't. And the gap between what AI CAN do and what AI SHOULD do — nobody was talking about that.

But the technology itself? The technology was real. And I was cautiously excited about finding the right places to use it.

The first real project was **OptiGen** — an AI-powered CRM and lead generation system for a pharmaceutical client. The challenge: track new drug approvals across the EU, US, and Asia, and map them to the key decision-makers (KDMs) and key opinion leaders (KOLs) in each space. The existing process was manual, slow, and couldn't scale.

Here's where my philosophy on AI started to form.

OptiGen COULD have auto-generated emails to these KDMs and KOLs. The AI could write them. We had all the data. It would have been the obvious move.

We deliberately chose not to.

Here's why. Building genuine personal connections with key decision-makers is way more valuable than risking them thinking "oh, just more AI-generated slop" and hitting delete. And people can tell. They can smell a generated email. Especially people who get hundreds of outreach emails a week.

Instead, we built it differently. **AI does the research. Humans do the relationship.**

The system automatically scraped pharmaceutical regulatory databases for new drug approvals. When it found one, it used GPT to crawl public data — press releases, LinkedIn profiles, conference proceedings, previous publications — and built comprehensive dossiers on relevant contacts. Their background, their previous work, their LinkedIn activity, their role in the approval process.

Then it presented all of this to the user. Here's the person. Here's everything you need to know about them. Here's their LinkedIn. Here's what they've been working on lately.

Now YOU write the email. And when you walk into a meeting with this person, the app makes sure you're fully prepared — it surfaces all the relevant intel so you always know who you're talking to.

Human-in-the-loop by design, not as a fallback. AI as a research assistant, not a relationship replacement.

That philosophy has guided every AI feature I've built since.

## Going Deeper (2024)

The next AI project was for Runday — a running platform with 18,000+ runners and 5,000+ events. Their event organizers and community managers needed to pull data from the database, but they didn't know SQL. Their requests always went through a developer. Slow and frustrating for everyone.

I built **"Chat with our DB"** — a natural language interface that let non-technical staff query PostgreSQL in plain English. "How many new runners joined in Kyiv last month?" → generates the SQL → runs it against a read-only replica → formats the results into a human-readable answer.

The technical implementation was a text-to-SQL pipeline using GPT-4. System prompt includes the database schema, table descriptions, relationships, and sample data. Generated SQL gets validated (SELECT only — no mutations), executed with timeout and result size limits, and PII gets redacted before the response.

Nothing groundbreaking by today's standards, but in 2024 it was genuinely useful. It freed up developer time and gave the operations team direct access to their own data. That's what good AI integration looks like — removing bottlenecks, not adding features for the sake of it.

Around the same time, I tackled the **Sanity v3 migration** for EUvsDisinfo. Migrating a CMS with 19,000+ documents across 13 languages from Sanity v2 to v3 — new plugin architecture, new build system (Vite replacing Webpack), rewriting all custom Studio plugins, updating every GROQ query. Zero content loss. Major undertaking, not glamorous, but the kind of work that keeps a platform running for millions of users.

## The Self-Hosting Revolution

This one started because of compliance and ended up becoming a philosophy.

EUvsDisinfo is EU-funded. EU-funded means all data must stay on EU servers. No exceptions. No US-hosted SaaS products. This forced us to explore self-hosting.

I discovered **Coolify** — an open-source, self-hosted PaaS that gives you a Heroku/Vercel-like deployment experience on your own servers. Docker orchestration, automatic SSL, reverse proxy via Traefik, GitHub webhook deployments, database provisioning — all through a web UI.

We started deploying on **Hetzner Cloud** servers. Excellent price-performance, EU data centers, NVMe SSDs. Started with EUvsDisinfo infrastructure, then expanded.

And that's when it clicked. Not just for compliance — for everything.

We were paying for Supabase SaaS. For Trigger.dev SaaS. For various other hosted services. All with rate limits, pricing tiers, connection caps, storage quotas. All controlled by someone else.

Self-hosting eliminated all of that. Custom PostgreSQL tuning? Done. Need more concurrent connections? Change a config file. Need to scale background job workers? Add a server. No tickets to support, no waiting for tier upgrades, no surprise pricing changes.

By the end of 2024, Coolify was becoming the default for all Veedoo projects. By 2025, everything ran on self-hosted infrastructure — Next.js apps, Supabase instances, Trigger.dev workers, n8n automation workflows, Postiz for social media management. All on Hetzner Cloud, all managed through Coolify.

The cost savings were significant. But more than that — it was about ownership. When you control your infrastructure, you control your destiny. No vendor can rug-pull your pricing. No SaaS can deprecate the feature you depend on. No outage on someone else's platform takes your product down.

Self-hosting isn't just a cost optimization. It's a philosophy.

## Architecture > Code

Somewhere in 2024-2025, I noticed a shift in what mattered most in my work.

With AI code assistants becoming genuinely useful — Claude, Cursor, Copilot — writing code got faster. Much faster. But the code is only as good as the design behind it. A language model can implement a function in seconds. It can't tell you whether that function should exist, where it should live in the system, or how it connects to everything else.

I started focusing heavily on **High-Level Design (HLD) and Low-Level Design (LLD)**. Understanding every part of a system — from the individual service level (micro) to the full system architecture (macro) — became the key skill. Not writing code faster, but designing systems better.

This applies everywhere. When I designed ParliamentConnect's ML pipeline, the value wasn't in writing Python code — it was in understanding how speaker diarization feeds into transcription feeds into face detection feeds into face recognition, and designing the data flow between each stage. When I built the community platform's multi-tenant architecture, the value was in designing RLS policies that enforce data isolation at the database level, not in writing the Next.js components.

In the AI era, architecture is the moat. AI can help you implement anything. But you need to know what to implement and how it fits together. HLD and LLD are more important now than ever.

## ParliamentConnect — The Hardest Thing I've Built

In 2025, I took on the most technically ambitious project of my career. Solo.

**ParliamentConnect** automatically processes parliament session videos — 2 to 8 hours long — and identifies who said what. It transcribes every speech and attributes it to the specific MP who delivered it. With 98% accuracy. In 30-45 minutes.

The tech: Python ML pipeline running on RunPod serverless GPUs (NVIDIA RTX PRO 6000, 96GB VRAM). Speaker diarization with pyannote.audio. Transcription with Whisper (faster-whisper for 4x speed). Face detection with RetinaFace. Face recognition matching against an MP database stored in PostgreSQL with pgvector. Video clip extraction with FFmpeg. Frontend in Next.js. Backend on self-hosted Supabase.

I had zero experience with Python ML, CUDA, or GPU computing when I started.

After years of picking up new tech — Android to React Native to Next.js to Sanity to Supabase to Coolify — I trusted the pattern. Every time I've faced a completely new domain, the process is the same: research deeply, understand the architecture, design the system, then implement. AI tools like Claude made the implementation part easier than ever — what used to take weeks of Stack Overflow debugging now takes focused conversations with an AI that understands your codebase.

But the AI couldn't design the pipeline for me. I had to understand how pyannote segments audio into speaker turns. How Whisper handles multilingual content. How RetinaFace detects faces at different scales. How cosine similarity works for face embeddings. How all of these pieces connect in a data pipeline that needs to process hours of video reliably.

That's the HLD/LLD work. That's the part that matters.

The 98% accuracy milestone felt good. Processing an 8-hour parliament session in 30 minutes — work that would take a human team days — felt even better.

## Becoming CTO

Mid-2025, Veedoo promoted me to CTO.

What does CTO mean at a small consultancy? It depends on the week. Some weeks I'm deep in code — like the entire ParliamentConnect solo build. Other weeks it's all architecture decisions, client meetings, mentoring, and strategy. There's no "typical day" and I like it that way.

The biggest CTO responsibility that first year was **AI enablement** — getting the entire development team productive with AI tools. I set up Claude Code with CLAUDE.md project files for each repo. Configured Cursor IDE with .cursorrules files. Deployed MCP (Model Context Protocol) servers so AI assistants could access project-specific data sources. Set up Cursor BugBot for automated code review on every PR.

The team's reaction was mixed. Some developers jumped in immediately. Others were hesitant — either skeptical of the technology or uncomfortable with changing their workflow. I had to meet each person where they were. Show, don't tell. Demonstrate the value on real tasks rather than giving lectures about the future of AI.

Also in 2025: built a **community/learning platform** (Skool-clone) with multi-tenant architecture, AI-powered content tools, and Stripe Connect for marketplace payments. The Stripe Connect integration was complex — multi-party payment routing, automated payouts, webhook-driven lifecycle management. But it works, and creators can monetize their communities through a system that handles all the payment complexity for them.

## Where I Am Now

It's 2026. I'm still CTO at Veedoo. Still building.

All our infrastructure runs on self-hosted Coolify across Hetzner Cloud. EUvsDisinfo continues to serve millions. ParliamentConnect is processing parliament sessions. The community platform is live. The team is using AI tools daily.

Looking back at the trajectory — from writing GROQ queries to training neural networks, from paying for SaaS to owning every server, from writing code to designing systems — the thread connecting all of it is the same: stay curious, keep learning, and focus on understanding how things work at every level.

---

## What These Years Taught Me

**AI should amplify humans, not replace them.** OptiGen's human-in-the-loop philosophy. ParliamentConnect's design-first approach. Training the team on AI tools as force multipliers. The common thread: use AI for what it's good at (research, implementation, repetitive tasks) and keep humans where they're irreplaceable (relationships, design decisions, judgment).

**Self-hosting is a philosophy, not just a cost optimization.** Yes, you save money. But the real value is control — over your data, your scaling, your destiny. When you depend on someone else's infrastructure, you're subject to their decisions.

**Architecture is the key skill now.** AI can write the code. You need to design the system. HLD and LLD — understanding every part from micro to macro — is what separates developers who use AI tools effectively from those who just generate spaghetti faster.

**The CTO title means less than the work.** At a small consultancy, CTO is whatever the company needs you to be that week. Sometimes it's coding. Sometimes it's mentoring. Sometimes it's making infrastructure decisions. The title is nice, but the work is what matters.

---

_This is Part 4 of a 5-part series. Previously: [How I Scaled EveryRun from 80 to 17,659 Users Solo](#). Next up: [Joining a Startup as Founding Engineer — My Baseloop Story](#)._

_Check out the open source tools I built along the way:_

- _[Self-Hosted Next.js & Supabase Starter Template](https://github.com/tao101/Self-Hosted-Next.js-Supabase-Fullstack-Starter-Template)_
- _[Coolify Trigger.dev v4](https://github.com/tao101/coolify-trigger-v4)_
- _[Supabase Sync](https://github.com/tao101/supabase-sync-script) (npm: `supabase-sync`)_
- _[Latest Supabase Coolify Template](https://github.com/tao101/latest-supabase-coolify-template)_

_Find me on [GitHub](https://github.com/tao101), [LinkedIn](https://www.linkedin.com/in/taoufiqlotfi), or at [taoufiqlotfi.com](https://www.taoufiqlotfi.com)._
