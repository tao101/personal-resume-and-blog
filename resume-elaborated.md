# Taoufiq Lotfi

**Full Stack Developer & CTO**

**Location:** Morocco / Moldova (Remote)
**Email:** admin@taoufiqlotfi.tech
**LinkedIn:** [linkedin.com/in/taoufiqlotfi](https://www.linkedin.com/in/taoufiqlotfi)
**GitHub:** [github.com/tao101](https://github.com/tao101)
**Website:** [taoufiqlotfi.com](https://www.taoufiqlotfi.com)

**Languages:** Arabic, French, English

---

## Professional Summary

Full stack developer with over 10 years of experience spanning mobile, web, and backend development — from native Android (Java) and React Native mobile apps, through React/Next.js SPAs and SSR/SSG web applications, to Python ML pipelines running on GPU-powered servers. Started as a freelance Android developer in Morocco, transitioned to React Native mobile development in Ukraine, and grew into a CTO role at a European digital consultancy where I now lead technical strategy across a portfolio of projects serving EU institutions, nonprofits, and startups.

Core technical strengths include architecting full-stack TypeScript applications with Next.js and self-hosted Supabase, building AI-powered features using OpenAI APIs and RAG pipelines, designing ML video processing systems with CUDA/Python, and managing self-hosted infrastructure at scale using Coolify as a PaaS layer on bare-metal and cloud servers. Deep believer in owning your infrastructure — migrated entire company stack from SaaS dependencies to self-hosted alternatives, reducing costs by significant margins while gaining full control over data residency, scaling, and reliability.

---

## Education

### Kharkiv National University of Radio Electronics — Kharkiv, Ukraine

**Bachelor of Science in Computer Engineering** (2017 – 2020)
Coursework included computer architecture, operating systems, algorithms and data structures, networking, digital signal processing, and embedded systems programming. The degree provided a strong foundation in low-level computing concepts that later informed work on GPU computing (CUDA), Docker containerization, and bare-metal server management.

**Master's degree** — Started but paused due to the 2022 Russian invasion of Ukraine. Plans to complete at a later date.

### Universit Ibn Zohr — Morocco

**University Studies** (2014 – 2017)
Studied while simultaneously working as a freelance Android developer, building native Java applications using the Android SDK, SQLite for local storage, and RESTful API integrations.

---

## Work Experience

---

### Veedoo — Digital Consultancy (Remote)

**CTO** (Mid 2025 – Present)
**Lead Full Stack Developer** (End of 2022 – Mid 2025)
**Mid Full Stack Developer** (2019 – End of 2022)

Veedoo is a digital consultancy specializing in multilingual web and platform development, digital solutions for global impact, and strategic communications support — primarily serving the public sector, nonprofits, and EU-funded projects. The company builds and maintains long-running platforms (some 9+ years) requiring high reliability, GDPR compliance, multilingual support (up to 13 languages), and EU data residency requirements.

---

#### 2019 — Joining Veedoo & Transitioning to Web Development

Joined Veedoo as a mid-level full stack developer, transitioning from a mobile-first background (2+ years of React Native freelancing) into web development. Focused on building a mix of web and mobile applications for Veedoo's clients.

**Tech Stack:** React 16.x (SPAs with React Router, Context API for state), React Native 0.59-0.61 (cross-platform mobile), Node.js 12.x with Express 4.x (REST APIs), MongoDB with Mongoose ODM

**Key Activities & Technical Details:**
- Built client-facing single-page applications using React with component-based architecture, React Router for client-side navigation, and Context API / early Redux patterns for state management
- Continued mobile development with React Native, handling platform-specific native modules, navigation (React Navigation), and async storage for offline-first patterns
- Developed RESTful APIs with Express.js following MVC patterns, implementing JWT-based authentication, middleware chains for request validation, and Mongoose schemas with MongoDB aggregation pipelines for complex queries
- Set up CI/CD pipelines for automated testing and deployment of Node.js services
- Adapted quickly from mobile-only development to full stack web work, leveraging transferable JavaScript/TypeScript skills across both React and React Native codebases

---

#### 2020 — Deepening Web Expertise & Embracing Modern Tooling

Took on more projects and responsibilities. Began studying Next.js for its server-side rendering (SSR) capabilities, which offered significant SEO advantages over client-side-only React SPAs — a critical requirement for Veedoo's content-heavy client websites.

**Key Activities & Technical Details:**
- Migrated a client's blog-heavy website from a React SPA to **Next.js with Static Site Generation (SSG)** using `getStaticProps` and `getStaticPaths` for build-time page generation. This moved ~500+ blog posts from client-side-rendered pages to pre-built static HTML served via a CDN (Vercel Edge Network), reducing Time to First Byte (TTFB) from ~2-3s to <100ms and dramatically improving Core Web Vitals scores
- Implemented **Incremental Static Regeneration (ISR)** with `revalidate` intervals so content updates propagated automatically without full rebuilds — solving the stale content problem inherent in pure SSG
- Discovered and adopted **serverless architecture** through Vercel's platform: API routes as serverless functions (Node.js lambdas), automatic scaling to zero, preview deployments per Git branch, and environment variable management per deployment context (production/preview/development)
- Learned the trade-offs between SSR (dynamic, per-request rendering for personalized content), SSG (build-time generation for static content), and CSR (client-side rendering for highly interactive SPAs) — applying the right pattern per use case
- Began using **Vercel Analytics** and **Web Vitals** monitoring to track real-world performance metrics (LCP, FID, CLS) and optimize based on actual user data

**Tech Stack Added:** Next.js 10-11 (Pages Router, SSR/SSG/ISR), Vercel (hosting, serverless functions, edge network, preview deployments), Serverless Functions (Node.js lambdas)

---

#### 2021 — SSR/SSG Mastery, Jamstack & Backend Expansion

Dove deeper into server-side rendering, static site generation, and the Jamstack architecture (JavaScript, APIs, Markup), which provided better products for Veedoo's clients — especially those with content-heavy websites requiring fast load times, strong SEO, and high reliability.

**Key Activities & Technical Details:**
- Built and delivered multiple **Jamstack websites** using the pattern of: pre-rendered static frontend (Next.js SSG) + headless CMS (Sanity) + serverless API functions — decoupling the frontend from the backend for independent scaling and deployment
- Worked on **Icons of Ukraine** — a project using **PHP** (Laravel-style MVC) for the backend with MySQL database, and React for the frontend SPA. This expanded backend language versatility beyond the Node.js ecosystem and provided exposure to PHP's request lifecycle, ORM patterns (Eloquent-style), and traditional server-rendered architectures
- Started deepening **backend knowledge**: relational database design with PostgreSQL (normalization, indexing strategies, foreign key constraints), Docker containerization (writing Dockerfiles, multi-stage builds, docker-compose for local development environments), Linux server configuration (nginx reverse proxy, SSL/TLS with Let's Encrypt, process management with PM2/systemd)
- Began contributing to **Lifeline Ukraine** (lifelineukraine.com) — Ukraine's national suicide prevention hotline platform

**Tech Stack Added:** PHP (MVC), MySQL, Docker (Dockerfile, docker-compose, multi-stage builds), Nginx, Linux server administration, Sanity CMS (headless, GROQ query language), Jamstack architecture

**Project Highlight — Lifeline Ukraine (Started 2021, Ongoing):**

> *A digital platform offering psychological support to Ukrainians during moments of crisis, including anonymous chat, mental health resources, and an online suicide awareness training to help people recognise and respond to suicidal thoughts.*

- **Challenge:** As Ukraine's only national suicide prevention hotline, LifeLine Ukraine plays a critical role in supporting individuals affected by the trauma of war. However, the absence of a user-friendly digital platform limited public awareness and made it harder for Ukrainians in need — especially those in high-risk or frontline areas — to seek help anonymously and discreetly.
- **Solution:** Developed a secure, mobile-optimised website tailored to vulnerable users. The platform offers anonymous chat-based support, emergency contact tools, and curated mental health resources. The design was guided by trauma-informed UX principles, including calming visuals, intuitive navigation, and a **quick-exit feature** (a prominent button that instantly navigates to an innocuous website like Google — critical for users in unsafe domestic environments). All features were developed in line with GDPR standards, with no personally identifiable information stored in chat sessions. Implemented **HTTPS everywhere** with HSTS headers, Content Security Policy (CSP) headers to prevent XSS, and secure cookie handling. Also developed a free online suicide awareness training course with progress tracking and completion certificates.
- **Impact:** More than 1,500 people use the platform's chat feature each month, providing Ukrainians — including refugees who are unable to call the hotline number from abroad — with easy and safe access to lifesaving mental health support.
- **Client Testimonial:** *"I've been impressed with the level of professionalism of the Veedoo team and management since we began working together almost 5 years ago."* — Paul Nailand, Lifeline Ukraine
- **Services:** Web Development, UX/UI Design, Usability Testing, Information Architecture, CMS, Hosting, Analytics
- **Technical Specifics:** Responsive design (mobile-first, tested across iOS Safari, Android Chrome, and low-bandwidth connections common in rural Ukraine), WCAG 2.1 AA accessibility compliance, Google Analytics with custom event tracking for anonymous usage patterns (no PII), automated uptime monitoring

---

#### 2022 — War, Humanitarian Response & Promotion to Lead

A pivotal year. The Russian invasion of Ukraine in February 2022 changed everything. Relocated from Kharkiv to Moldova/Morocco while continuing to work remotely. Channeled technical skills into immediate humanitarian response while managing increased responsibilities at Veedoo.

**Promoted to Lead Full Stack Developer (End of 2022)**

**Key Projects:**

**1. Ukraine Shelter (ukraineshelter.com) — February 2022**

> *Launched amidst the chaos and confusion of the Russian invasion of Ukraine.*

Nobody remembers who had the idea or exactly when the project started, but the domain name was registered on **25 February** (1 day after the invasion) and the first version of the site launched on **27 February 2022** — just 3 days after the invasion began.

The early days were chaotic, but together with a small team of volunteers and supported by the designers and developers at Veedoo, the site launched primarily to coordinate incoming offers of help and shelter. The platform was needed to log and record offers of accommodation and to match these with friends and family who were moving to safer parts of Ukraine or crossing into the EU.

**Technical Context:** Built under extreme time pressure (wartime conditions, personal relocation from Kharkiv). The initial version prioritized speed-to-launch over architectural perfection — a pragmatic decision that allowed the platform to start helping people immediately. The system handled form submissions for shelter offers, a matching algorithm to connect refugees with available accommodation, and a map-based interface for geographic searching. Infrastructure was designed for high availability given the critical nature of the service.

Since then the project has grown significantly, with a sizable team of volunteers all committed to helping Ukrainians find a safe place to stay away from the dangers of war.

**2. Lifeline Ukraine — Upgraded (Critical Wartime Priority)**

The platform built in 2021 became more important than ever due to the war. Focused on upgrading the system and helping the team set up everything they needed to assist as many people as possible — with the main goal of making it as easy for them as possible to provide support at scale.

**Technical Details:** Scaled the infrastructure to handle the surge in traffic following the invasion (traffic increased by orders of magnitude as the war drove demand for mental health support). Optimized database queries, implemented caching layers, and ensured the chat system could handle concurrent connections reliably. Added monitoring and alerting to ensure zero downtime for a life-critical service.

**3. EUvsDisinfo — Backend & CMS Architecture (Veedoo's Biggest Client)**

> *An AI-enhanced multilingual digital platform helping citizens across Europe and beyond recognise, understand, and build resilience to Russian disinformation through trusted content, expert analysis, and public education.*

- **Challenge:** In response to growing disinformation following the 2014 Ukrainian revolution and Russia's annexation of Crimea, the EEAS launched EUvsDisinfo — an initiative to collect, analyse, and expose Russian disinformation across Europe. The EEAS required a multilingual platform and a custom content management system to support collaboration across its international network of analysts, contributors, and editors.
- **Solution:** Designed and developed a custom "Disinformation Management System" (DMS) to serve as a secure, AI-enhanced editing and publishing platform, alongside a fully responsive public-facing website. The system enables real-time editorial collaboration and content workflows, supports 13 languages, and aligns with GDPR and EU usability standards. The platform also hosts a library of educational resources, functioning both as a research hub and a public awareness tool.
- **Impact:** The EUvsDisinfo platform has published over 19,000 verified disinformation cases and reaches millions of users annually. It has become a central source for understanding Russian disinformation tactics, providing a secure, scalable, and multilingual infrastructure for the EEAS and its partners.
- **Client:** European External Action Service (EEAS) — Government / Public Sector
- **Services:** Custom Software & Web Development, UX/UI Design, Usability Testing, AI Optimisation, Hosting & Support
- **Duration:** 9 years, ongoing

**Personal contributions to EUvsDisinfo in 2022 — Technical Deep Dive:**
- **CMS Architecture:** Took ownership of the backend and CMS infrastructure built on **Sanity CMS**. Sanity uses a real-time, collaborative editing model (similar to Google Docs) backed by a document-oriented data store with **GROQ** (Graph-Relational Object Queries) as its query language. Migrated the entire content schema and editorial workflows from Sanity v1 to **Sanity v2**, which involved rewriting custom input components, updating the Studio configuration, and migrating the GROQ queries powering the public-facing website
- **Disinformation Evidence Automation Pipeline:** Built a Node.js-based automation system that, when an analyst flagged a disinformation article:
  1. **Web scraping:** Used Puppeteer (headless Chrome) to navigate to the flagged URL and capture a full-page screenshot at multiple viewport sizes
  2. **HTML archiving:** Downloaded the complete HTML source including inline assets (images, stylesheets) using a recursive scraper, creating a self-contained archive of the page as it appeared at that moment — critical for evidence preservation since disinformation sources frequently edit or delete content
  3. **Blockchain timestamping:** Integrated **OpenTimestamps** (an open protocol that leverages the Bitcoin blockchain) to create cryptographic timestamps for each archive. This generates a proof that the archived content existed at a specific point in time, providing legally defensible, immutable evidence that cannot be backdated or tampered with. The timestamp proof is stored alongside the archive in Sanity
  4. **Workflow integration:** The entire pipeline was triggered via Sanity webhooks, ran as background jobs, and updated the CMS document with links to the archived evidence and timestamp proofs — all without requiring analyst intervention beyond the initial flagging
- Built editorial workflow tools with custom Sanity plugins (React-based UI components within the Sanity Studio) for exploring, categorizing, and documenting disinformation patterns across 13 languages
- **Infrastructure:** All EUvsDisinfo infrastructure is self-hosted on EU-based servers (requirement for EU-funded projects — no data can leave EU jurisdiction). Managed deployment, monitoring, backups, and security hardening
- The client's satisfaction with this work directly led to the **promotion to Lead Full Stack Developer**

---

#### 2023 — Lead Role, AI Integration & EveryRun

As Lead Full Stack Developer, continued deep work on EUvsDisinfo while exploring the newly released GPT API (GPT-3.5 Turbo, later GPT-4) for client projects.

**Key Projects at Veedoo:**

**1. EUvsDisinfo — Continued Development**
Maintained and developed new features for the platform, continuing to improve editorial workflows and the disinformation management system. This included performance optimizations on GROQ queries for the public-facing site (which serves millions of pageviews), implementing content versioning and audit trails for editorial accountability, and improving the multilingual content publishing pipeline.

**2. OptiGen — AI-Powered Lead Generation in the Pharmaceutical Sector**

> *Built using the newly released GPT API combined with web scraping to create an intelligent lead generation system.*

- **Challenge:** A leading healthcare client needed an efficient way to track and engage with key contacts associated with newly approved medicines and drugs across the EU, US, and Asia. The existing process was slow and heavily reliant on manual research, limiting the client's ability to respond quickly to new market opportunities and build relationships at scale.
- **Solution:** Designed and developed a custom AI-powered CRM and lead generation system that automatically identified new drug approvals and mapped them to relevant contacts. The system scraped and analysed public data, cross-referenced sources, and validated contact details using smart algorithms. Built-in feedback loops allowed the system to learn and improve over time, increasing accuracy and relevance with continued use.
- **Impact:** Delivered a powerful, self-improving lead generation tool that automated thousands of manual tasks. By integrating AI into the research and validation process, the client gained a faster, more reliable way to identify prospects and engage decision-makers as soon as a new product hit the market — significantly enhancing operational efficiency and business development capacity.
- **Client:** Confidential Healthcare Partner
- **Services:** Systems Analysis & Design, Software Architecture, Custom Software Development, AI Integration, Data Scraping & Analysis, Testing & User Support

**Technical Deep Dive — OptiGen:**
- **Data Pipeline:** Built a scheduled scraping pipeline using Node.js with Puppeteer and Cheerio that monitored pharmaceutical regulatory databases (FDA, EMA, PMDA) for new drug approvals. When a new approval was detected, the system extracted structured data: drug name, generic name, approval date, therapeutic area, indication, region, and sponsoring company
- **AI-Powered Contact Discovery:** Used the **OpenAI GPT API** (initially GPT-3.5 Turbo, upgraded to GPT-4 as it became available) to:
  - Parse unstructured web content (press releases, LinkedIn profiles, conference proceedings) to identify key decision-makers associated with each drug approval
  - Validate and enrich contact information by cross-referencing multiple data sources
  - Generate relevance scores for each contact based on their role, seniority, and proximity to the drug approval process
- **Feedback Loop:** Implemented a human-in-the-loop feedback system where the client could mark contacts as relevant/irrelevant, which was fed back into the prompt engineering and scoring algorithms to improve accuracy over time
- **Tech Stack:** Node.js, Puppeteer, Cheerio, OpenAI GPT API, PostgreSQL, React dashboard for CRM interface

---

### EveryRun — Virtual Running Events Platform (Part-time, Remote)

**Product Engineer** (July 2023 – September 2024)

> *Membership platform for runners. Everyone. Everywhere. Everyrun.*

As the **sole developer**, scaled the virtual running events platform from **80 to over 17,659 users** by delivering comprehensive features and robust infrastructure.

**Tech Stack (Detailed):**
- **Frontend:** Next.js 14 (App Router with React Server Components, Server Actions for mutations, Streaming SSR with Suspense boundaries), TypeScript (strict mode), Tailwind CSS for styling
- **Mobile:** React Native Expo (managed workflow) with shared TypeScript types between web and mobile
- **Database:** PostgreSQL hosted on **Neon** (serverless Postgres with branching — each preview deployment got its own isolated database branch, enabling safe testing of schema migrations without affecting production data)
- **ORM:** Drizzle ORM (type-safe SQL query builder with automatic TypeScript type inference from the database schema — chosen over Prisma for its lighter runtime, SQL-first approach, and better serverless cold-start performance)
- **Validation:** Zod for runtime type validation on both API inputs and form data, with shared schemas between frontend forms and backend API routes
- **Authentication:** Lucia-Auth (lightweight, session-based auth library that provides full control over the session storage layer — sessions stored in PostgreSQL, with secure HTTP-only cookies and CSRF protection)
- **Analytics:** PostHog (self-hosted analytics with feature flags, A/B testing, session replays, and funnel analysis — used to make data-driven product decisions)
- **Payments:** Stripe (subscriptions, one-time payments, webhook handling for payment lifecycle events)
- **Hosting:** Vercel (with preview deployments per PR, automatic HTTPS, edge caching)

**Key Achievements — Technical Details:**
- **Development Workflow Architecture:** Architected a streamlined development process leveraging **Vercel preview deployments** + **Neon DB branching**. Every Git push created a preview deployment with its own isolated database branch (forked from production data). This meant the CEO and stakeholders could review features with real data in isolated environments, and schema migrations could be tested against production-like data before merging. This workflow enabled rapid iteration: features went from idea to production in days, not weeks
- **Virtual Event System:** Built a complete virtual race platform where users could log GPS-tracked runs (via mobile app), participate in virtual events across time zones, track progress on leaderboards with real-time updates (using PostgreSQL LISTEN/NOTIFY via Neon), and earn achievements. Implemented distance calculation using the Haversine formula on GPS coordinates
- **Charitable Donation Integration:** Integrated Stripe Connect to enable charitable donations tied to running events — runners could raise money for specific causes, with automatic fund distribution to registered charities
- **Fibery.io CRM Integration:** Built a bidirectional sync between the EveryRun database and **Fibery.io** using their REST API, creating a custom CRM workspace for the CEO and Sales Manager. This included automated event reports, user cohort analysis, churn tracking, and revenue dashboards — all synced in near-real-time via background jobs
- Authored a comprehensive **30-page codebase documentation** covering architecture decisions (with ADR format), database schema documentation, API reference, deployment procedures, and onboarding guide — ensuring a smooth handover and long-term project success upon project completion

**Veedoo Case Study on EveryRun:**
- **Challenge:** Everyrun set out to create a global platform that connects runners of all levels through community-driven races and running events. The challenge was to build a seamless user experience that supports both race participants and event organizers.
- **Solution:** Full UX research, user interviews with both runners and organizers, and usability testing across multiple geographies. The insights guided a redesign of the web platform's structure, focusing on accessibility, speed, and clarity. A revised information architecture and new product design were implemented to streamline event discovery, registration, and management. The platform supports multilingual content, custom branding for events, and real-time updates.
- **Impact:** Event participation increased and user satisfaction improved thanks to simplified workflows for both runners and hosts. The intuitive design has helped position Everyrun as a leader in digital running experiences — uniting people around the world through sport.

---

#### 2024 — Backend Mastery, Self-Hosting & AI Deep Dive (at Veedoo)

Continued as Lead Full Stack Developer, deepening backend and infrastructure expertise while exploring AI, self-hosting, and modern database technologies.

**Key Projects at Veedoo:**

**1. EUvsDisinfo — Sanity v3 Migration & Internal Tooling**
- Upgraded the CMS from **Sanity v2 to Sanity v3** — a major migration involving the transition from Sanity's legacy Studio framework to the new one built on Vite (replacing Webpack), React 18 (with concurrent features), and a new plugin architecture. This required rewriting all custom Studio plugins, migrating the document schema definitions to the new format, updating GROQ queries for v3's updated query engine, and testing the migration with production data to ensure zero content loss
- Built additional internal tools for the editorial team using **Sanity's custom document actions** and **custom views** (React components embedded in the Studio) to streamline workflows: bulk content operations, cross-language content validation (ensuring all 13 language versions are in sync), and automated content quality checks

**2. Runday — "Chat with Our DB" AI Feature**

> *An online ecosystem powering free, inclusive 5K events — helping thousands of runners across multiple cities get moving, connect locally, and grow a movement to promote community health.*

- Built a conversational AI interface ("Chat with our DB") for the Runday client, allowing non-technical users (event organizers, community managers) to query their PostgreSQL database using natural language. For example: "How many new runners joined in Kyiv last month?" or "What's the average attendance for Saturday events in 2024?"
- **Technical Implementation:** Built a **text-to-SQL** pipeline using the OpenAI GPT-4 API. The system takes a natural language query, combines it with the database schema (table definitions, column descriptions, relationships, and sample data) as context in the system prompt, and generates a SQL query. The generated SQL is validated against a whitelist of allowed operations (SELECT only — no mutations), executed against a read-only database replica, and the results are formatted back into natural language by a second LLM call. Implemented guardrails including query timeout limits, result set size limits, and PII redaction
- Studied **RAG (Retrieval-Augmented Generation)** architecture patterns, **text embeddings** (OpenAI ada-002, later text-embedding-3-small), and **vector databases** (pgvector extension for PostgreSQL) to understand how to build semantic search and context-aware Q&A systems for future projects

**Runday Platform (Veedoo's 9-year ongoing project):**
- **Challenge:** Runday is a free, community-based running initiative that brings people together every Saturday morning for a friendly 5km run, jog, or walk. As participation grew, so did the need for a robust digital infrastructure to support community engagement, streamline event coordination, and enhance the experience for both runners and organisers.
- **Solution:** Designed and developed a scalable, multilingual platform tailored to the needs of grassroots sports communities. Built a custom community management system, a reliable race timing solution, and a user-friendly mobile app. Supported brand development through graphic design, social media marketing, and automated newsletters.
- **Impact:** Runday has grown into a vibrant network of more than 18,000 runners across multiple countries, with over 5,000 events organised to date.
- **Client Testimonial:** *"The company's dedication to excellence is reflected in every aspect of their work. The successful completion of the 'Runday' project, within budget and timeline, is a testament to Veedoo's high standards."* — Alona Lashchenko, Runday

**3. Supabase Exploration**
- Used **Supabase** for a Veedoo client project, evaluating the full stack: PostgreSQL with Row Level Security (RLS) policies for fine-grained access control, GoTrue for authentication (email/password, OAuth providers), Supabase Storage (S3-compatible object storage with RLS), Realtime (WebSocket-based subscriptions for live data sync), and PostgREST (auto-generated REST API from the database schema). Appreciated the developer experience — especially RLS policies that move authorization logic to the database layer — but noted pricing concerns for production use at scale
- Since EUvsDisinfo requires self-hosting on EU-based servers (as an EU-funded project, all data must remain within EU jurisdiction), began exploring **self-hosted Supabase** as an alternative to the SaaS offering

**Self-Hosting & Coolify Adoption (Beginning of a Major Shift):**

This year marked the beginning of a fundamental shift in infrastructure philosophy. After working with Supabase's SaaS offering and recognizing both its excellent developer experience and its pricing limitations, began exploring self-hosted alternatives — especially since EUvsDisinfo requires all infrastructure to be hosted on EU-based servers as an EU-funded project.

- Discovered **Coolify** — an open-source, self-hosted PaaS (Platform as a Service) that provides a Heroku/Vercel-like deployment experience on your own servers. Coolify handles Docker container orchestration, automatic SSL certificates (Let's Encrypt), reverse proxy configuration (Traefik), environment variable management, GitHub/GitLab webhook-based auto-deployments, and database provisioning — all through a web UI
- Began experimenting with deploying projects on Coolify, running on **Hetzner Cloud** servers (chosen for excellent price-performance ratio, EU data centers, and NVMe SSD storage). Learned to manage Docker Compose-based service stacks, configure Traefik routing rules, set up health checks and automatic restarts, and manage persistent volumes for databases
- By end of year, had several Veedoo internal projects running on self-hosted Coolify infrastructure, replacing various SaaS subscriptions
- Started self-hosting **n8n** (workflow automation platform) on Coolify for automating repetitive tasks: monthly invoice generation, automated email notifications, data pipeline orchestrations, and webhook-based integrations between services
- Began learning bare-metal server management: SSH hardening, firewall configuration (UFW/iptables), automated backups (restic to S3-compatible storage), monitoring (Prometheus/Grafana basics), and log aggregation
- This exploration laid the groundwork for what would become a core competency — over the following two years, **Coolify became the default deployment platform for all Veedoo and client projects**, hosting everything from Next.js applications to self-hosted Supabase instances, Trigger.dev workers, n8n automation workflows, and more

**Professional Development:**
- Completed courses on **NestJS** (understanding the Angular-inspired, decorator-based, module-driven architecture for building scalable Node.js backend services — controllers, providers, guards, interceptors, pipes, and the dependency injection system)
- Completed advanced **TypeScript** courses covering: advanced generics and conditional types, mapped types and template literal types, discriminated unions for type-safe state machines, the `infer` keyword for type extraction, module augmentation, and declaration merging
- Completed **PostgreSQL** courses covering: query optimization (EXPLAIN ANALYZE, index types — B-tree, GIN, GiST, BRIN), partitioning strategies, window functions, CTEs (Common Table Expressions), materialized views, PL/pgSQL stored procedures, and connection pooling (PgBouncer)
- Deepened understanding of RAG, embeddings, and AI application architecture through both study and the Runday "Chat with our DB" implementation

---

#### 2025 — CTO Promotion, ML/AI Video Processing & Developer Enablement (at Veedoo)

**Promoted to CTO (Mid 2025)**

A landmark year — promoted to CTO and took on the most technically ambitious project to date, involving machine learning, GPU computing, and video processing. Also focused on empowering the entire Veedoo development team with AI tools and workflows. By this point, **Coolify had become the standard deployment platform** across all Veedoo projects — every new project and most existing ones were running on self-hosted Coolify infrastructure on Hetzner Cloud servers, from Next.js applications and self-hosted Supabase instances (using custom Docker Compose templates with tuned PostgreSQL configs) to Trigger.dev background job workers, n8n automation workflows, Postiz social media management, and various internal tools. This eliminated monthly SaaS costs across multiple services and gave full control over scaling, data residency, and uptime.

**Key Projects:**

**1. EUvsDisinfo — Continued Development**
Ongoing maintenance and feature development for Veedoo's flagship EU project. Continued to evolve the Disinformation Management System, optimize content delivery for the public-facing site (serving millions of annual users), and ensure compliance with evolving EU digital regulations.

**2. Community Platform (Skool.com Clone) with Built-in AI Tools**
- Built a full community/learning platform for a Veedoo client, inspired by Skool.com's model of combining community discussion, courses, and membership management into a single platform
- **Technical Architecture:** Next.js App Router with React Server Components for the frontend, self-hosted Supabase for the backend (PostgreSQL with RLS policies for community-level data isolation, Realtime for live discussions, Storage for media uploads). Built with a multi-tenant architecture where each community creator gets an isolated data scope enforced at the database level via RLS
- Integrated AI tools directly into the platform: AI-powered content summarization (for long discussion threads), AI-assisted course content generation, and smart content moderation using the OpenAI Moderation API
- Implemented **Stripe** for subscription billing and **Stripe Connect** (Standard accounts) for marketplace-style payouts — community creators set their own prices, the platform takes a percentage, and Stripe Connect handles the complex multi-party payment routing, tax reporting (1099-K), and payout scheduling automatically
- Built a webhook-driven payment lifecycle: `checkout.session.completed` → provision access, `invoice.payment_failed` → grace period + dunning emails, `customer.subscription.deleted` → revoke access. All webhook events are verified using Stripe's webhook signature verification and processed idempotently

**3. ParliamentConnect (parliamentconnect.com) — Solo Build**

> *A platform that automatically discovers, transcribes, and publishes parliamentary speeches across all social media platforms.*

Built this entire project solo — both frontend and backend — representing the most technically complex project of the career to date. This project required learning Python ML/AI tooling, GPU computing with CUDA, and video/audio processing from scratch.

**System Architecture Overview:**

```
Parliament Video Source
        │
        ▼
  Supabase Trigger (new session detected)
        │
        ▼
  RunPod Serverless Function (NVIDIA RTX PRO 6000)
        │
        ├─► Download parliament session video
        │
        ├─► Speaker Diarization (pyannote.audio)
        │   └─► Timestamps + unique speaker IDs (voice embeddings)
        │
        ├─► Transcription (Whisper)
        │   └─► Text for each diarized segment
        │
        ├─► Active Speaker Detection (custom pipeline)
        │   └─► Face detection per video frame (RetinaFace/MTCNN)
        │   └─► Lip-sync analysis to identify who is speaking
        │
        ├─► Face Recognition (face_recognition / InsightFace)
        │   └─► Match detected faces against MP database
        │   └─► Confidence scoring + manual review threshold
        │
        └─► Update Supabase with attributed clips
                │
                ▼
        Next.js Frontend (user-facing platform)
                │
                ▼
        Postiz API (self-hosted) → Social Media Publishing
```

**Frontend & Backend:**
- **Next.js** with App Router, React Server Components, and Server Actions for mutations (avoiding a separate API layer). Used Streaming SSR with Suspense for fast initial loads while heavy data fetches complete in the background
- **Self-hosted Supabase** for: PostgreSQL database (with RLS policies for user-level data access), GoTrue authentication (email/password + OAuth), Realtime subscriptions (WebSocket-based live updates when new clips are processed), and Storage (for video clip files, MP photos, and thumbnails)
- **Supabase Database Triggers:** PostgreSQL triggers + `pg_net` extension to make HTTP calls to RunPod's serverless API when new parliament session records are inserted — eliminating the need for a polling mechanism

**Video Processing Pipeline — Technical Deep Dive (Python + CUDA):**

This was an entirely new domain. Built a Python-based ML pipeline running on **RunPod serverless** infrastructure with **NVIDIA RTX PRO 6000** GPUs (48GB VRAM):

1. **Video Download & Pre-processing:** Downloads full parliament session videos (often 2-8 hours long), extracts audio track (FFmpeg), and splits video into frames for visual analysis

2. **Speaker Diarization** (using **pyannote.audio**):
   - Processes the extracted audio through a pre-trained neural network that segments the audio into speaker turns
   - Produces timestamps for every spoken segment with unique speaker embeddings (voice fingerprints)
   - Runs on GPU for accelerated inference — a 4-hour session is diarized in ~10-15 minutes on the RTX PRO 6000
   - Output: `[(start_time, end_time, speaker_id), ...]` where speaker_id is consistent within a session

3. **Transcription** (using **OpenAI Whisper**, large-v3 model):
   - Transcribes each diarized audio segment individually (rather than the full audio) for better accuracy and proper speaker attribution
   - Whisper runs locally on GPU via `faster-whisper` (CTranslate2 backend) for 4x faster inference compared to the standard PyTorch implementation
   - Supports multiple languages (parliament sessions may switch between languages)

4. **Active Speaker Detection (ASD)** — Custom Pipeline:
   - For each diarized segment, extracts video frames at the corresponding timestamps
   - Runs face detection on each frame using **RetinaFace** (or MTCNN as fallback) to detect all visible faces and their bounding boxes
   - Built a custom ASD process that correlates lip movement patterns with the audio signal to determine which detected face is the active speaker — this is critical because parliament sessions show multiple faces simultaneously (wide shots of the chamber, reaction shots, etc.)
   - The ASD module uses temporal analysis across multiple frames to build confidence scores for speaker-face associations

5. **Face Recognition** (using **face_recognition** library / **InsightFace**):
   - Takes the detected active speaker face and computes a 128-dimensional face embedding
   - Compares the embedding against a pre-built database of known Members of Parliament (built from official portrait photos, multiple angles where available)
   - Uses cosine similarity with configurable thresholds: high-confidence matches (>0.85 similarity) are auto-attributed, medium-confidence matches (0.70-0.85) are flagged for manual review, low-confidence matches (<0.70) are left unattributed
   - The face embedding database is stored in PostgreSQL with the **pgvector** extension for efficient similarity search

6. **Clip Generation & Database Update:**
   - For each identified speech segment: extracts the video clip (FFmpeg), generates a thumbnail, and uploads both to Supabase Storage
   - Updates the Supabase database with: MP attribution, transcript text, timestamps, confidence scores, and storage URLs
   - Sends a Supabase Realtime notification so the frontend updates live

**Results:** Achieved **98% accuracy** in speaker identification and attribution, with continuous improvement as more MP face images are added to the training database. The system processes a full parliament session end-to-end in approximately 30-45 minutes (depending on session length), compared to what would take a human team days of manual work.

**Social Media Integration:**
- Self-hosted **Postiz** (open-source social media management tool) on Coolify
- Integrated Postiz's REST API into the ParliamentConnect frontend, allowing users to connect their social media accounts (Twitter/X, Facebook, LinkedIn, Instagram) and schedule/publish parliamentary clips directly from the app
- Built the integration so users authenticate with ParliamentConnect only — the Postiz OAuth flows are handled server-side via API calls, so users never need to interact with the Postiz UI directly

**Tech Stack:** Next.js (App Router, RSC, Server Actions), Supabase (self-hosted — PostgreSQL, RLS, Realtime, Storage, pg_net, pgvector), Python 3.11, PyTorch, CUDA 12.x, pyannote.audio, faster-whisper, RetinaFace, face_recognition/InsightFace, FFmpeg, RunPod (serverless GPU — NVIDIA RTX PRO 6000), Postiz (self-hosted on Coolify)

**4. CTO Responsibilities — AI Enablement & Team Development:**
- Introduced AI automation across Veedoo to reduce time spent on repetitive monthly tasks (invoice generation, report compilation, content scheduling — all automated via n8n workflows with AI-assisted content generation)
- Created an **AI usage guide** for the team covering:
  - How to write effective prompts and system instructions for code generation
  - How to use **Claude Code** (Anthropic's CLI tool) for codebase-aware AI assistance — including setting up CLAUDE.md files for project-specific instructions, using MCP servers for tool integration, and effective context management strategies
  - Best practices for AI-assisted code review, debugging, and refactoring
- Set up appropriate **MCP (Model Context Protocol) servers** for each project — this gives AI coding assistants structured access to project-specific tools and data sources (databases, APIs, documentation) so they can provide contextually relevant assistance rather than generic responses
- Trained and mentored all developers on:
  - How to use AI-assisted development tools effectively — emphasizing that AI is a force multiplier, not a replacement, and that the quality of output depends on the quality of context provided
  - How to use **Cursor** IDE for AI-augmented coding — including its Composer feature for multi-file edits, the chat interface for codebase Q&A, and tab completion for inline suggestions
  - The importance of **context management** when working with AI tools — including CLAUDE.md files, .cursorrules files, proper code documentation, and maintaining clean, well-structured codebases that AI tools can reason about effectively
- Set up **Cursor BugBot** across all Veedoo repositories to automate code review — BugBot runs on every PR and provides AI-powered code review comments, catching bugs, suggesting improvements, and enforcing code quality standards automatically, reducing the manual code review burden on the team

---

### Baseloop — (Part-time, Remote)

**Founding Engineer** (November 2025 – Present)

Joined [Baseloop](https://baseloop.io) as a founding engineer, working alongside the CEO and Lead Developer Kevin to build and scale the product.

**Key Contributions — Technical Details:**
- Led the migration from SaaS-dependent infrastructure to a **fully self-hosted setup on Coolify**:
  - **Trigger.dev:** Migrated from Trigger.dev's SaaS offering to a self-hosted instance using a custom Docker Compose configuration (which later evolved into the open-source [coolify-trigger-v4](https://github.com/tao101/coolify-trigger-v4) template). This eliminated per-execution pricing and SaaS rate limits that were bottlenecking background job throughput
  - **Supabase:** Migrated from Supabase's SaaS to a self-hosted instance using a custom Coolify template (which later became [latest-supabase-coolify-template](https://github.com/tao101/latest-supabase-coolify-template)). Used the [supabase-sync](https://www.npmjs.com/package/supabase-sync) CLI tool (which was also built as a result of this migration) to perform the full data migration including database schema, data, auth users (with preserved password hashes), and storage files
  - The self-hosted infrastructure runs on Hetzner Cloud servers, reducing monthly infrastructure costs significantly compared to the combined SaaS bills
- Eliminated SaaS limitations that were slowing down development velocity — no more worrying about Trigger.dev's execution limits, Supabase's connection pooling limits on the free/pro tier, or storage quota restrictions
- The self-hosted infrastructure enabled faster development cycles with full control over database configuration (custom PostgreSQL tuning, connection pool sizes), background job concurrency, and deployment cadence

**Tech Stack:** CedarJS (TypeScript framework — batteries-included with built-in ORM, auth, queues, and GraphQL API layer, similar in philosophy to Laravel but for the TypeScript ecosystem), self-hosted Supabase, self-hosted Trigger.dev, Coolify on Hetzner Cloud

**Personal Notes:** Picked up CedarJS quickly despite no prior experience — the framework's convention-over-configuration approach and Laravel-like patterns (models, migrations, seeds, middleware, guards) made it intuitive for someone familiar with MVC architectures. Appreciated the batteries-included philosophy: built-in TypeScript ORM with migrations, authentication system, job queues, and auto-generated GraphQL API — though personally found GraphQL's verbosity less appealing compared to REST or tRPC for most use cases.

---

#### 2026 — Current (at Veedoo & Baseloop)

Continuing work across both roles — maintaining and evolving the projects and platforms built in 2025, iterating on improvements, and expanding capabilities. All infrastructure continues to run on self-hosted Coolify across Hetzner Cloud servers, with ongoing optimization of PostgreSQL performance, container resource allocation, and backup strategies.

---

## Freelance Work (Pre-Veedoo)

### Freelance React Native Developer — Kharkiv, Ukraine (2017 – 2019)

While studying for a Bachelor of Science in Computer Engineering at Kharkiv National University of Radio Electronics, worked as a freelance React Native mobile developer, building cross-platform mobile applications for various clients.

**Tech Stack:** React Native 0.55-0.60, JavaScript (ES6+), React Navigation, AsyncStorage, native module bridging, REST API integration, Redux for state management, Firebase (authentication, cloud messaging, analytics)

**Key Technical Experience:**
- Built cross-platform apps (iOS + Android) from a single codebase, handling platform-specific differences through conditional code and native module bridging
- Implemented offline-first patterns with AsyncStorage and background sync for apps that needed to work in areas with unreliable connectivity
- Managed the full app lifecycle: development, testing (on physical devices and simulators), app store submission (App Store Connect + Google Play Console), and post-launch updates via CodePush for over-the-air JavaScript bundle updates

### Freelance Android Developer — Morocco (2014 – 2017)

While studying at Universit Ibn Zohr, worked as a freelance Android application developer, building native Android apps using Java.

**Tech Stack:** Java, Android SDK (API levels 19-25), SQLite (local database), RESTful API integration (Retrofit, OkHttp), XML layouts, Material Design components, Google Maps API, Firebase (Cloud Messaging, Analytics), Git

**Key Technical Experience:**
- Built native Android applications using Java with the Android SDK, following Google's Material Design guidelines
- Implemented local data persistence with SQLite databases and ContentProviders for inter-app data sharing
- Consumed RESTful APIs using Retrofit with OkHttp for network calls, Gson for JSON serialization, and implemented caching strategies for offline access
- Handled the Android activity/fragment lifecycle, background services, broadcast receivers, and push notifications via Firebase Cloud Messaging
- Published apps to the Google Play Store, managing the full release cycle including signing, ProGuard obfuscation, and staged rollouts

---

## Additional Veedoo Project: Go Help Now

> *A multinational humanitarian startup non-profit which helps volunteers find a project for cooperation.*

- **Challenge:** Go Help Now, a multinational humanitarian startup, set out to create a digital platform that empowers people to respond quickly and meaningfully during crises. The organization needed to build a trusted, user-friendly brand and web platform that connects volunteers with urgent projects, facilitates cash donations, and provides access to safe housing solutions.
- **Solution:** Developed the organization's visual identity and branding. Created a comprehensive information architecture and modular design system supporting three core functions: volunteer matching, donation processing, and housing coordination. Built with usability and accessibility in mind, with usability testing across international users.
- **Impact:** The platform launched as a centralized hub for humanitarian action, enabling thousands of users to connect with meaningful volunteer opportunities and provide financial or housing assistance during times of crisis. Increased volunteer engagement and donor conversion rates.
- **Client:** Go Help Now — Nonprofit / Volunteering / Humanitarian Aid
- **Services:** Branding, Web Platform Development, Usability Testing, Informational Architecture, Design System, Product Design
- **Duration:** 2 years

---

## Open Source Projects

Built and published open-source tooling to solve real problems encountered while self-hosting infrastructure with Coolify — helping other developers adopt self-hosted stacks more easily. These projects were born from practical needs across Veedoo and Baseloop work.

### [Self-Hosted Next.js & Supabase Fullstack Starter Template](https://github.com/tao101/Self-Hosted-Next.js-Supabase-Fullstack-Starter-Template)

A production-ready starter template for building modern web applications with Next.js and self-hosted Supabase, optimized for deployment on Coolify. Born from the patterns and architecture refined across multiple Veedoo and client projects (ParliamentConnect, Community Platform, etc.).

**Key Features:**
- Full-stack architecture with Next.js App Router (React 19 with Server Components, TypeScript in strict mode, Shadcn UI component library, Legend State for reactive state management with fine-grained reactivity and automatic persistence)
- Self-hosted Supabase instance with automated database migrations (via Supabase CLI), Row Level Security (RLS) policies for fine-grained access control, Auth (email/password + OAuth providers), Storage (S3-compatible with RLS), and Realtime (WebSocket subscriptions)
- Enterprise-grade security patterns: role-based access control enforced at the database level via RLS, CSRF protection, secure HTTP-only cookies, Content Security Policy headers, and input validation with Zod
- Built-in observability with Sentry monitoring (error tracking, performance monitoring, session replays)
- Auto-generated API documentation via Swagger/OpenAPI (using next-swagger-doc)
- Comprehensive testing suite: Playwright for E2E tests (with page object model pattern), Jest for unit tests
- Real-time capabilities out-of-the-box via Supabase Realtime subscriptions
- Includes full architecture documentation, developer guide, and Coolify deployment guide with environment-specific configurations

**Tech Stack:** Next.js 14+, React 19, TypeScript (strict), Shadcn UI, Tailwind CSS, Supabase (self-hosted), Legend State, Zod, Playwright, Jest, Sentry, Swagger/OpenAPI

### [Coolify Trigger.dev v4](https://github.com/tao101/coolify-trigger-v4)

Docker Compose configurations for self-hosting Trigger.dev v4 on Coolify — providing a complete setup for running background jobs, scheduled tasks, and workflow automation without relying on Trigger.dev's SaaS offering. This project was born from the Baseloop migration and refined through production use.

**Key Features:**
- Complete self-hosted Trigger.dev v4 setup: web application, PostgreSQL (primary database), Redis (caching and session storage), ElectricSQL (real-time database synchronization), ClickHouse (analytics and event storage for high-throughput write workloads), private Docker registry (for deploying worker code), MinIO (S3-compatible object storage for packages and assets), and Supervisor (manages worker execution and Docker operations)
- **Three deployment options:**
  - **Distributed (Recommended for production):** Separates webapp + databases from workers across multiple servers. Enables horizontal scaling — add worker servers independently as workload grows. Workers crash independently without affecting the webapp. Includes security hardening, resource limits (Docker memory/CPU constraints), log rotation, and NVMe-optimized I/O settings
  - **Single Server:** All services on one machine — suitable for development and testing
  - **External Databases:** Use Coolify's managed PostgreSQL/Redis instead of bundled ones
- Pre-configured for **4 server tiers** (4/8/16/32 vCPU) on Hetzner Cloud with optimized resource allocation per tier
- Automatic HTTP Basic Auth for the Docker registry using Coolify's auto-generated `SERVICE_PASSWORD_REGISTRY` variable
- Automatic worker token generation and distribution via shared Docker volumes (single-server) or manual one-time setup (distributed)
- Quick Start guide for Coolify v4: link the GitHub repo for auto-updates, or copy-paste the Docker Compose directly

**Services:** Web App (Port 3000), PostgreSQL, Redis, ElectricSQL, ClickHouse, Docker Registry (Port 5000), MinIO, Supervisor

### [Supabase Sync Script](https://github.com/tao101/supabase-sync-script) (Published on npm as `supabase-sync`)

A CLI tool to perform full one-time migrations between Supabase instances — solving the real problem of migrating from Supabase SaaS to self-hosted (or between self-hosted instances) without losing data, auth users, or storage files. Built out of necessity during the Baseloop migration and used across multiple Veedoo projects.

**Key Features:**
- **Full migration support:**
  - **Database schema:** Tables, functions, triggers, RLS policies — exported via `pg_dump` with schema-only mode, filtered to exclude Supabase's internal schemas (`auth`, `storage`, `realtime`, etc. are handled separately)
  - **Database data:** Full data migration using PostgreSQL's COPY format for high-performance bulk inserts (orders of magnitude faster than INSERT statements)
  - **Sequence reset:** Automatically resets all sequences after data import to prevent primary key conflicts on new inserts — a subtle but critical step that's easy to miss in manual migrations
  - **Auth users:** Migrates users from Supabase's `auth.users` table, **preserving bcrypt password hashes** so users can log in with their existing credentials on the new instance without needing to reset passwords
  - **Storage:** Migrates buckets and files with concurrent uploads (configurable concurrency) for performance
  - **Roles:** Database roles with proper filtering of Supabase's built-in system roles
- **Two modes:** Interactive (guided prompts with connection testing at each step) and CI (automated via environment variables or JSON config file, suitable for CI/CD pipelines)
- Dry run mode to preview all changes without applying them
- Connection testing that validates database URLs immediately after input (catches misconfigured URLs early)
- Supports all migration paths: SaaS→self-hosted, SaaS→local, self-hosted→self-hosted, self-hosted→local

**Published:** [npmjs.com/package/supabase-sync](https://www.npmjs.com/package/supabase-sync)
**Tech Stack:** Node.js, PostgreSQL client tools (pg_dump, psql), Supabase Management API, Commander.js (CLI framework), Inquirer.js (interactive prompts)

### [Latest Supabase Coolify Template](https://github.com/tao101/latest-supabase-coolify-template)

A Docker Compose template for deploying the latest Supabase stack on Coolify with automatic JWT/API key generation — solving the problem of Coolify's built-in Supabase template being outdated and lacking production-ready configurations.

**Key Features:**
- Deploys the **full Supabase stack** (12 services): Kong (API Gateway — routes all API requests), Studio (admin dashboard UI), Auth/GoTrue (authentication service — email/password, OAuth, magic links), PostgREST (auto-generated REST API from PostgreSQL schema), Realtime (WebSocket server for live subscriptions), Storage (S3-compatible file storage API), PostgreSQL 15 (primary database), MinIO (S3-compatible object storage backend for Supabase Storage), Supavisor (Elixir-based connection pooler — replacement for PgBouncer), and Analytics/Logflare (logging and analytics)
- **Automatic secure credential generation** using Coolify's magic environment variables — `SERVICE_PASSWORD_JWT` generates the JWT secret, and the anonymous/service role API keys are valid JWTs signed with this secret (generated at container startup). PostgreSQL passwords, admin credentials, and all inter-service secrets are also auto-generated. No manual secret management required
- **Two configurations:**
  - **Development/Staging** (`docker-compose.yml`): Default settings, suitable for any server
  - **Production** (`docker-compose.8vcpu-32gb-ccx33-production.yml`): Optimized for Hetzner CCX33 (8 vCPU, 32GB RAM, NVMe SSD) with:
    - **PostgreSQL tuning:** `shared_buffers=8GB` (25% RAM), `effective_cache_size=24GB` (75% RAM), `work_mem=64MB`, `max_parallel_workers=8` (matching vCPU count), `random_page_cost=1.1` (NVMe optimization — tells the query planner that random I/O is nearly as cheap as sequential I/O on SSDs), moderate autovacuum settings for large tables, and slow query logging (queries >1s)
    - **Connection pooling (Supavisor):** Pool size 50 (default 20), max clients 1000 (default 100), DB pool 25 (default 5)
    - **Realtime:** File descriptors increased to 20000 (default 10000) for handling more concurrent WebSocket connections
    - Designed for **200-500 concurrent users** with **10GB+ databases** and **millions of rows**
- One-click deployment: paste Docker Compose in Coolify and deploy — Coolify handles SSL, reverse proxy, and DNS routing automatically

**Services:** Kong (API Gateway, Port 8000), Studio (Port 3000), Auth/GoTrue (Port 9999), PostgREST (Port 3000), Realtime (Port 4000), Storage (Port 5000), PostgreSQL (Port 5432), MinIO (Port 9000), Supavisor (Port 4000), Analytics/Logflare (Port 4000)

---

## Technical Skills

### Languages
JavaScript (ES6+), TypeScript (strict mode, advanced generics, conditional types, discriminated unions), Python 3.x (ML/AI pipelines, data processing), PHP (MVC/Laravel patterns), Java (Android SDK), SQL (PostgreSQL, MySQL), HTML5, CSS3

### Frontend
React 18/19 (Server Components, Suspense, concurrent features), Next.js 13-15 (App Router, Pages Router, SSR, SSG, ISR, Server Actions, Streaming, Middleware), React Native 0.60+ / Expo (managed workflow, EAS builds), Tailwind CSS, Shadcn UI, Legend State (reactive state management), Redux, React Query/TanStack Query

### Backend
Node.js 18+ (ESM, Workers, Streams), Express 4.x (middleware, routing, error handling), NestJS (modules, providers, guards, interceptors, dependency injection), Next.js API Routes & Server Actions, PHP (MVC), Python (FastAPI basics, scripting, ML pipelines)

### Databases & ORMs
PostgreSQL 14-16 (RLS, pg_net, pgvector, PL/pgSQL, partitioning, window functions, CTEs, EXPLAIN ANALYZE optimization), MongoDB (aggregation pipelines, Mongoose ODM), Supabase (hosted & self-hosted — Auth, Storage, Realtime, PostgREST, RLS policies), Neon (serverless Postgres, DB branching), Drizzle ORM (type-safe SQL), MySQL, SQLite

### CMS & Content
Sanity v2 & v3 (GROQ queries, custom Studio plugins, document actions, webhooks, real-time collaborative editing), Jamstack architecture (headless CMS + static generation + serverless functions)

### AI & Machine Learning
OpenAI GPT API (GPT-3.5/4, function calling, embeddings — ada-002, text-embedding-3-small), RAG (Retrieval-Augmented Generation) pipelines, Vector databases (pgvector), Text-to-SQL pipelines, PyTorch, CUDA 12.x (GPU computing on NVIDIA RTX PRO 6000), pyannote.audio (speaker diarization), faster-whisper (speech-to-text), RetinaFace/MTCNN (face detection), face_recognition/InsightFace (face recognition with embedding similarity search), FFmpeg (video/audio processing), OpenAI Moderation API

### DevOps & Infrastructure
Docker (Dockerfile, multi-stage builds), Docker Compose (multi-service orchestration), **Coolify** (primary self-hosted PaaS — deployed and managed Next.js apps, Supabase, Trigger.dev, n8n, Postiz, and more across production environments), Vercel (serverless hosting, edge network, preview deployments), RunPod (serverless GPU computing), Hetzner Cloud (EU data centers, NVMe servers — CCX/CX series), Traefik (reverse proxy, auto SSL via Let's Encrypt), Nginx, Linux server administration (SSH hardening, UFW/iptables, systemd, log management), n8n (self-hosted workflow automation), Postiz (self-hosted social media management), Trigger.dev (self-hosted background jobs & scheduled tasks), restic (encrypted backups to S3-compatible storage)

### Payments
Stripe (subscriptions, one-time payments, webhook lifecycle handling), Stripe Connect (Standard accounts — multi-party marketplace payments, automated payouts, tax reporting)

### Analytics & Testing
PostHog (self-hosted analytics, feature flags, A/B testing, session replays, funnels), Sentry (error tracking, performance monitoring), Playwright (E2E testing, page object model), Jest (unit testing), Lucia-Auth (session-based authentication), Zod (runtime type validation, schema-first API design)

### Tools & Workflow
Git (branching strategies, interactive rebase, cherry-pick), Claude Code (Anthropic CLI — CLAUDE.md project instructions, MCP server integration), Cursor IDE (Composer, chat, tab completion, .cursorrules), MCP (Model Context Protocol — connecting AI tools to project-specific data sources), Cursor BugBot (automated AI code review on PRs), Fibery.io (custom CRM/project management), OpenTimestamps (blockchain-based cryptographic timestamping for evidence preservation), Puppeteer/Cheerio (web scraping), Swagger/OpenAPI (API documentation)

---

## Key Highlights

- **CTO at Veedoo** — Leading technical strategy, AI adoption, and developer mentoring at a European digital consultancy serving EU institutions and nonprofits
- **Humanitarian Impact** — Built Ukraine Shelter in 3 days after the Russian invasion (domain registered Feb 25, launched Feb 27, 2022); maintained Lifeline Ukraine's suicide prevention platform during wartime (1,500+ monthly chat users)
- **EU-Scale Impact** — Key developer on EUvsDisinfo for the European External Action Service (19,000+ documented disinformation cases, millions of annual users, 13 languages, blockchain-timestamped evidence)
- **Solo Product Engineering** — Scaled EveryRun from 80 to 17,659 users as the sole developer, with Neon DB branching for isolated preview environments
- **ML/Video Processing** — Built ParliamentConnect's end-to-end video processing pipeline (speaker diarization, transcription, face detection, face recognition) achieving 98% accuracy, running on NVIDIA RTX PRO 6000 GPUs via RunPod serverless
- **Self-Hosting Advocate** — Migrated all company infrastructure to self-hosted Coolify on Hetzner Cloud (Supabase, Trigger.dev, n8n, Postiz, and more); published 4 open-source tools to help others do the same, including an npm package (`supabase-sync`) for full Supabase instance migrations
- **AI Enablement** — Trained entire development team on AI-assisted workflows; set up Claude Code with CLAUDE.md project instructions, Cursor IDE with .cursorrules, MCP servers for project-specific AI context, and Cursor BugBot for automated code review across all repositories
- **Open Source Contributor** — Published production-tested Docker Compose templates and CLI tools for the Coolify/Supabase/Trigger.dev self-hosting ecosystem
