# From Morocco to Ukraine to CTO — My First 4 Years at Veedoo (2019-2022)

In 2019, a European digital consultancy found me through my freelance work and offered me a job. By the end of 2022, I'd built platforms that helped refugees find shelter, kept a suicide prevention hotline running during a war, and architected a blockchain-powered evidence system for fighting Russian disinformation.

I also watched the country I'd called home for 5 years go to war — from a hotel room in Turkey.

This is the story of my first four years at Veedoo.

---

## They Found Me

After 5 years of freelancing — first Android apps in Morocco, then React Native in Ukraine — I had built enough of a reputation that opportunities started coming to me instead of the other way around. Veedoo, a digital consultancy based in Europe serving EU institutions, nonprofits, and startups, reached out based on my portfolio.

I joined as a mid-level full stack developer in 2019. The transition from freelance to company life, from mobile-only to full stack web — it was somewhere in between comfortable and terrifying. React Native to React? Natural. Same language, similar patterns. But backend development? Databases? Server architecture? That was new territory.

The tech stack was React, Node.js, Express, and MongoDB. I was building SPAs and mobile apps for Veedoo's clients. Nothing revolutionary, but every project was teaching me something I didn't know before. And unlike freelancing, I had a team around me. People to learn from. Code reviews that actually caught my mistakes.

## The Next.js Moment (2020-2021)

The real shift came when I discovered Next.js. Veedoo's clients had content-heavy websites — blogs, news platforms, multilingual portals — and client-side React SPAs weren't cutting it for SEO. That's when I dove into server-side rendering.

My first big Next.js project was migrating a client's website with 500+ blog posts from a React SPA to Next.js with Static Site Generation. The before and after was dramatic — Time to First Byte went from roughly 2-3 seconds to under 100 milliseconds. Not a typo. We went from dynamically rendering every page on every request to serving pre-built static HTML from a CDN. The client's Google rankings improved almost overnight.

That migration taught me more about web performance than any course ever could. SSR versus SSG versus CSR — understanding when to use which, and why, became second nature. I added ISR (Incremental Static Regeneration) so content updates would propagate without full rebuilds. Discovered Vercel's serverless architecture. Started using Jamstack patterns with Sanity CMS as a headless backend.

Around this time I also started working on **Lifeline Ukraine** — Ukraine's national suicide prevention hotline platform. Building a platform for people in crisis requires a different mindset. Every design decision was guided by trauma-informed UX principles. Calming visuals. Intuitive navigation. A quick-exit button that instantly navigates to Google — because some users accessing a mental health resource might be in unsafe domestic situations and need to hide what they're looking at immediately.

No personally identifiable information stored. GDPR-compliant anonymous chat. HTTPS everywhere with strict security headers. You approach code differently when the people using it are at their most vulnerable.

There was also a PHP project — Icons of Ukraine — that humbled me a bit. Laravel-style MVC with MySQL, React for the frontend. It reminded me that every language and framework has its own philosophy, and being good at JavaScript doesn't automatically make you good at PHP. But it expanded my backend versatility, and the Docker and Linux server administration skills I picked up would become essential later.

## February 24, 2022

I was on vacation in Turkey when the war started.

I'd left Kharkiv — the city I'd lived in for 5 years, where I'd studied, freelanced, built a life — expecting to come back in two weeks. I left everything there. My apartment, my stuff, my routines. Two weeks, I thought.

Then the invasion happened. And I wasn't going back.

I was lucky. I wasn't in Kharkiv when the bombs started falling. But watching the city you know — the streets you walked, the cafes you sat in, the university you graduated from — getting shelled on a TV screen in a Turkish hotel room? That's a different kind of shock.

The decision was quick. Not the EU, not staying in Turkey. Morocco. Home. I wanted to be close to family. I'd end up staying in Morocco for about three years, working remotely for Veedoo the entire time.

But before any of that, there was work to do.

## Ukraine Shelter — 3 Days to Launch

Nobody remembers exactly who had the idea. It was a Veedoo initiative — the team saw the crisis unfolding and mobilized. The domain name was registered on February 25th, one day after the invasion. The first version of the site launched on February 27th.

Three days.

Ukraine Shelter was a platform to match refugees with shelter offers. People fleeing Kharkiv, Kyiv, Mariupol — they needed somewhere to go. And people across Ukraine and the EU were offering their homes. The platform connected them.

The architecture was pragmatic. Speed over perfection. We didn't sit around debating the optimal database schema or arguing about code style. People needed help NOW. Form submissions for shelter offers, a matching algorithm, a map-based interface for geographic searching. Infrastructure designed for high availability because downtime on this platform didn't mean lost revenue — it meant someone didn't find shelter.

"Just ship it" — the lesson from my freelancing years — had never felt more real. Or more important.

The platform grew significantly after launch. A team of volunteers rallied around it. But that first version, built in three chaotic days while the world was watching a country I loved get invaded — that's something I'll never forget.

## Lifeline Under Wartime Pressure

The suicide prevention platform I'd been working on since 2021 suddenly became one of the most critical services in Ukraine. When a country goes to war, mental health doesn't just suffer — it collapses. The demand for Lifeline's services increased by orders of magnitude.

My job was to make sure the platform could handle it. Scaling infrastructure, optimizing database queries, implementing caching layers, adding monitoring and alerting for zero downtime. This was a life-critical service — if the chat system went down, people in crisis had nowhere to turn.

The weight of it was real. Both heavy and motivating at the same time. For both Ukraine Shelter and Lifeline Ukraine, I learned what it feels like when downtime doesn't mean losing money. It means lives affected. You approach every deployment, every migration, every infrastructure decision differently when that's the stakes. More carefully. More seriously. But also with more purpose than any other project I've ever worked on.

Over 1,500 people used Lifeline's chat feature every month — including Ukrainian refugees abroad who couldn't call the national hotline number from other countries. The platform gave them a way to get help anyway.

## EUvsDisinfo — Fighting Disinformation at EU Scale

While handling wartime platform scaling, I was also taking ownership of Veedoo's biggest client: EUvsDisinfo. This was (and still is) a platform for the European External Action Service — the EU's diplomatic service — dedicated to tracking and exposing Russian disinformation across Europe.

The numbers tell the story: 19,000+ documented disinformation cases, millions of annual users, content in 13 languages, a distributed international team of analysts and editors.

My corner of it was the backend and CMS architecture. EUvsDisinfo runs on Sanity CMS with a custom "Disinformation Management System" built on top of it. Real-time collaborative editing (like Google Docs), custom editorial workflows, and GROQ queries powering the public-facing multilingual website.

The most interesting technical work was the **evidence preservation pipeline**. Disinformation sources frequently edit or delete their content after being exposed. So we needed a way to capture and preserve evidence the moment it was flagged. I built an automation system that:

1. **Scraped the flagged URL** using Puppeteer — full-page screenshots at multiple viewport sizes
2. **Archived the complete HTML** including all inline assets, creating a self-contained snapshot of the page as it existed at that moment
3. **Timestamped the archive on the blockchain** using OpenTimestamps — an open protocol that leverages the Bitcoin blockchain to create cryptographic proof that the content existed at a specific point in time. This produces legally defensible, immutable evidence that cannot be backdated or tampered with.

The whole pipeline was triggered by Sanity webhooks. An analyst flags an article, and the system handles everything else automatically. No manual intervention beyond the initial flag.

All infrastructure had to be self-hosted on EU-based servers — EU-funded project, EU data residency requirements. No exceptions. This compliance requirement would later become the seed that grew into my entire self-hosting philosophy, but that's a story for the next post.

## The Promotion I Didn't Expect

At the end of 2022, Veedoo promoted me to Lead Full Stack Developer.

It was a pleasant surprise. I wasn't pushing for it. I was just doing my work — showing up, building good things, making clients happy. The EUvsDisinfo team specifically appreciated the automation work. The evidence pipeline saved them hours of manual labor. The custom editorial tools made their 13-language content operations smoother.

Sometimes the best career strategy is not having a career strategy. Just do excellent work consistently, and the recognition follows.

## Going Home

After the war started, I went from Turkey back to Morocco. Close to family. That's what I needed.

I'd end up staying in Morocco for about three years, working remotely for Veedoo the entire time. The work didn't change — the same projects, the same clients, the same late-night deployments. But the context was different. I was building things from my room in Morocco that were helping people in Ukraine. Code as a bridge between continents.

In Q4 2024, I'd move to Moldova. But during those three years in Morocco, I kept building. And the next chapter — AI, self-hosting, building ML pipelines, becoming CTO — was already starting to take shape.

---

## What Those 4 Years Taught Me

**Tech can save lives.** When you're building shelter matching for refugees or a suicide prevention platform during a war, code stops being abstract. It's not about clean architecture or clever algorithms. It's about whether someone finds a safe place to sleep tonight. Whether someone in crisis can reach a counselor. That changes how you think about everything you build, even the projects that aren't life-or-death.

**Adversity builds you.** I wouldn't wish a war on anyone. But the projects I'm most proud of — Ukraine Shelter, Lifeline under wartime pressure, the evidence pipeline — all came from the hardest moments. Comfort doesn't push you to ship a platform in three days.

**Stay adaptable.** Morocco to Ukraine to Turkey to Morocco. Mobile to web. Normal times to wartime. The ability to adapt — to a new country, a new tech stack, a new reality — is the most transferable skill I have.

**Show up and deliver.** The promotion to Lead wasn't planned. It came from consistently doing good work on the things that mattered most. Not from politics, not from self-promotion, not from asking for it. Just from showing up and delivering.

---

*This is Part 2 of a 5-part series about my career journey. Previously: [A Moroccan Developer's Journey — From Android Apps to React Native in Ukraine](#). Next up: [How I Scaled a Running Platform from 80 to 17,659 Users as the Only Developer](#).*

*Find me on [GitHub](https://github.com/tao101), [LinkedIn](https://www.linkedin.com/in/taoufiqlotfi), or at [taoufiqlotfi.com](https://www.taoufiqlotfi.com).*
