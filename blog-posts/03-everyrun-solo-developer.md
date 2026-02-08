# How I Scaled a Running Platform from 80 to 17,659 Users as the Only Developer

When I joined EveryRun, 80 people were using the platform. When I left 14 months later, that number was 17,659. I was the only developer the entire time.

This is what it's like to own a product end-to-end — the good, the bad, and the "it's 2 AM and only I can fix this."

---

## How I Got the Gig

In mid-2023, I was working as Lead Full Stack Developer at Veedoo when the EveryRun opportunity came along. It was a part-time role — product engineer for a virtual running events platform. The appeal was simple: total ownership.

At Veedoo, I was part of a team working on multiple client projects. At EveryRun, I would BE the team. One developer, one product, complete control over every technical decision. For someone who'd been freelancing since 18, the idea of owning a product again — but this time with a real business behind it and users to serve — was hard to resist.

I said yes.

## Choosing the Stack

When you're the only developer, every tech choice matters more. There's nobody to pick up the slack if you choose a tool that's painful to work with. And there's nobody to blame but yourself.

Here's what I went with and why:

**Next.js 14 (App Router)** — React Server Components and Server Actions were new at the time. I bet on them early and it paid off. Server Actions meant I could handle mutations without building a separate API layer. Less code, less surface area, faster iteration.

**PostgreSQL on Neon** — This was the decision that changed everything, but I'll get to that in a minute.

**Drizzle ORM** over Prisma — controversial take, but Drizzle won me over. It's SQL-first, the TypeScript type inference is automatic from your schema, and the runtime is much lighter. For a serverless environment (Vercel), cold-start performance matters. Prisma's binary engine adds noticeable latency on cold starts. Drizzle doesn't have that problem.

**React Native Expo** for the mobile app — shared TypeScript types between web and mobile. Write the type once, use it everywhere.

**Stripe** for payments and **Stripe Connect** for paying Organizers.

**PostHog** for analytics — feature flags, A/B testing, session replays, funnels. This became my co-pilot for every product decision.

**Vercel** for hosting with preview deployments per PR.

Was everything perfect? No. Some choices were annoying in practice. But the overall stack let me move fast, which is what matters when you're alone.

## The Neon DB Branching Workflow

This was the game-changer. If you take one thing from this post, let it be this.

Neon is serverless PostgreSQL with a killer feature: database branching. Think Git branches, but for your database. You can fork your entire production database — schema, data, everything — into an isolated branch in seconds.

I connected this to Vercel's preview deployments. The result: **every pull request got its own preview deployment AND its own isolated database branch with real production data.**

Think about what that means. The CEO could click a preview link on any PR and test the feature with real data in a completely isolated environment. Schema migrations could be tested against production-like data before merging. I could experiment freely without any risk of touching production.

For a solo developer, this was massive. It eliminated an entire category of risk. I could iterate faster because I wasn't afraid of breaking things. Features went from idea to production in days instead of weeks.

If you're building anything on Vercel with PostgreSQL, look into Neon DB branching. Seriously.

## The Growth Story

Let's be honest about the numbers. Going from 80 to 17,659 users wasn't because I wrote brilliant code. The growth was marketing-driven. The CEO and the business side drove user acquisition — campaigns, partnerships, community building. My job was to make sure the product could handle it and the features were there to retain users.

But that's an important lesson in itself. As a developer, it's easy to think the product IS the code. It's not. The product is the experience, and the code is just the tool that delivers it. The best architecture in the world doesn't matter if nobody knows the product exists.

PostHog was my eyes and ears. Feature flags let me roll out changes gradually. A/B testing showed me what actually worked versus what I assumed would work (not always the same thing). Session replays helped me understand how real people used the app — which was often different from how I designed it to be used.

One feature I'm particularly proud of: charitable donation integration through Stripe Connect. Runners could raise money for causes tied to their virtual events, with automatic fund distribution to registered charities. Building something where users aren't just exercising but also raising money for good causes — that felt right.

## The Reality of Being Solo

Here's what nobody tells you about being a solo developer on a growing product.

**No code review.** Every architecture decision was mine alone. Sounds great until you're at a crossroads and genuinely don't know which path is better. There's no senior dev to rubber duck with. No PR reviewer to catch the thing you missed. You just decide, commit, and live with the consequences.

**Always on-call.** If something broke at 2 AM on a Saturday, guess who was fixing it? There's no on-call rotation when the rotation is just you. Every notification from the monitoring system hits different when you know nobody else is going to see it.

**Context switching.** I was doing this part-time alongside my Lead role at Veedoo. That meant constantly switching between two completely different codebases, two different sets of problems, two different stakeholders. Monday morning I'm working on a 13-language CMS for EU disinformation tracking. Monday afternoon I'm debugging a GPS distance calculation for a virtual running event. Your brain does not enjoy this.

All three were real challenges. I'm not going to pretend it was easy. But there's something that comes from making every decision yourself — a depth of ownership and understanding of a system that you don't get any other way.

## The Handover

After about 14 months, the engagement came to a natural end. The product was stable. The team wanted to shift their budget toward marketing to drive further growth. The system I'd built was running smoothly and didn't need a full-time developer to maintain it.

Clean exit.

But before I left, I wrote 30 pages of documentation.

Architecture decisions documented in ADR format — what we chose, why, what alternatives were considered. Database schema documentation with entity-relationship diagrams. API reference for every endpoint. Deployment procedures step by step. An onboarding guide for whoever would pick up the codebase next.

Why? Two reasons.

First, professional pride. When you build something from scratch and hand it to someone else, that documentation is how you ensure your work outlives your involvement. The code tells you what it does. The documentation tells you why.

Second, I've been on the receiving end of bad handovers. Inheriting a codebase with no documentation, no context, no explanation of why anything is the way it is. I know how frustrating that is, and I wasn't going to do it to someone else.

Handing off something you built from scratch is bittersweet. You know every line. You remember why that weird edge case handler exists. You remember the 2 AM debugging session that led to that particular database index. And then you walk away and someone else takes the wheel.

But that's the gig. Build it well. Document it thoroughly. Move on.

---

## What Being a Solo Dev Taught Me

**Ownership is a double-edged sword.** Total control means total responsibility. Every bug is yours. Every architectural mistake is yours. But so is every win. There's no hiding in a team when you ARE the team.

**Document like someone's going to inherit your code tomorrow** — because eventually they will. And the quality of that documentation is the last impression you leave on a project.

**The product isn't the code.** EveryRun grew because of marketing, community, and a clear value proposition. My job was to build the best possible tool for delivering that value. But the code alone didn't create the growth. Never confuse the tool with the thing it builds.

---

_This is Part 3 of a 5-part series about my career journey. Previously: [My First 4 Years at Veedoo — War, Humanitarian Tech, and the Road to Lead](#). Next up: [From Lead Dev to CTO — How AI and Self-Hosting Changed Everything](#)._

_Find me on [GitHub](https://github.com/tao101), [LinkedIn](https://www.linkedin.com/in/taoufiqlotfi), or at [taoufiqlotfi.com](https://www.taoufiqlotfi.com)._
