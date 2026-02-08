# Joining a Startup as Founding Engineer — My Baseloop Story

When you're already a CTO working full-time, joining a startup part-time as a founding engineer sounds crazy. Here's why I did it anyway.

---

## Why I Said Yes

In November 2025, I was 7 months into my CTO role at Veedoo. Leading technical strategy across multiple client projects, managing infrastructure, mentoring the team. Full plate. Full-time. No bandwidth to spare.

Then the Baseloop opportunity showed up, and I said yes immediately.

Three reasons.

**The startup energy.** At Veedoo, I build for clients. It's great work — meaningful projects, real impact. But consultancy work is fundamentally different from product work. You're building someone else's vision. At a startup, you're building the thing from zero. Different kind of energy. Different kind of ownership.

**The people.** I connected with the CEO and the team. When the people are right, the work follows. Simple as that.

**The technical challenge.** Building infrastructure from scratch, working with new tools, solving problems that nobody else has solved yet. After years of working within established systems, the idea of starting with a blank canvas was exciting.

So I joined as founding engineer, part-time, alongside my CTO role at Veedoo.

## First Task: Rip Out the SaaS

The first real project at Baseloop was a migration. The product was running on Trigger.dev's SaaS for background jobs and Supabase's SaaS for the database, auth, and storage. Both were hitting limits — rate caps, connection pooling restrictions, pricing tiers that didn't scale with what we needed.

My task: migrate everything to self-hosted infrastructure on Coolify.

I'd done this before at Veedoo, but Baseloop was different. At Veedoo, I migrated gradually over months. At Baseloop, we needed to rip out both services and stand up replacements while keeping the product running. Real users, real data, no downtime allowed.

What I didn't know at the time was that this one migration would end up producing three open-source projects and an npm package.

## The Trigger.dev Nightmare

Let me be honest: self-hosting Trigger.dev was painful.

The documentation for self-hosting was thin. The Docker setup had gaps. And when things broke — and they broke often — there was no "call support" option. This is open source. You're on your own.

Multiple times I found myself deep in Trigger.dev's source code on GitHub, reading through their Go and TypeScript services, trying to understand why a specific worker wasn't connecting or why jobs were silently failing. Tracing through their codebase to find configuration options that weren't documented. Opening issues. Sometimes just reading the code was faster than waiting for a response.

This is founding engineer work. Not the glamorous "we're building the future" stuff. The "it's 11 PM and I'm reading someone else's Docker entrypoint script trying to figure out why Redis connections are dropping" stuff.

Eventually I got it working. Wrote a proper Docker Compose configuration with everything: web app, PostgreSQL, Redis, ElectricSQL, ClickHouse, private Docker registry, MinIO, Supervisor. Created configs for different server tiers. Documented every gotcha I hit along the way.

That became **[coolify-trigger-v4](https://github.com/tao101/coolify-trigger-v4)** — my first open-source contribution from the Baseloop work.

## The Supabase Migration

The Supabase migration was a different kind of scary.

Moving a database is always nerve-wracking. But Supabase isn't just a database — it's PostgreSQL + authentication + storage + real-time subscriptions + auto-generated APIs. You can't just `pg_dump` and call it a day.

The biggest challenge: **preserving user password hashes.** When you migrate auth users between Supabase instances, you need to carry over the bcrypt password hashes. If you don't, every single user has to reset their password on the new instance. For a product with active users, that's not acceptable.

There were real "oh shit" moments. The first test migration, sequences weren't reset after data import — new records were getting primary key conflicts with imported data. Auth users were imported but sessions weren't valid. Storage buckets migrated but file permissions didn't carry over correctly.

Each problem led to a solution. Each solution became a feature in the CLI tool I was building to automate the process. Eventually that tool became **[supabase-sync](https://www.npmjs.com/package/supabase-sync)** — published on npm, handling full Supabase instance migrations: schema, data, auth users (with preserved password hashes), storage files, roles, and sequences.

I also created **[latest-supabase-coolify-template](https://github.com/tao101/latest-supabase-coolify-template)** — a Docker Compose template for deploying the full Supabase stack on Coolify with automatic JWT generation and production-ready PostgreSQL tuning. Because Coolify's built-in Supabase template was outdated and missing critical production configurations.

## I Didn't Plan to Open Source Any of This

Here's the thing — none of the open source work was planned.

I built the Trigger.dev Docker Compose because we needed it for Baseloop. I built supabase-sync because we needed to migrate our data. I built the Supabase Coolify template because we needed a proper deployment setup.

After building each tool, I realized the same thing each time: nobody else had solved this problem either. The Coolify community was asking "how do I self-host Trigger.dev?" The Supabase community was asking "how do I migrate from SaaS to self-hosted?" The answers didn't exist.

So I cleaned up the code, wrote documentation, and published. If it helped me, it would help someone else.

That's the open source mindset I've adopted: build for yourself first, share when you realize you're not the only one with the problem.

## Learning CedarJS

The Baseloop product itself is built with CedarJS — a TypeScript framework I'd never used before. It's batteries-included: built-in ORM with migrations, authentication, job queues, and an auto-generated GraphQL API. The philosophy is similar to Laravel but for the TypeScript ecosystem. Convention over configuration.

Picking it up was fast. After years of MVC patterns across different frameworks (Express, NestJS, Laravel-style PHP), the patterns felt familiar. Models, migrations, seeds, middleware, guards — the names change but the concepts don't.

My honest take on GraphQL after using it in production: it's powerful but verbose. For most use cases, I prefer REST or tRPC. The type safety of GraphQL is nice, but the boilerplate of writing resolvers, managing schemas, and handling N+1 query problems — for a startup moving fast, it feels like overhead. But that's a personal preference, and CedarJS makes it manageable.

## Balancing Two Jobs

People ask me how I manage being CTO at Veedoo full-time AND founding engineer at Baseloop part-time. The honest answer has two parts.

**Part one: time blocks.** Veedoo gets my full-time hours. Baseloop gets dedicated blocks — evenings, weekends, and specific time slots I carve out. I don't mix them. When I'm working on Veedoo, I'm working on Veedoo. When I'm working on Baseloop, I'm working on Baseloop.

**Part two: I'm an indoor cat.** I spend most of my time in my room in front of my laptop. Easily 10-12 hours a day. That's not a complaint — it's what I enjoy. I'm not the person going out every weekend or maintaining a packed social calendar. My idea of a good evening is solving a problem that's been bugging me all day. Some people think that's unhealthy. I think it's just knowing what you want.

Both roles energize me in different ways. Veedoo gives variety — multiple clients, different domains, team management. Baseloop gives ownership — building from zero, making foundational decisions, seeing direct impact of every choice. Together they keep things interesting.

## What Excites Me

I'll keep the product details vague — Baseloop is still building and I don't want to say too much before we're ready.

What excites me most isn't the product itself (though I believe in it). It's the founding experience.

Being there from day one. Making the decisions that become the foundation everything else is built on. Choosing the infrastructure. Setting up the deployment pipeline. Writing the migration tools that don't exist yet. These early decisions compound. The architecture you set up in month one shapes what's possible in year two.

At Veedoo, I inherited systems and evolved them. At Baseloop, I'm laying the foundation. Both are valuable. But there's something about building on an empty canvas that hits different.

---

## What Being a Founding Engineer Taught Me

**Sometimes the tooling doesn't exist and you have to build it.** Before you can build the product, you have to build the tools to build the product. Three open-source projects and an npm package came from just trying to set up infrastructure. That's founding engineer life.

**Read the source code.** When documentation fails — and at the edge of what's been done before, it always does — the source code is the truth. Being comfortable reading through someone else's codebase to solve your own problem is a non-negotiable skill.

**Open source is selfish in the best way.** I didn't open-source these tools out of altruism. I open-sourced them because maintaining them publicly keeps them better documented, better tested, and more likely to get contributions. The fact that they help other people is a bonus, but the primary beneficiary is future me.

**You can have two jobs if you're honest about what it costs.** It works for me because I enjoy spending 10-12 hours a day in front of my laptop. That's my lifestyle, not a sacrifice. But I won't pretend it would work for everyone, or that there aren't tradeoffs.

---

*This is Part 5 of a 5-part series about my career journey. Previously: [From Lead Dev to CTO — How AI and Self-Hosting Changed Everything at Veedoo](#).*

*Check out the tools I built during the Baseloop migration:*
- *[Supabase Sync](https://github.com/tao101/supabase-sync-script) (npm: `supabase-sync`) — Full Supabase instance migration CLI*
- *[Coolify Trigger.dev v4](https://github.com/tao101/coolify-trigger-v4) — Self-host Trigger.dev on Coolify*
- *[Latest Supabase Coolify Template](https://github.com/tao101/latest-supabase-coolify-template) — Production Supabase on Coolify*
- *[Self-Hosted Next.js & Supabase Starter Template](https://github.com/tao101/Self-Hosted-Next.js-Supabase-Fullstack-Starter-Template)*

*Find me on [GitHub](https://github.com/tao101), [LinkedIn](https://www.linkedin.com/in/taoufiqlotfi), or at [taoufiqlotfi.com](https://www.taoufiqlotfi.com). Baseloop is at [baseloop.io](https://baseloop.io).*
