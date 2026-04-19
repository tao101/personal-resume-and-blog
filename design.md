# Portfolio Design System — Taoufiq Lotfi

> **READ THIS FIRST (for any AI coding agent / human building this site):**
> Always read `CLAUDE.md` in this repo **before** using this document. `CLAUDE.md` is the source of truth for author context — bio, projects, the resume pipeline, the 7 blog posts, and the writing conventions. `design.md` (this file) is the visual and structural spec for the portfolio website. Content comes from `CLAUDE.md` and the resume/blog files; styling, layout, and interaction rules come from here.

This is a single source of truth for the portfolio site at `taoufiqlotfi.com`. It defines the audience, visual language, components, page structure, motion, accessibility, and performance budget. Every decision below is opinionated on purpose — the goal is a site that converts founders, recruiters, and HR into warm leads, not a showcase of visual tricks.

---

## 1. Target Audience

The portfolio is a **commercial conversion tool**, not a playground. Every design decision is scored against "does it move this reader toward starting a conversation?"

### Primary audiences

**1. Startup founders (Seed – Series A)**
- **Looking for:** a fractional CTO, a founding engineer, or a senior contractor who can own a product end-to-end.
- **Scan time:** 2–5 minutes. Skims stats, reads one case study deeply, clicks the contact CTA.
- **Needs to believe in 2 minutes:** Taoufiq ships products solo, has architectural judgment (HLD/LLD), is cost-aware (self-hosting story), and has shipped things that work at scale.
- **Trigger words:** *ParliamentConnect (98% accuracy), EveryRun (solo-scaled to 17,659 users), self-hosted Coolify migration, 10+ years, CTO, founding engineer.*

**2. Technical recruiters**
- **Looking for:** CTO / Staff / Lead / Founding Engineer placements.
- **Scan time:** 30 seconds. Skims for titles, years, tech stack, location, availability, and a copy-pasteable email.
- **Needs in 30 seconds:** years of experience (10+), current title (CTO at Veedoo), concrete stack (TypeScript, Next.js, Python, Postgres, AI/ML), remote-friendly, contactable.

### Secondary audience

**3. In-house HR at larger companies**
- **Looking for:** a candidate who fits an open req.
- **Scan time:** 20–60 seconds, often feeding into an ATS.
- **Needs:** keyword density (skills strip), clear job titles and dates, contact method that does not require a form.

### Tertiary audience

**4. Engineers evaluating collaboration** (open source contributors, peers, prospective hires)
- **Looking for:** taste, technical depth, writing quality.
- **They read:** the blog and the open-source repos. They do not need the sales pitch.

### Explicitly **not** the audience

- End-consumers, B2C buyers, casual blog-drive-by traffic, hiring managers for junior/entry roles, passive job-board browsers.

### Design consequences of the audience

- **Above-the-fold must satisfy the 30-second recruiter**: name, title, location, stats, contact button.
- **Below the fold must reward the 2-minute founder**: one featured case study with depth, two compact supporting ones.
- **A dense skills section near the bottom** carries the ATS keyword pass.
- **No fluff sections** (quotes, testimonials-from-nobody, illustrations) that cost the recruiter their 30 seconds.

---

## 2. Brand Voice

Same voice as the existing blog posts — confident, specific, and numerate.

- **First person, short paragraphs.** Lead with the story, weave tech in naturally.
- **Proof-driven.** Every claim has a number or a project name next to it. "98% accuracy", "17,659 users", "3 days", "€205/month", "19,000 documents".
- **Zero buzzwords.** No "synergy", "passionate", "rockstar", "ninja", "10x engineer".
- **Vulnerability where it adds weight** — shipping a platform 3 days into the Ukraine invasion, relocating mid-war. Not oversharing, not trauma-cosplay.
- **No emojis.** Anywhere. Icons are SVG from Lucide.
- **Sentence case headings.** No title case shouting, no all-caps except the uppercase micro-labels.

---

## 3. Design Principles (5 pinned)

1. **Conversion over decoration.** Every section earns its place by moving the reader one step closer to a conversation. If it doesn't, cut it.
2. **Mobile is the primary surface.** Design at 375px first. Desktop is progressive enhancement. More than half of recruiter and founder traffic will be mobile.
3. **Speed is a brand attribute.** If the site is fast, the developer looks fast. LCP < 1.5s on Slow 3G is non-negotiable.
4. **Numbers beat adjectives.** "98% accuracy" beats "highly accurate". "17,659 users" beats "many users". Proof, not vibes.
5. **Accessible by default.** WCAG 2.2 AA minimum on every element, in both light and dark modes. Zero color-only meaning. Full keyboard operability.

---

## 4. Color System — Light + Dark Mode

### 4.1 Theme strategy

Two modes: **`light`** and **`dark`**. The site **defaults to the user's OS preference** (`prefers-color-scheme`). A manual toggle lets the user pick `light`, `dark`, or `system`, and the choice persists to `localStorage` under `theme`. The cycle is **system → light → dark → system**, so users always have a one-click path back to OS-driven.

To prevent a flash-of-unstyled-theme, the resolved theme class (`light` or `dark`) is written onto `<html>` by a tiny inline script in `<head>` **before first paint**. No client-side theme computation after hydration.

### 4.2 Light mode — exact values Taoufiq supplied

```css
:root {
  --color-white: #ffffff;
  --color-surface: #fafafa;
  --color-text-primary: #1a1c20;
  --color-text-secondary: #6b7280;
  --color-text-muted: #9ca3af;
  --color-accent: #6366f1;
  --color-accent-hover: #4f46e5;
  --color-accent-light: #eef2ff;
  --color-accent-gradient-end: #8b5cf6;
  --color-border: #e5e7eb;
  --color-border-dashed: #d1d5db;
  --color-dark: #111827;
}
```

**Role + contrast audit (on `#ffffff`):**

| Token | Value | Role | Contrast vs #fff | Verdict |
|---|---|---|---|---|
| `--color-white` | `#ffffff` | Page background (light) | — | — |
| `--color-surface` | `#fafafa` | Card/section background, subtle contrast to page | — | — |
| `--color-text-primary` | `#1a1c20` | Headings, body text on light | 15.8 : 1 | AAA ✓ |
| `--color-text-secondary` | `#6b7280` | Secondary body, captions | 4.59 : 1 | AA body ✓ |
| `--color-text-muted` | `#9ca3af` | Decorative only (timestamps, micro-labels ≥18pt) | 2.84 : 1 | ✗ body — **decorative only** |
| `--color-accent` | `#6366f1` | Accent surfaces, icons, focus ring, ≥18pt text | 3.94 : 1 | ✗ body text — **use for bg, icons, display type only** |
| `--color-accent-hover` | `#4f46e5` | All accent **body text**, link color, chip text | 5.37 : 1 | AA body ✓ |
| `--color-accent-light` | `#eef2ff` | Chip/badge background, soft accent fills | — | — |
| `--color-accent-gradient-end` | `#8b5cf6` | Second stop of the signature gradient | 3.85 : 1 | ✗ body — gradient only |
| `--color-border` | `#e5e7eb` | Default hairline borders, card outlines | — | — |
| `--color-border-dashed` | `#d1d5db` | Dashed separators, placeholder outlines | — | — |
| `--color-dark` | `#111827` | Reserved — footer bg, inverted sections | — | — |

### 4.3 Dark mode — derived companion palette

Dark mode is **derived, not inverted**. Same hue family, rebalanced for dark surfaces. Every pair is verified to meet WCAG AA.

```css
.dark {
  --color-white: #0b0d12;             /* page bg in dark */
  --color-surface: #111827;           /* card / section bg */
  --color-text-primary: #f5f5f7;      /* headings, body */
  --color-text-secondary: #a1a1aa;    /* secondary body */
  --color-text-muted: #71717a;        /* decorative only */
  --color-accent: #818cf8;            /* accent surfaces, icons */
  --color-accent-hover: #a5b4fc;      /* accent body text */
  --color-accent-light: #1e1b4b;      /* chip/badge bg */
  --color-accent-gradient-end: #a78bfa;
  --color-border: #1f2937;
  --color-border-dashed: #374151;
  --color-dark: #0b0d12;
}
```

**Contrast audit (on `--color-white` dark = `#0b0d12`):**

| Token | Value | Contrast | Verdict |
|---|---|---|---|
| `--color-text-primary` (`#f5f5f7`) | primary text | 17.5 : 1 | AAA ✓ |
| `--color-text-secondary` (`#a1a1aa`) | secondary | 7.6 : 1 | AAA ✓ |
| `--color-text-muted` (`#71717a`) | muted | 4.1 : 1 | AA large only — decorative |
| `--color-accent-hover` (`#a5b4fc`) | accent body text | 9.5 : 1 | AAA ✓ |
| `--color-accent` (`#818cf8`) | accent display ≥18pt / icons | 5.6 : 1 | AA body ✓ |

### 4.4 shadcn/ui semantic mapping

Apply these names so shadcn components work out of the box. Same token names in both modes; values differ.

```css
/* shared semantic tokens — values come from the --color-* above */
:root {
  --background: var(--color-white);
  --foreground: var(--color-text-primary);
  --card: var(--color-surface);
  --card-foreground: var(--color-text-primary);
  --popover: var(--color-white);
  --popover-foreground: var(--color-text-primary);
  --primary: var(--color-accent-hover);        /* NOTE: hover value is the safe-contrast variant */
  --primary-foreground: var(--color-white);
  --secondary: var(--color-surface);
  --secondary-foreground: var(--color-text-primary);
  --muted: var(--color-surface);
  --muted-foreground: var(--color-text-secondary);
  --accent: var(--color-accent-light);
  --accent-foreground: var(--color-accent-hover);
  --destructive: #dc2626;
  --destructive-foreground: var(--color-white);
  --border: var(--color-border);
  --input: var(--color-border);
  --ring: var(--color-accent);
  --radius: 0.625rem;
}
```

### 4.5 Explicit usage rules

- **Never** use `--color-accent` (`#6366f1` light / `#818cf8` dark) as body text color. It fails AA on its own background. Use `--color-accent-hover` for all accent-colored body copy and links.
- **Never** invert light colors to build dark mode. Use the spec'd dark values.
- **Never** put the gradient on large fills or on body paragraphs.
- Test every foreground/background pair **independently in dark mode** — do not assume light-mode pairs translate.

---

## 5. Gradient Rules

The signature gradient `#6366f1 → #8b5cf6` (light) / `#818cf8 → #a78bfa` (dark) is reserved for exactly three placements per page:

1. **Hero name** (Taoufiq Lotfi) — `background-clip: text`.
2. **Primary CTA hover state** — subtle glow or fill swap, not the default rest state.
3. **One section-divider accent line** — a 1px or 2px horizontal rule, once per page.

```css
background: linear-gradient(135deg, var(--color-accent) 0%, var(--color-accent-gradient-end) 100%);
```

**Forbidden placements:** full-page bg, large card bg, paragraph body, long-form headings, repeated decorative lines, button rest states, footers.

---

## 6. Typography

### 6.1 Families

- **Inter Variable** — all UI and body copy. Self-hosted (`.woff2`), subset to `latin` + `latin-ext`, preloaded. Weights used: 400, 500, 600, 700. `font-display: swap`.
- **JetBrains Mono** — code blocks and the stat numbers in the hero (for tabular figures). Weights: 400, 500.
- **Fallback stack:** `Inter, -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif`.

Only **one** webfont file is shipped on first paint (Inter variable). JetBrains Mono is loaded on-demand when a page contains code.

### 6.2 Scale (rem, mobile → desktop)

| Name | Size | Use |
|---|---|---|
| `display-xl` | `clamp(2.5rem, 8vw, 4.5rem)` | Hero name |
| `display-lg` | `clamp(2rem, 5vw, 3rem)` | Section heroes |
| `h1` | `2rem` / `2.5rem` | Page titles |
| `h2` | `1.5rem` / `2rem` | Section titles |
| `h3` | `1.25rem` / `1.5rem` | Card/block titles |
| `body-lg` | `1.125rem` | Blog body |
| `body` | `1rem` | Default body |
| `small` | `0.875rem` | Captions, metadata |
| `micro` | `0.75rem` | Uppercase labels (0.05em tracking) |

### 6.3 Rules

- Line-height: 1.7 for blog body, 1.5 for UI body, 1.2 for headings, 1 for display.
- Letter-spacing: `-0.02em` on display, `0` on body, `0.05em` on uppercase micro-labels.
- Always `font-feature-settings: "tnum"` on stats and any numeric column.
- Minimum body size is 16px on mobile (prevents iOS auto-zoom on inputs).
- Line length is 35–60ch on mobile, 65–75ch on desktop. Blog long-form is strictly 65–75ch.
- No all-caps on body, ever. Micro-labels only.

---

## 7. Spacing & Layout

### 7.1 Spacing scale

4px base unit. Allowed values: **4, 8, 12, 16, 24, 32, 48, 64, 96, 128** (Tailwind `1, 2, 3, 4, 6, 8, 12, 16, 24, 32`). No arbitrary values in production code.

### 7.2 Container & rhythm

- Container: `max-w-6xl mx-auto px-4 md:px-8`.
- Blog post container: `max-w-2xl mx-auto px-4 md:px-0` (narrow measure).
- Section vertical rhythm: `py-16 md:py-24`. First section on page uses `pt-24 md:pt-32` to clear the sticky nav.
- Card padding: `p-6 md:p-8`.

### 7.3 Breakpoints (Tailwind defaults — do not redefine)

| Token | Min width | Target device |
|---|---|---|
| `sm` | 640px | Large phone landscape |
| `md` | 768px | Tablet portrait |
| `lg` | 1024px | Tablet landscape / small laptop |
| `xl` | 1280px | Desktop |

### 7.4 Grid

- Mobile: single column.
- `md:`: 2-column for case-study pairs, 2-col for skills.
- `lg:`: 3-column for blog cards and skill clusters. Never more than 3 on any screen.

### 7.5 Z-index scale

`0` base → `10` sticky nav → `20` mobile bottom CTA bar → `40` dropdown → `50` mobile menu sheet → `70` toast → `100` modal → `110` modal scrim. Do not invent new z-indexes outside this scale.

---

## 8. Components

Each component below is a **spec, not code**. Agents implement each one against the spec with shadcn/ui + Tailwind + Framer Motion.

### 8.1 Button

- Variants: `primary` (accent fill), `secondary` (outline), `ghost` (text-only).
- Min height: 44px mobile, 40px desktop. Min tap area always 44×44.
- Primary rest: solid `--color-accent-hover`. Primary hover: 135° gradient fill with subtle 12px outer glow.
- Focus: 2px `--color-accent` outer ring + 2px offset from element, visible on keyboard focus only (`:focus-visible`).
- Tap feedback (Framer Motion): `whileTap={{ scale: 0.97 }}`, `whileHover={{ y: -1 }}` on primary only.
- Disabled: opacity 0.5, cursor `not-allowed`, no hover state.
- Icon-only buttons require `aria-label`.

### 8.2 Stat chip (hero)

- Pill (`rounded-full`), border `1px` `--color-border`, bg transparent.
- Number in JetBrains Mono, `font-feature-settings: "tnum"`, 1.5rem–2rem.
- Label below in `--color-text-secondary`, micro size, uppercase.
- Animate in on viewport enter with `useMotionValue` count-up (see §11).

### 8.3 Case-study card

- Structure: tag chip → title (h3) → 1-sentence problem → 1-line outcome with the **headline metric** in `--color-accent-hover` → tech stack chips → optional "Read the deep dive →" link to `/blog/[slug]`.
- Background: `--color-surface` in both modes.
- Border: `1px` `--color-border` in light, none in dark (use surface contrast instead).
- Hover (desktop only): lift `y: -2`, border color `--color-accent`, shadow `0 4px 16px rgba(99,102,241,0.08)`.

### 8.4 Tech chip

- `rounded-md` (not full), height 24px, `px-2`.
- Bg `--color-accent-light`, text `--color-accent-hover`, micro-label size.
- Uppercase tracking 0.05em.
- Non-interactive by default (no hover). If it becomes a filter, add focus ring.

### 8.5 Nav (top)

- Mobile: logo left, theme toggle + hamburger right. 56px tall. Fixed to top.
- Desktop: logo left, links center (`Work`, `Blog`, `About`), theme toggle + primary CTA right. 64px tall. Sticky.
- Scroll-linked (Framer Motion `useScroll`): at `scrollY > 8`, add `backdrop-blur-md`, lower-opacity bg, and a 1px bottom border. No full opaque fill.

### 8.6 Theme toggle

- Icon-only button, 40×40 (with ≥44 tap target via `hitSlop`/padding).
- Cycles: system → light → dark → system.
- Icons (Lucide): `Monitor` (system), `Sun` (light), `Moon` (dark).
- `aria-label` reflects current state: `"Theme: system. Activate to switch to light."`
- Color crossfade on theme change: CSS `transition: background-color 220ms, color 220ms, border-color 220ms`.

### 8.7 Mobile CTA bar

- Fixed bottom, full-width, safe-area padding (`env(safe-area-inset-bottom)`).
- Two buttons: primary "Email me" (mailto), secondary "Book a call" (Cal.com or similar).
- Visible only on `< md` (768px).
- Hide automatically when the hero primary CTA is in the viewport (use `IntersectionObserver`) to avoid duplicate CTAs.
- Slide-in from bottom on first scroll (not on load), 220ms, `ease-out`.

### 8.8 Blog card

- Title (h3) → 1-line description → metadata row (`{date} · {readTime} · {tag}`).
- Border top `1px` `--color-border` between items on the index page; card-style on the landing "From the blog" section.
- Entire card is clickable (`<article>` wrapped in `<Link>`).

### 8.9 Table of contents (blog post, desktop)

- Sticky on `lg:` and up, right column, `top-24`.
- Max 2 heading levels (h2 + h3).
- Active item highlighted via scrollspy (`IntersectionObserver`), `--color-accent-hover` text.
- Hidden on mobile; mobile gets a collapsible TOC at the top of the article instead.

### 8.10 Footer

- Minimal. Three lines:
  1. Contact row: email, GitHub, LinkedIn, website.
  2. "© {year} Taoufiq Lotfi."
  3. "Built with Next.js · self-hosted on Coolify + Hetzner" — italicized, muted.
- Bg: `--color-dark`; foreground: `--color-text-primary` in dark mode, inverted in light mode.

---

## 9. Page Structure

### 9.1 Landing page (`/`) — fold by fold (mobile)

1. **Fold 1 — Hero.** Name (gradient). One-line pitch: "Full stack developer & CTO. I ship AI-powered products solo." 3 stat chips (e.g., `98% accuracy`, `17,659 users`, `10+ years`). Primary CTA "Hire me" + secondary "See what I've built" anchor.
2. **Fold 2 — What I can build for you.** 3 cards, each a role Taoufiq can play: *Fractional CTO*, *Founding engineer*, *Senior full-stack contractor*. Each card 1 paragraph, no bullets.
3. **Fold 3 — Featured case study.** ParliamentConnect (strongest proof). Problem → approach → 98% accuracy metric → tech stack chips → "Read the deep dive →" link to `/blog/07-parliamentconnect-ml-pipeline-architecture`.
4. **Fold 4 — Two more case studies.** EveryRun (solo-scaled, 17,659 users) and EUvsDisinfo (EU-funded, 13 languages). Compact cards in a 2-col grid on `md:`.
5. **Fold 5 — Skills strip.** Dense, scannable, keyword-rich. Matches the `resume-marketing.md` skills section structure exactly (Languages, Frontend, Backend, Databases, AI/ML, Infrastructure, Payments, CMS, Testing, Tools).
6. **Fold 6 — About.** Single paragraph — same voice as the blog. Optional square photo. Links to the first blog post ("A Moroccan Developer's Journey") for the long story.
7. **Fold 7 — From the blog.** 3 latest/featured blog cards in a row (stacked on mobile).
8. **Fold 8 — Final CTA.** Large, one primary CTA. No form. "The fastest way to work with me is email. I reply within 24 hours." + email button.
9. **Fold 9 — Footer.**

### 9.2 Blog index (`/blog`)

See §17.

### 9.3 Blog post (`/blog/[slug]`)

See §17.

### 9.4 About page (`/about`) — optional v1.5

A longer bio if the landing About section proves too compressed. Deferred unless needed after launch.

---

## 10. Conversion Strategy

- **One primary CTA**: email (`mailto:admin@taoufiqlotfi.tech?subject=Hiring%20Taoufiq`). A "Book a call" secondary CTA links to Cal.com (or similar) once set up.
- **Primary CTA appears in exactly 3 places:** hero, after the last case study, footer final CTA block. Plus the sticky mobile CTA bar (same destination).
- **Secondary CTA** is always a scroll anchor ("See what I've built"), never a competing destination.
- **No contact form, no "get in touch" modal, no newsletter popup.** Forms are friction.
- **No dead-ends.** Every section ends with a link that moves forward (next case study, blog post, or CTA).
- **Track intent events** (mailto click, Cal.com click, blog deep-link click) via PostHog. Lazy-loaded after first interaction.

---

## 11. Motion — Framer Motion

### 11.1 Library & tokens

- Library: **`framer-motion`**. All non-trivial animation runs through it. CSS transitions only for:
  - native `:hover` / `:focus-visible` states on non-animated elements
  - the theme-switch color crossfade (220ms)
- Shared motion tokens (defined once, in `lib/motion.ts`):

```ts
export const duration = { fast: 0.15, base: 0.22, slow: 0.32 };
export const ease = {
  enter: [0.16, 1, 0.3, 1] as const,
  exit: [0.7, 0, 0.84, 0] as const,
};
```

### 11.2 Patterns

- **Section reveal:** `initial={{ opacity: 0, y: 16 }}` → `whileInView={{ opacity: 1, y: 0 }}` with `viewport={{ once: true, margin: "-15%" }}`. Multi-child sections use `staggerChildren: 0.05`.
- **Stat numbers:** count-up via `useMotionValue` + `animate` on viewport enter. Duration `slow` (320ms). Respect reduced motion (render final value statically).
- **Buttons:** primary only — `whileHover={{ y: -1 }}`, `whileTap={{ scale: 0.97 }}`, spring transition.
- **Mobile menu:** `AnimatePresence` slide-in sheet from right. Enter `base`, exit 60–70% of enter.
- **Nav bar:** scroll-linked via `useScroll` → transform opacity and blur on `scrollY` crossing 8px.
- **Blog reading progress:** `useScroll()` → `scaleX` on a 2px top bar, `--color-accent`.
- **Page transitions:** none in v1. Each route is its own document (static). Keep it fast.

### 11.3 Hard rules

- **Reduced motion:** `useReducedMotion()` at the app root. When `true`, return static variants (`initial={false}`), no count-up, no hover lift, no scroll-linked blur.
- **Above-the-fold sections do NOT animate on initial load.** LCP cost is too high. They render final-state immediately.
- Animate only `transform` and `opacity`. Never `width`, `height`, `top`, `left`.
- Exit animations are ~60–70% of enter duration.
- One primary animation per viewport. Do not stack parallax + count-up + card lift + stagger all at once.

---

## 12. Accessibility (non-negotiables)

- Every color pair used is listed in the contrast tables in §4 and verified in both modes.
- All interactive elements are ≥44×44pt with ≥8px spacing.
- Visible `:focus-visible` ring on every interactive element. 2px `--color-accent`, 2px offset. Never remove focus rings.
- Semantic HTML: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`. Headings h1→h6, no skips.
- Every icon-only button has `aria-label`.
- Skip-to-content link as the first focusable element, visible on focus.
- `prefers-color-scheme` is the default theme; manual toggle overrides and persists.
- `prefers-reduced-motion` is honored everywhere (§11.3).
- Zero color-only meaning: tags, statuses, and errors always pair color with an icon or a label.
- No carousels. No autoplay. No captchas unless abuse requires it.
- All images have meaningful `alt`. Decorative images get `alt=""`.

---

## 13. Performance Budget

| Metric | Target | Notes |
|---|---|---|
| LCP | < 1.5s | Slow 3G, Lighthouse mobile |
| CLS | < 0.05 | reserve space for every async element |
| INP | < 200ms | |
| TTI | < 2.5s | |
| Total JS (landing) | < 50KB gzip | Framer Motion is lazy where possible; use `LazyMotion` + `domAnimation` |
| Total CSS (landing) | < 20KB gzip | Tailwind purged |
| Webfonts | 1 file preloaded | Inter Variable, subset latin + latin-ext |

Rules:

- No hero image. The stats are the hero.
- Images: AVIF → WebP fallback → JPEG. Always `width`/`height` or `aspect-ratio`.
- No third-party scripts on the landing page at first paint. PostHog + Sentry are dynamically imported after first user interaction.
- Use `next/image` with `priority` only on one above-the-fold image (if any).
- Framer Motion: import via `LazyMotion` with `domAnimation` feature set to keep the bundle small.

---

## 14. SEO & Meta

- Title: `Taoufiq Lotfi — Full Stack Developer & CTO | AI, Self-Hosting, Shipping Solo`.
- Description (meta): one-sentence pitch + one proof stat (example: "Full stack developer & CTO with 10+ years shipping AI-powered products — including an ML pipeline with 98% accuracy, built solo.").
- Open Graph + Twitter card: pre-rendered 1200×630 summary image per page (landing, about, each blog post). Title + tag overlayed on the accent gradient.
- JSON-LD: `Person` on the landing page, `BlogPosting` on each blog post.
- `sitemap.xml` and `robots.txt` generated at build.
- Canonical URLs on every page.
- Language: `lang="en"` (site is English-only — see §18).

---

## 15. Content Guardrails

- Every claim cites a number, a project name, or a company name.
- One personal photo max, square, soft-focused background. Optional — launch without if not ready.
- No stock photography. No illustrated avatars. No hand-drawn doodles.
- No emojis. SVG icons only (Lucide).
- No "I am passionate about..." / "I love..." sentences.
- No fake testimonial placeholders. If no real testimonials are ready, omit the section.

---

## 16. Build Checklist (ready-to-ship)

### Visual
- [ ] Gradient used in at most 3 placements on any page
- [ ] No hex value hard-coded in a component — all go through semantic tokens
- [ ] Focus ring visible on every interactive element in both modes
- [ ] Theme toggle cycles system → light → dark → system
- [ ] No flash-of-unstyled-theme on page load
- [ ] Dark mode tested independently (not inferred from light)

### Interaction
- [ ] All tap targets ≥44×44 with ≥8px gaps
- [ ] Primary CTA has hover, tap, focus, and disabled states
- [ ] Mobile menu opens, closes via swipe/tap outside/close button
- [ ] Mobile CTA bar hides when hero CTA is in view

### Motion
- [ ] `prefers-reduced-motion: reduce` disables count-up, hover lift, and stagger
- [ ] Above-the-fold content renders at final state (no load animation)
- [ ] No layout shift from any animation

### Performance
- [ ] Lighthouse mobile: LCP < 1.5s, CLS < 0.05, INP < 200ms
- [ ] Total landing JS ≤ 50KB gzip
- [ ] One webfont file preloaded
- [ ] Third-party scripts deferred until interaction

### Accessibility
- [ ] Heading hierarchy valid (no skips)
- [ ] Skip-to-content link present and functional
- [ ] All icon-only buttons have `aria-label`
- [ ] Keyboard tab order matches visual order on every page
- [ ] Color is never the only indicator (status, errors, tags)

### SEO
- [ ] `<title>`, meta description, OG tags, Twitter card on every page
- [ ] `Person` JSON-LD on `/`, `BlogPosting` JSON-LD on each post
- [ ] Sitemap and robots.txt generated
- [ ] Canonical URL on every page

### Content
- [ ] Every claim cites a number or a project name
- [ ] Zero emojis
- [ ] Contact email works (mailto link opens with pre-filled subject)

### Pre-launch
- [ ] Tested on 375px, 768px, 1024px, 1440px
- [ ] Tested with reduced motion enabled
- [ ] Tested in both Chrome and Safari, both modes
- [ ] Tested in Lighthouse + axe + keyboard-only

---

## 17. Blog Section

The blog is a **first-class part of the site**, not a v2. It exists to demonstrate technical writing, build long-tail SEO, and give long-form depth to the landing-page case studies.

### 17.1 `/blog` — index page

- Reverse-chronological list of posts.
- Each item: title (h3), 1-line description, metadata row (`{date} · {readTime} · {tag}`), thin `--color-border` bottom divider.
- Entire item is a link into `/blog/[slug]`.
- Pagination: simple `Previous / Next` at the bottom, 10 posts per page. No infinite scroll.
- Tag filter in a micro-label row at the top (`career`, `tech`, `infra`, `ML`). Clicking narrows the list. A "Clear filter" link appears when active.

### 17.2 Landing page — "From the blog" section

- 3 latest posts (or 3 hand-picked `featured: true` posts) as blog cards in a row.
- Each card: tag chip → title (h3) → 1-line description → `readTime · date`.
- Link at the bottom: "All posts →" → `/blog`.

### 17.3 `/blog/[slug]` — post page

- Reader-optimized layout. 65–75ch measure. 18px body on desktop, 16px on mobile. Line-height 1.7.
- Hero: tag chip → title (display-lg) → metadata row (`{date} · {readTime} · {author}`).
- Body: MDX-rendered. Code blocks use JetBrains Mono, `--color-surface` bg, `--color-border` border. Inline code uses `--color-accent-light` bg with `--color-accent-hover` text.
- Images: rounded-md, 1px `--color-border` outline, full-bleed on mobile (stretch to `100vw` with negative horizontal margin).
- Sticky desktop table of contents on `lg:` and up (§8.9).
- Reading progress bar at top of viewport — 2px, `--color-accent`, Framer Motion `useScroll → scaleX`.
- Author footer: photo (square, 64px) + 1-liner + primary CTA ("Hire me →") + links to GitHub / LinkedIn / Website.
- "Related posts" at the end: up to 3 cards.

### 17.4 Content source

- Posts live as MDX files in `blog-posts/` (already on disk — 7 posts today).
- At build time, compiled with `contentlayer` (preferred) or `next-mdx-remote` fallback.
- Frontmatter contract:

```yaml
---
title: "..."
description: "..."            # one line, ~140 chars max
date: "2026-02-08"            # ISO
tags: ["career", "infra"]     # subset of the tag vocabulary
readTime: 8                   # minutes, integer
featured: false               # surfaces in landing "From the blog"
draft: false                  # excludes from build when true
slug: "moroccan-developer-journey"  # optional override; else derive from filename
---
```

- Filenames already use a numeric prefix (`01-`, `02-`, ...). Strip the prefix for the slug at build time.

### 17.5 Cross-links from landing case studies

- ParliamentConnect card → `/blog/parliamentconnect-ml-pipeline-architecture`
- EveryRun card → `/blog/everyrun-solo-developer`
- EUvsDisinfo / Veedoo cards → `/blog/veedoo-part-1-war-humanitarian-tech` or `/blog/veedoo-part-2-ai-selfhosting-cto`
- Self-hosting stat → `/blog/why-i-self-host-everything`

### 17.6 SEO per post

- Per-post Open Graph image auto-generated from `{title, tag, date}` rendered on the accent gradient.
- JSON-LD `BlogPosting` with `author`, `datePublished`, `headline`, `image`, `mainEntityOfPage`.
- Canonical URL.
- `prev` / `next` links in `<head>` for paginated lists.

### 17.7 What the blog does **not** have in v1

- No comments, no Disqus, no newsletter signup, no like/clap buttons, no reading-time countdown timer, no sidebar ads. Each post ends with the author footer + primary CTA only.
- RSS feed **is** shipped (it's cheap, and serious readers expect it). No UI around it — just `/rss.xml` discoverable via `<link rel="alternate">`.

---

## 18. Out of Scope for v1

Explicitly **not** in the first launch. Agents must not add these unless the scope is reopened.

- **i18n / multi-language.** The site is **English-only**. No language switcher, no locale routing (`/en/`, `/fr/`), no translations, no `next-intl`, no `i18next`. `<html lang="en">` is fixed. Taoufiq's multilingual work (Arabic, French, English — and the 13-language EUvsDisinfo platform) is a *topic the site discusses*, not a UX of the site itself.
- Blog comments, Disqus, or any third-party comment widget.
- Newsletter signup / email capture form.
- 3D / WebGL / Three.js / Spline scenes.
- Video backgrounds, autoplaying video, hero videos.
- Hero illustration or large marketing graphics.
- Carousels, sliders, marquee tickers.
- Analytics dashboards, admin UI, CMS admin panel. MDX files are the CMS.
- Dark-mode-only or light-mode-only stunts (both modes are mandatory, see §4).
- Server-side rendered personalization. The landing and blog are statically generated.
- Full-page loading spinners. Each route renders at final state or with a small skeleton.

---

## Appendix A — Default page layout skeleton (reference)

```tsx
// app/layout.tsx (simplified)
<html lang="en" suppressHydrationWarning>
  <head>
    <ThemeScript />   {/* inline — prevents flash */}
    <link rel="preload" as="font" href="/fonts/inter-var.woff2" type="font/woff2" crossOrigin="" />
  </head>
  <body>
    <SkipLink />
    <Nav />
    <main id="main">{children}</main>
    <Footer />
    <MobileCtaBar />
  </body>
</html>
```

## Appendix B — Theme init script (inline in `<head>`)

```html
<script>
  (function () {
    try {
      var stored = localStorage.getItem('theme');
      var mode = stored || 'system';
      var resolved = mode === 'system'
        ? (matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light')
        : mode;
      document.documentElement.classList.add(resolved);
      document.documentElement.style.colorScheme = resolved;
    } catch (e) {}
  })();
</script>
```

## Appendix C — Tailwind `darkMode: "class"`

Tailwind is configured with `darkMode: "class"` so the `.dark` class on `<html>` (set by the script above) drives all dark variants. Do not use `darkMode: "media"` — we need the manual override.
