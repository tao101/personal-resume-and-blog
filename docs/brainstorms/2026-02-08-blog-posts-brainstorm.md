# Brainstorm: 5 Personal Brand Blog Posts

**Date:** 2026-02-08
**Author:** Taoufiq Lotfi (born 1996, Moroccan, writing from 2026)

---

## What We're Building

5 blog posts for Taoufiq's personal blog, each covering a chapter of his career. Written in first person, informal but not sloppy, as a 29/30-year-old Moroccan developer looking back at his journey. The goal is personal brand building — showing the human behind the code.

---

## Key Decisions

- **Tone:** Mix of personal storytelling and technical insights. Lead with the story, weave in tech naturally. Not a tutorial, but devs reading it pick up useful stuff.
- **Vulnerability level:** Balanced. Mention real challenges without oversharing. Don't pretend everything was easy, but don't dwell either.
- **Veedoo split into 2 posts:** Part 1 (2019-2022) covers joining, learning, war, humanitarian response. Part 2 (2023-2026) covers AI adoption, self-hosting revolution, CTO role.
- **CTAs:** Each post ends with a personal reflection/lesson + links to relevant repos, projects, or tools mentioned.
- **Length target:** ~1500-2500 words per post. Long enough to tell the story properly, short enough to hold attention.
- **Language:** English. Conversational. Short paragraphs. Some Arabic/French sprinkled in if it feels natural (e.g., "hamdulillah" or "alhamdulillah" for genuine moments).

---

## Post 5: "A Moroccan Developer's Journey — From Android Apps in Morocco to React Native in Ukraine" (Freelance years, 2014-2019)

**Publishing order: 1st** (origin story)

### Hook
Opening with where it all started: "In 2014, I was an 18-year-old in Morocco building Android apps in Java while studying at university. I had no idea that in a few years I'd be living in Ukraine, building mobile apps for clients across Europe, and setting up the foundation for everything that came after."

### Story Arc

1. **The real beginning — hardware kid (age 12):**
   - Started tinkering with Arduino at 12 years old. Was drawn to hardware first — understanding how physical things work. This curiosity about how things work underneath is what eventually pulled him toward software.
   - The shift from hardware to software happened naturally. Got an Android phone and wanted to build apps for it. That was the gateway.

2. **Morocco & the hustle (2014-2017):**
   - Building Android apps while studying at Ibn Zohr university. Java, Android SDK, Firebase, Material Design.
   - Freelancing on oDesk (now Upwork) — finding clients globally as an 18-year-old from Morocco. The hustle of managing clients, delivering apps, publishing to Play Store, all while going to class.
   - Self-taught before university. The university provided structure but the real learning was building real things for real clients.

3. **Why Ukraine:**
   - Ukrainian universities offered affordable, quality Computer Engineering programs. Common path for Moroccan/North African students.
   - The decision to move across continents for education. Packing up and leaving Morocco.

4. **Kharkiv — culture shock & growth (2017-2019):**
   - Language barrier was the biggest challenge. A Moroccan in Eastern Europe navigating a completely different language and culture.
   - Studying Computer Engineering (architecture, algorithms, networking, embedded systems) — how low-level computing knowledge later informed GPU computing (CUDA), Docker, server management.
   - Pivoting from native Android to React Native. Cross-platform was the future. Building iOS + Android from one codebase.
   - Continued freelancing on Upwork while studying. The grind of university + client work.

5. **The bridge to Veedoo (2019):**
   - Veedoo found him through his freelance work — reputation built over 5 years of shipping apps led to the opportunity.
   - Transition from freelance to first "real" company job.

### Technical Insights (woven into the story)
- Arduino → Android → React Native evolution
- The oDesk/Upwork freelance hustle (practical tips from experience)
- What Computer Engineering taught that web dev bootcamps don't
- CodePush for OTA updates — shipping without App Store review
- The skills that transfer from mobile to web (and the ones that don't)

### Key Lessons (closing)
- **"Just ship it"** — Freelancing taught pragmatism over perfection. Stop overthinking, deliver.
- **"Clients teach you more than code"** — Communication, managing expectations, understanding what people actually need. The soft skills that no tutorial covers.

### Links/CTA
- GitHub profile
- Personal website
- A message to young Moroccan/African developers starting out
- Invite readers from similar backgrounds to connect

---

## Post 1: "From Morocco to Ukraine to CTO — My First 4 Years at Veedoo" (2019-2022)

**Publishing order: 2nd**

### Hook
Opening with the contrast: a Moroccan developer who got found by a European consultancy through his freelance work, built humanitarian platforms, and then watched the country he'd called home for 5 years go to war — all while building the tools that would help the people affected.

### Story Arc

1. **Joining Veedoo (2019):**
   - They found him through his freelance portfolio. The shift from solo freelancer to team member at a European digital consultancy.
   - Transition from mobile to full stack web. Somewhere in between comfortable and challenged — React Native to React was natural, but backend/databases were new territory.
   - Tech: React, Node.js, Express, MongoDB. Building SPAs and mobile apps for Veedoo's clients.

2. **Leveling up (2020-2021):**
   - Discovering Next.js. The "aha" moment with SSG — migrating 500+ blog posts, TTFB from ~2-3s to <100ms. Understanding SSR vs SSG vs CSR trade-offs.
   - Jamstack architecture. Sanity CMS.
   - Starting Lifeline Ukraine — Ukraine's national suicide prevention hotline platform. Building with trauma-informed UX (quick-exit button, calming visuals, GDPR-compliant anonymous chat).
   - The PHP project (Icons of Ukraine) that expanded his backend versatility. Docker, Linux server admin.

3. **The war — February 24, 2022:**
   - **Key personal detail:** Was on vacation in Turkey when the invasion started. Lucky to not be in Kharkiv — but the shock of not being able to go back. Left everything there expecting to return in 2 weeks. Never went back.
   - The emotional weight of watching your adopted city get bombed from abroad.

4. **Ukraine Shelter — 3 days to launch:**
   - Veedoo initiative. Domain registered Feb 25 (1 day after invasion), site live Feb 27.
   - Building a shelter-matching platform under impossible conditions. Pragmatic architecture — speed over perfection because people needed help NOW.
   - The feeling of shipping something where downtime doesn't mean lost revenue, it means people don't find shelter.

5. **Lifeline Ukraine under wartime pressure:**
   - The platform built in 2021 became life-critical. Traffic surged by orders of magnitude.
   - Scaling infrastructure, caching, monitoring. Zero downtime for a service where lives depend on it.
   - **Personal weight:** Both heavy and motivating. For both Ukraine Shelter and Lifeline, knowing that downtime means lives affected — not just money lost — changes how you approach your work.

6. **EUvsDisinfo & the promotion:**
   - Taking ownership of the CMS and backend for Veedoo's biggest client (European External Action Service).
   - Building the disinformation evidence preservation pipeline: web scraping → HTML archiving → OpenTimestamps blockchain timestamping. Immutable, legally defensible proof.
   - Sanity v1 → v2 migration. Custom editorial tools for a 13-language platform.
   - **Promotion to Lead Full Stack Developer (end of 2022):** A pleasant surprise. Wasn't pushing for it — the client's satisfaction with the automation work led to it.

7. **After the war started — going home:**
   - From Turkey → back to Morocco. Wanted to be close to family after everything.
   - Stayed in Morocco for ~3 years working remotely. (Moved to Moldova Q4 2024.)

### Technical Insights (woven into the story)
- Next.js SSG migration (TTFB win with real numbers)
- Building under wartime constraints — pragmatic architecture decisions
- OpenTimestamps blockchain timestamping for evidence preservation
- Sanity CMS for a 13-language, 19,000+ document platform
- Trauma-informed UX (quick-exit feature for domestic violence contexts)

### Key Takeaways (closing)
All four, woven together:
- **Tech can save lives** — When you build shelter matching and suicide prevention, code stops being abstract
- **Adversity builds you** — The hardest moments shaped more than any comfortable project
- **Stay adaptable** — Morocco → Ukraine → Turkey → Morocco, mobile → web, normal times → wartime
- **Show up and deliver** — The promotion came from consistently doing excellent work, not from asking for it

### Links/CTA
- EUvsDisinfo website
- Lifeline Ukraine
- Invite readers to share their own "building under pressure" stories

---

## Post 3: "How I Scaled a Running Platform from 80 to 17,659 Users as the Only Developer" (EveryRun)

**Publishing order: 3rd**

### Hook
Opening with the numbers: "When I joined EveryRun, 80 people were using the platform. When I left 14 months later, that number was 17,659. I was the only developer the entire time."

### Story Arc

1. **How I got the gig:**
   - Part-time alongside Veedoo. The appeal of owning a product end-to-end as the sole developer.

2. **The tech stack decisions:**
   - Why Next.js App Router + Neon + Drizzle + Stripe + PostHog + Vercel.
   - Honest opinions: what worked, what was annoying. Why Drizzle over Prisma. Why Neon over regular Postgres.

3. **The Neon DB branching workflow:**
   - Game-changer. Every PR got its own database with real production data.
   - CEO could review features in isolated environments. 10x'd development speed.

4. **The growth story:**
   - 80 → 17,659 users. Growth was marketing-driven — the CEO/business side drove acquisition. Taoufiq's job was making sure the product could handle it and the features were there.
   - PostHog analytics, A/B testing with feature flags.
   - Charitable donation integration via Stripe Connect.

5. **The reality of being a solo dev:**
   - **All three pain points were real:**
     - No code review, no second opinion on architecture decisions. No safety net.
     - Always on-call — if it broke, only you could fix it.
     - Context switching — doing this part-time alongside Veedoo meant constantly switching between two codebases.

6. **The handover:**
   - Product was stable, team wanted to shift budget to marketing. Clean exit.
   - Writing 30 pages of documentation — driven by professional pride AND having been on the receiving end of bad handovers.
   - The bittersweet feeling of handing off something you built from scratch.

### Technical Insights (woven into the story)
- Neon DB branching + Vercel preview deployments workflow
- Drizzle ORM vs Prisma real-world comparison
- Stripe Connect for charitable donations
- PostHog for data-driven product decisions (feature flags, A/B testing, funnels)
- What goes into 30 pages of handover docs (ADRs, schema docs, API reference, deployment procedures)

### Closing Reflection
Ownership, making decisions alone, and the underrated skill of documenting well so the next person can succeed.

### Links/CTA
- EveryRun
- Invite solo devs to share their experiences

---

## Post 2: "From Lead Dev to CTO — How AI and Self-Hosting Changed Everything at Veedoo" (2023-2026)

**Publishing order: 4th**

### Hook
"In 2023 I was writing GROQ queries for a CMS. By 2025 I was training a neural network to recognize politicians' faces. Here's how that happened."

### Story Arc

1. **The GPT moment (2023):**
   - When the GPT API dropped. Building OptiGen — AI-powered pharma lead generation.
   - **Key philosophy — AI should do the research, humans should do the relationship:**
     - OptiGen could have auto-generated emails to key decision-makers (KDMs) and key opinion leaders (KOLs). They deliberately chose NOT to.
     - Instead: AI does all the research (drug approvals, contact discovery, LinkedIn profiles, previous work, posts). Provides the user with everything they need to know. Shows all contact info.
     - The user writes the email personally. Because building genuine personal connections with KDMs/KOLs is more valuable than risking them thinking "oh, just more AI-generated slop."
     - Same for meeting prep — the app surfaces all relevant intel so you walk into every meeting prepared.
     - Human-in-the-loop by design, not as a fallback.
   - **Honest take on AI hype:** Didn't like the big hype. It hurt AI in general because non-technical people expected it to do way more than it was capable of. Just because AI CAN do something doesn't mean it SHOULD.

2. **Going deeper with AI (2024):**
   - "Chat with our DB" for Runday — text-to-SQL pipeline letting non-technical staff query PostgreSQL in plain English.
   - Learning RAG, embeddings, vector databases (pgvector).
   - Sanity v3 migration — 19,000+ documents, zero data loss. Major undertaking.

3. **The self-hosting revolution (2024):**
   - **Started because of compliance** — EUvsDisinfo (EU-funded) requires all data on EU servers. This forced self-hosting exploration.
   - **Stayed because it was better** — after learning Coolify, realized the philosophy and cost savings were worth it across ALL projects.
   - Discovering Coolify. Migrating to Hetzner Cloud. Self-hosting Supabase, n8n, eventually everything.
   - By end of 2024: Coolify was becoming the default for all Veedoo projects.

4. **The shift to architecture thinking (2024-2025):**
   - With AI code assistants becoming powerful, the most important skill shifted to understanding architecture — both High-Level Design (HLD) and Low-Level Design (LLD).
   - Understanding every part of a system from micro (individual service) to macro (full system) is the key to success. AI can help implement, but you need to design.
   - This applies to everything from ParliamentConnect's ML pipeline to the community platform's multi-tenant architecture.

5. **ParliamentConnect — built solo (2025):**
   - The most technically complex project. Python, ML, CUDA, GPU computing — all new.
   - **Approach: trusted the pattern.** After years of picking up new tech (Android → React Native → Next.js → ...), knew he'd figure it out. Plus AI tools like Claude made it easier — focus on research, HLD/LLD, understanding the pipeline. Let AI assist with implementation details.
   - Speaker diarization, face recognition, Whisper transcription. 98% accuracy. 30-45 min processing for 2-8 hour sessions.
   - RunPod serverless with NVIDIA RTX PRO 6000 GPUs.

6. **Becoming CTO (mid 2025):**
   - CTO at a small consultancy: **depends on the week.** Some weeks deep in code (like the ParliamentConnect solo build), other weeks it's all strategy, mentoring, and architecture decisions.
   - Training the team on AI tools: **mixed reactions.** Some devs jumped in, others were hesitant. Had to meet each person where they were.
   - Claude Code, Cursor IDE, MCP servers, Cursor BugBot for automated code review.
   - Skool-clone community platform with Stripe Connect marketplace payments.
   - By this point: all infrastructure running on self-hosted Coolify across Hetzner Cloud.

### Technical Insights (woven into the story)
- OptiGen's human-in-the-loop philosophy (AI for research, humans for relationships)
- Text-to-SQL pipeline (Runday)
- Self-hosting journey: Coolify + Hetzner (compliance → philosophy → cost savings)
- ParliamentConnect ML pipeline (pyannote, Whisper, RetinaFace, pgvector)
- Why HLD/LLD is the key skill in the AI era
- How to introduce AI tools to a mixed-reaction team

### Closing Reflection
The evolution from "coder" to "architect" to "technical leader." Why the most important thing you can learn now is how to design systems, not how to write code — because AI will increasingly handle the latter. Self-hosting as a philosophy of ownership.

### Links/CTA
- ParliamentConnect
- All 4 open source repos
- Invite readers to share their self-hosting journey or AI philosophy

---

## Post 4: "Joining a Startup as Founding Engineer — My Baseloop Story" (Baseloop, still ongoing)

**Publishing order: 5th** (latest chapter)

### Hook
"When you're already a CTO working full-time, joining a startup part-time as a founding engineer sounds crazy. Here's why I did it anyway."

### Story Arc

1. **Why I said yes:**
   - All three reasons: startup energy (building from zero vs. consultancy work), the people (connected with the CEO), and interesting technical challenges.
   - Different from Veedoo — product company vs. consultancy. Different pace, different problems.

2. **The first task — rip out SaaS:**
   - Migration from Trigger.dev SaaS + Supabase SaaS to fully self-hosted on Coolify.
   - This one project ended up producing 3 open-source tools and an npm package.

3. **The scary parts:**
   - **Real "oh shit" moments.** Especially Trigger.dev — painful to self-host. Multiple times had to dig into their open source code to fix issues they were facing. This is real founding engineer work.
   - Supabase migration: preserving bcrypt password hashes so users don't need to reset passwords. The subtle things that can go very wrong.

4. **Open-sourcing the tooling:**
   - Wasn't planned from the start. Built it for Baseloop, then realized nobody else had solved this problem either.
   - Decided to open-source to help others going through the same migration path.
   - supabase-sync (npm), Coolify Trigger.dev template, Supabase Coolify template.

5. **Learning CedarJS:**
   - New TypeScript framework with Laravel-like patterns. Picked it up quickly — convention-over-configuration feels natural for anyone who knows MVC.
   - GraphQL vs REST — honest take.

6. **Balancing two jobs:**
   - Clear time blocks: Veedoo full-time, Baseloop in dedicated hours.
   - **The honest truth:** works because he's an "indoor cat" — spends most time in his room in front of his laptop, easily 10-12 hours a day. Not complaining — it's what he enjoys.
   - Both roles energize differently: consultancy (variety, client work) vs. startup (ownership, speed).

7. **Where it's going:**
   - What excites him most is the founding experience itself — being there from day one, making foundational decisions.
   - Keep it vague on product details, focus on the experience of being a founding engineer.

### Technical Insights (woven into the story)
- Trigger.dev self-hosting pain points (and reading their source code to fix issues)
- Full Supabase SaaS-to-self-hosted migration (the gotchas)
- How supabase-sync works and why bcrypt hash preservation matters
- CedarJS first impressions for TypeScript devs
- Coolify as the common infrastructure layer across both jobs

### Closing Reflection
Why founding engineer roles are valuable even part-time. What you learn when nothing exists yet and you have to build the tooling before you can build the product. The open source mindset: "I built this for myself, but if it helped me, it'll help someone else too."

### Links/CTA
- All 4 open source repos (with npm link for supabase-sync)
- Baseloop website
- Invite other founding engineers to share their experience

---

## Publishing Order (Final)

1. **Post 5 (Freelance)** — Origin story. Arduino at 12, Android apps, oDesk, Morocco to Ukraine.
2. **Post 1 (Veedoo Part 1)** — War, humanitarian tech, growth. The emotional core.
3. **Post 3 (EveryRun)** — Solo dev story. The numbers-driven standalone piece.
4. **Post 2 (Veedoo Part 2)** — AI era, self-hosting, CTO. The technical evolution.
5. **Post 4 (Baseloop)** — Latest chapter. Founding engineer, open source, what's next.

Chronological narrative arc. Each post can stand alone but together they tell the full story.

---

## Cross-Cutting Themes

These themes appear across multiple posts and tie the series together:

- **"Just ship it"** — from freelancing through Ukraine Shelter through ParliamentConnect
- **Self-hosting philosophy** — starts in Veedoo Part 2, becomes central in Baseloop
- **AI as a tool, not a replacement** — OptiGen's human-in-the-loop, ParliamentConnect's design-first approach, training the team
- **Architecture > code in the AI era** — HLD/LLD as the key skill, understanding systems from micro to macro
- **Adaptability** — Morocco → Ukraine → Turkey → Morocco → Moldova; Android → React Native → React → Next.js → Python/ML
- **Building things that matter** — shelter matching, suicide prevention, disinformation fighting, open source

---

## Open Questions

- Do you want to include any photos/screenshots in the posts? (e.g., Ukraine Shelter, ParliamentConnect interface, PostHog dashboards)
- Should each post link to the others (creating a "series")?
- Do you have a blog platform in mind or are we building one?
- Any projects/details you want to explicitly NOT mention (e.g., confidential client names)?
