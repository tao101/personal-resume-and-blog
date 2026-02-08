# Brainstorm: 2 Standalone Blog Posts — Self-Hosting Journey & ParliamentConnect Architecture

**Date:** 2026-02-08
**Author:** Taoufiq Lotfi

---

## What We're Building

Two standalone deep-dive blog posts, loosely connected to the existing 5-post career series but focused on specific topics rather than career chapters.

---

## Key Decisions

- **Tone:** Same as the career series — mix of personal storytelling and technical insights. Conversational, short paragraphs, first person.
- **Relationship to series:** Standalone but can reference the career posts (e.g., "as I wrote about in my career series...").
- **Length target:** ~2000-3000 words each. These are deep-dives, slightly longer than the career posts.

---

## Post 6: "Why I Self-Host Everything Now — And Why You Should Too"

### Angle

Practical guide + personal story. Lead with the journey (compliance forced my hand → discovered Coolify → went all-in), back it up with **real cost comparisons** using actual pricing, and close with the "everything as code" philosophy for the AI era.

### Hook

"I used to pay $700+/month in SaaS fees for a single project — Supabase 2XL compute at $410, Trigger.dev Pro at $210+ just for the concurrency we needed, plus per-second compute charges on top. Now I run the same stack — and more — for about €205/month on my own servers. But the 70% cost savings isn't even the main reason I self-host everything."

### Story Arc

1. **How it started — compliance, not choice:**
   - EUvsDisinfo (EU-funded) requires all data on EU servers. No US-hosted SaaS allowed.
   - This forced exploration of self-hosting alternatives in 2024.
   - Discovered Coolify — open-source, self-hosted PaaS. Heroku/Vercel-like experience on your own servers.

2. **The first migration — Supabase:**
   - Was using Supabase SaaS (2XL compute add-on at ~$410/mo) for Baseloop.
   - Also paying for Trigger.dev SaaS ($50/mo base + usage).
   - Hit limits: connection pooling caps, rate limits, storage quotas, pricing tiers that didn't scale with needs.
   - Migrated to self-hosted Supabase on Hetzner Cloud.

3. **The real cost comparison:**

   **Before (SaaS):**
   - Supabase Pro + 2XL compute add-on: ~$410/mo
   - Trigger.dev Pro: $50/mo base (includes only 200 concurrent runs)
   - Trigger.dev extra concurrency to reach 1000: 800 more / 50 per bundle = 16 × $10 = $160/mo
   - Trigger.dev compute charges: billed per second based on machine tier (e.g., Small 1x at $0.0000338/sec, Medium 2x at $0.0001700/sec, Large 2x at $0.0006800/sec) — adds up fast with 1000 concurrent runs
   - Trigger.dev run invocation fees: $0.25 per 10,000 runs
   - **Conservative total: ~$700-800+/mo** (for ONE project)
   - Plus: rate limits, connection caps, storage quotas, someone else controlling your scaling

   **After (Self-Hosted on Hetzner Cloud):**
   - CCX43 (16 vCPU, 64GB RAM) for Supabase: €96.49/mo
   - CPX52 (12 vCPU, 24GB RAM) for Trigger.dev webapp: €28.49/mo
   - 4x CPX42 (8 vCPU, 16GB RAM each) for Trigger.dev workers: €79.96/mo (4 × €19.99)
   - **Total: ~€205/mo (~$220/mo)**
   - Plus: no rate limits, no connection caps, custom PostgreSQL tuning, 1000+ concurrent Trigger runs, unlimited compute time, full control

   **Savings: ~$500-600+/mo (70%+ reduction) with MORE capability**

   Sources: [Supabase Pricing](https://supabase.com/pricing), [Trigger.dev Pricing](https://trigger.dev/pricing), [Hetzner Cloud](https://www.hetzner.com/cloud)

4. **It's not just about cost — it's about control:**
   - Custom PostgreSQL tuning (shared_buffers, work_mem, NVMe optimization). Try that on Supabase SaaS.
   - Need more concurrent Trigger.dev workers? Add a server. No waiting for tier upgrades.
   - No vendor can rug-pull your pricing. No SaaS can deprecate the feature you depend on.
   - No outage on someone else's platform takes your product down.
   - Data residency — you choose where your data lives. Period.

5. **The tools I built along the way:**
   - supabase-sync (npm) — full Supabase instance migration CLI (schema, data, auth users with preserved passwords, storage)
   - Coolify Trigger.dev v4 template — Docker Compose for self-hosting Trigger.dev
   - Latest Supabase Coolify Template — production-ready Supabase on Coolify
   - None of these were planned. Built them because they didn't exist.

6. **Self-hosting in the AI era — everything as code:**
   - Key insight: with AI coding tools (Claude Code, Cursor), having your entire infrastructure defined in code (Docker Compose files, env configs, deployment scripts, monitoring configs) in the repo means AI can understand your full system.
   - No clicking around external dashboards. No context that only lives in a SaaS UI.
   - The AI assistant can read your docker-compose.yml and understand every service, every connection, every config.
   - Everything version-controlled. Everything reviewable. Everything AI-readable.
   - Self-hosting enables this naturally — your infrastructure IS your codebase.

7. **Coolify and what's next — Dokploy:**
   - Coolify has been the workhorse. Recommend it explicitly.
   - But recently started exploring Dokploy — likes their Docker Swarm setup for zero-downtime deployments.
   - Dokploy's approach: health checks + Swarm rolling updates + automatic rollback on failure.
   - Not switching from Coolify, but dipping feet in Dokploy for specific use cases.

8. **The philosophy:**
   - Self-hosting is a philosophy, not just a cost optimization.
   - When you control your infrastructure, you control your destiny.
   - If something goes wrong, YOU can spend time fixing it. On SaaS, you open a ticket and wait.
   - It wins on every axis: cost, control, data ownership, AI compatibility, debugging ability.

### Closing Reflection

Self-hosting started as a compliance requirement and became a core belief. The combination of Coolify + Hetzner Cloud + Docker Compose gives you the same DX as Vercel/Heroku with full ownership. And in the AI era, having everything as code in your repo isn't just nice — it's a competitive advantage.

### Links/CTA

- All 4 open source repos
- Hetzner Cloud referral (if applicable)
- Coolify website
- Dokploy website
- Invite readers to share their self-hosting journey

---

## Post 7: "How I Built an ML Pipeline That Identifies Politicians with 98% Accuracy — Solo"

### Angle

Architecture deep-dive. Full product context (what ParliamentConnect does and why it exists), then a detailed walkthrough of the ML pipeline architecture — the stages, the data flow, the design decisions, and how each piece connects to the next. Focus on HLD/LLD thinking, not code snippets.

### Hook

"In 2025, I took on the most technically ambitious project of my career. I had zero experience with Python ML, CUDA, or GPU computing. The result: a system that processes 8-hour parliament sessions and correctly identifies who said what with 98% accuracy, in under 45 minutes."

### Story Arc

1. **What ParliamentConnect does:**
   - Platform that automatically discovers, transcribes, and publishes parliamentary speeches.
   - Takes full parliament session videos (2-8 hours long), processes them through an ML pipeline, and produces attributed clips — who said what, with text transcription.
   - Users can then share clips directly to social media via integrated Postiz.
   - Why this matters: transparency, accessibility, public engagement with parliamentary proceedings.

2. **The challenge — why this is hard:**
   - Parliament sessions show multiple people. Camera cuts between speakers, reaction shots, wide chamber views.
   - You can't just "transcribe the audio" — you need to know WHO is speaking at every moment.
   - Multiple languages in a single session (depending on parliament).
   - Videos are 2-8 hours long. Processing must be efficient.
   - You need to match faces against a database of known MPs. New MPs join, faces change over time.

3. **The architecture overview (the pipeline):**

   ```
   Parliament Video Source
           │
           ▼
     Supabase DB Trigger (new session detected)
           │
           ▼
     RunPod Serverless Function (NVIDIA RTX PRO 6000, 96GB VRAM)
           │
           ├─► Download full session video
           │
           ├─► Extract audio track (FFmpeg)
           │
           ├─► Speaker Diarization (pyannote.audio)
           │   └─► Output: [(start, end, speaker_id), ...]
           │   └─► Voice embeddings create consistent speaker IDs within session
           │
           ├─► Transcription (faster-whisper, large-v3)
           │   └─► Each diarized segment transcribed individually
           │   └─► 4x speed vs standard Whisper (CTranslate2 backend)
           │
           ├─► Active Speaker Detection (custom)
           │   └─► Face detection per frame (RetinaFace)
           │   └─► Lip-sync + temporal analysis → who is actually speaking
           │
           ├─► Face Recognition
           │   └─► 128-dim face embedding vs MP database (pgvector)
           │   └─► Cosine similarity with confidence thresholds
           │   └─► >0.85 = auto-attribute, 0.70-0.85 = manual review, <0.70 = skip
           │
           ├─► Clip extraction (FFmpeg) + thumbnail generation
           │
           └─► Update Supabase (attributed clips, transcripts, confidence scores)
                   │
                   ▼
           Next.js Frontend (real-time updates via Supabase Realtime)
                   │
                   ▼
           Postiz API (self-hosted) → Social Media Publishing
   ```

4. **Design decisions — why each piece:**
   - **Why pyannote.audio for diarization:** Pre-trained neural network, GPU-accelerated, produces voice embeddings that are consistent within a session. A 4-hour session diarized in ~10-15 min on RTX PRO 6000.
   - **Why faster-whisper over standard Whisper:** CTranslate2 backend gives 4x speed improvement. When processing hours of audio, this matters enormously. Same accuracy.
   - **Why a custom ASD pipeline:** Parliament footage isn't a 1-on-1 interview. Multiple faces visible simultaneously. Need to correlate lip movement with audio signal across temporal frames to determine who is actually speaking.
   - **Why pgvector for face matching:** Face embeddings are 128-dimensional vectors. pgvector enables efficient cosine similarity search directly in PostgreSQL — no separate vector database needed. Keeps architecture simple.
   - **Why confidence thresholds:** Not everything should be auto-attributed. The 3-tier system (auto/review/skip) balances automation with accuracy. 98% accuracy comes from this calibrated approach.
   - **Why RunPod serverless:** Pay only for GPU time during processing. A parliament session takes 30-45 min of GPU time. No need to keep an expensive GPU server running 24/7.
   - **Why Supabase triggers → RunPod:** Event-driven architecture. No polling. pg_net extension makes HTTP calls directly from PostgreSQL triggers.

5. **The HLD/LLD lesson:**
   - This project crystallized the belief that architecture > code in the AI era.
   - AI tools (Claude) helped with Python implementation details. But NO AI designed this pipeline.
   - The value was understanding HOW these pieces connect:
     - How diarization output feeds into transcription input
     - How face detection in video frames maps to audio segments
     - How confidence scoring creates a feedback loop for accuracy improvement
     - How the data flows from video → structured database records → real-time frontend
   - Understanding the system from micro (individual ML model) to macro (full pipeline) was the skill that made this possible.

6. **The "zero to ML" context:**
   - Had zero Python ML, CUDA, or GPU experience before this project.
   - Trusted the pattern: after years of Android → React Native → Next.js → Supabase → Coolify, picking up new domains follows the same process. Research deeply, understand the architecture, design the system, then implement.
   - AI tools made the implementation faster than ever. But they couldn't design the pipeline.

7. **Results:**
   - 98% accuracy in speaker identification and attribution.
   - Full 8-hour parliament session processed in 30-45 minutes.
   - Work that would take a human team days.
   - Continuously improving as more MP face images are added.

### Technical Insights (architecture-level, no code)

- Event-driven pipeline design (DB triggers → serverless GPU functions)
- Speaker diarization → transcription → visual analysis data flow
- Multi-modal ML: audio (voice) + visual (face) + temporal (lip-sync) signals combined
- Confidence-based attribution with human review fallback
- pgvector for vector similarity search within existing PostgreSQL (no separate vector DB)
- RunPod serverless GPU economics (pay-per-use vs. always-on)

### Closing Reflection

ParliamentConnect proved that the hardest part of building complex systems isn't the code — it's the architecture. Understanding how ML models, databases, GPUs, and frontends connect into a coherent pipeline is the real skill. AI can help you implement each piece. But designing how the pieces fit together? That's still a human job. And it's the most important job.

### Links/CTA

- ParliamentConnect website
- Mention the self-hosting stack it runs on (tying back to Post 6)
- Invite readers to share their "zero experience in X, built Y" stories

---

## Publishing Order

1. **Post 6 (Self-Hosting)** — Published first. Sets up the infrastructure philosophy.
2. **Post 7 (ParliamentConnect)** — Published second. Can reference the self-hosting post ("as I wrote about in my self-hosting post, everything runs on Coolify...").

---

## Open Questions

- Do you want a visual diagram for the ParliamentConnect pipeline (beyond ASCII)?
- Should the self-hosting post include a "getting started" section for readers who want to try Coolify?
- Any Trigger.dev SaaS usage costs you remember beyond the $50/mo base? (usage-based charges for compute/runs)
