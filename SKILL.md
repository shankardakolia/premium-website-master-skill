---
name: premium-website-master
description: >
  One-shot premium website generator (20 presets + live demo catalogue).
  Use for /premium-website-master, /premium-website-master show, or preset + brief + boom.
argument-hint: "show | Preset N [Name] | Brief: ... | boom"
license: MIT
metadata:
  author: shankardakolia
  version: "2.3.2"
  repository: https://github.com/shankardakolia/premium-website-master-skill
  short-description: "20 presets · dual mode ground-up · temp images"
---

# Premium Website Master Skill v2.3.2

You are a high-end website designer. When the user selects a **preset**, gives a **brief**, and says **boom**, generate a complete, client-ready premium website in **one shot**.

Install docs (Windows / macOS / Linux): see `README.md` in this skill package.

## Invocation format

### Show live catalogue (no site generation)

```
/premium-website-master show
```

Also accept: `show`, `catalogue`, `catalog`, `demos`, `list demos`, or `list presets`.

**On show:** Immediately print the full live catalogue from `catalogue.md` (exact preset names + exact demo URLs). Do **not** generate a website. Do **not** ask for a brief.

### Generate a site

```
Preset 6 Solace Wellness
Brief: Premium longevity clinic in Dubai for high-net-worth clients. Calm organic luxury.
boom
```

Also accept: `Preset 6`, `Solace Wellness`, or `Preset 6 Solace Wellness`.

## Command routing (run first)

Parse the invocation argument / first user message:

| Input | Action |
|-------|--------|
| `show`, `catalogue`, `catalog`, `demos`, `list demos`, `list presets` | Print live catalogue only (see below). Stop. |
| Preset number and/or name + brief + boom | Generate full site. |
| Preset only / brief missing | List presets (or show catalogue) and ask once for missing brief. |
| Invalid / empty with no clear intent | Print short help: how to `show`, how to pick a preset, and how to boom. |

## Show command — required output

When the user runs **show** (or aliases above):

1. Load `catalogue.md` from this skill package if available; otherwise use the embedded list below.
2. Print **on screen** every preset with:
   - **Exact preset name** (spelling and capitalization must match)
   - **Live demo URL** (exact path; keep URL encoding)
3. Use this format:

```text
Premium Website Master — Live catalogue
Hub: https://noventra-portfolio.vercel.app

 1. Aether Luxury
    https://noventra-portfolio.vercel.app/Bloom%20Florist/index.html
 2. Nexus Frontier
    https://noventra-portfolio.vercel.app/BrightTech%20Solutions/index.html
 3. Vanguard Bold
    https://noventra-portfolio.vercel.app/AutoPro%20Garage/index.html
 4. Lumina Studio
    https://noventra-portfolio.vercel.app/Pixel%20Studio/index.html
 5. Opulento
    https://noventra-portfolio.vercel.app/HomeStyle%20Interiors/index.html
 6. Solace Wellness
    https://noventra-portfolio.vercel.app/Healthy%20Bites/index.html
 7. Forge Agency
    https://noventra-portfolio.vercel.app/Spark%20Events/index.html
 8. Pinnacle Wealth
    https://noventra-portfolio.vercel.app/Smart%20Finance%20Advisors/index.html
 9. Horizon Real Estate
    https://noventra-portfolio.vercel.app/Dream%20Homes%20Realty/index.html
10. Elysium Hospitality
    https://noventra-portfolio.vercel.app/Ocean%20View%20Hotel/index.html
11. Karma Impact
    https://noventra-portfolio.vercel.app/GreenLeaf%20Caf%C3%A9/index.html
12. Apex Gaming
    https://noventra-portfolio.vercel.app/FitLife%20Gym/index.html
13. Verdant
    https://noventra-portfolio.vercel.app/FreshFarm%20Organics/index.html
14. Quill Media
    https://noventra-portfolio.vercel.app/WanderQuest%20Travel/index.html
15. Vesper Professional
    https://noventra-portfolio.vercel.app/LegalEase%20Associates/index.html
16. Cipher Web3
    https://noventra-portfolio.vercel.app/PetCare%20Clinic/index.html
17. Bloom Education
    https://noventra-portfolio.vercel.app/LearnSmart%20Academy/index.html
18. Velora Fashion
    https://noventra-portfolio.vercel.app/Bella%20Fashion/index.html
19. Summit Corporate
    https://noventra-portfolio.vercel.app/City%20Dental%20Care/index.html
20. Nova Signature
    https://noventra-portfolio.vercel.app/Kids%20World%20Preschool/index.html

Pick a preset (name or number), add a Brief, then say boom.
```

**Hard rules for show:**
- Never invent, shorten, or “clean up” URLs (keep `%20`, `Caf%C3%A9`, etc.).
- Never rename presets.
- Optional: add the demo brand on a middle line (e.g. `Demo: Bloom Florist`) — preset name + URL are mandatory.
- Do not generate HTML for a show-only request.

## Output rules (site generation)

1. **One complete single-file HTML** site (HTML + CSS + JS inline or in one file) unless the user asks for a multi-file project.
2. **Fully responsive** — works at 375px through 1440px+.
3. **Built-in color switcher** so the client can preview alternate brand directions (palette variants).
4. **Dark / light mode — built from the ground up (required, same priority as responsiveness):**
   - **Never bolt on mode after the fact.** Design the token system dual-mode first, then build components against tokens only.
   - **Architecture (mandatory):**
     - `data-mode="light" | "dark"` on `<html>` owns **structure**: `--bg`, `--bg-elevated`, `--bg-soft`, `--bg-card`, `--text`, `--text-muted`, `--border`, `--header-bg`, form/surface colors.
     - Optional `data-theme` / palette switchers may **only** change **accents** (`--accent`, `--accent-2`, softs). They must **not** redefine backgrounds/text (that breaks mode).
     - Use `html[data-mode="light"] { ... }` and `html[data-mode="dark"] { ... }` with enough specificity that palette rules never win over mode for structural tokens.
   - **Navbar control:** sun/moon (or clear label) in header actions, both mobile and desktop; persist in `localStorage` (e.g. `pwm-color-mode`).
   - **Brand-dark presets** (gaming, cinematic, dark SaaS, etc.): default `data-mode="dark"` and still ship a real light companion palette (not “dark-on-dark”).
   - **Brand-light presets:** default `data-mode="light"` with a real dark companion.
   - Restyle surfaces, text, borders, cards, forms, header, filters, tags — **never** `filter: invert()` on the page.
   - No hardcoded `#fff` / `#000` on major surfaces; use CSS variables so mode works everywhere.
   - CTA contrast in both modes (e.g. white label on accent fills).
   - **Default mode is light** unless the user explicitly prefers dark (or a saved preference exists).
   - Toggle must visibly change the page (if light and dark look the same, the implementation failed).
5. **Images strategy (first generation):**
   - **On first boom / first generation:** use **temporary stock images** (e.g. Unsplash or similar HTTPS URLs) that match the industry/mood — hero, cards, gallery, team, product tiles. Prefer real photo URLs over pure CSS gradients for media areas.
   - Do **not** ship empty gray boxes or gradient-only product/course/gallery tiles when the section is meant to show photography.
   - Later, when the user provides brand assets, swap temporary URLs for final images without redesigning layout.
   - Always set meaningful `alt` text; use `loading="lazy"` below the fold.
6. **No content placeholders** — real copy from the brief, no lorem ipsum, no TODOs, no incomplete sections (copy is final-quality; images may be temporary stock).
7. **Awwwards-level quality** — distinctive typography, refined spacing, one signature visual moment, polished micro-interactions.
8. Honor the selected preset’s aesthetic (quiet luxury, frontier SaaS, wellness, etc.).
9. Semantic HTML, accessible contrast, focus states, and `prefers-reduced-motion` support.
10. **Scroll-triggered reveal animations (required, must be clearly visible):**
   - Below-the-fold content animates in on scroll via `IntersectionObserver` **plus** a `requestAnimationFrame` scroll fallback (IO alone often fails after first paint on mobile/continuous scroll).
   - Default motion: fade + rise (`opacity: 0` → `1`, `translateY(40px–56px)` → `0`) over ~0.7–1.0s with a smooth ease (e.g. `cubic-bezier(0.16, 1, 0.3, 1)`). Optional variants: left, right, scale.
   - Animate **discrete content units only** (cards, articles, section heads, stats, steps, forms) — **never** put `opacity: 0` / reveal classes on tall shells (`.container`, full `section`, whole grids). Tall shells stick invisible because IO thresholds never fire.
   - Stagger sibling items (≈60–120ms steps) so lists/grids cascade.
   - Trigger when ~10–20% of the element is visible; `rootMargin` bottom about `-8%` to `-10%`.
   - Re-check visibility on scroll, resize, hash links, and after filter/search UI that shows/hides cards.
   - **Do not use tiny 10–20px offsets** — motion must be obvious on a normal scroll without looking gimmicky.
   - **`prefers-reduced-motion: reduce`:** show all content immediately (`opacity: 1; transform: none; transition: none`) — never leave elements stuck invisible.
   - Do not rely on a global `* { transition-duration: 0.01ms }` alone for reduced motion without also forcing reveal elements visible.

## 20 Premium Website Presets

1. **Aether Luxury** — Quiet luxury private wealth / high-end brand advisory  
   Live: https://noventra-portfolio.vercel.app/Bloom%20Florist/index.html
2. **Nexus Frontier** — Agentic AI / frontier SaaS platform  
   Live: https://noventra-portfolio.vercel.app/BrightTech%20Solutions/index.html
3. **Vanguard Bold** — Confident modern tech / infrastructure  
   Live: https://noventra-portfolio.vercel.app/AutoPro%20Garage/index.html
4. **Lumina Studio** — Creative agency / design studio  
   Live: https://noventra-portfolio.vercel.app/Pixel%20Studio/index.html
5. **Opulento** — Premium luxury e-commerce shop  
   Live: https://noventra-portfolio.vercel.app/HomeStyle%20Interiors/index.html
6. **Solace Wellness** — Premium wellness, longevity, spa, biohacking  
   Live: https://noventra-portfolio.vercel.app/Healthy%20Bites/index.html
7. **Forge Agency** — Creative production / film / experiential agency  
   Live: https://noventra-portfolio.vercel.app/Spark%20Events/index.html
8. **Pinnacle Wealth** — Private wealth / fintech / family office  
   Live: https://noventra-portfolio.vercel.app/Smart%20Finance%20Advisors/index.html
9. **Horizon Real Estate** — Luxury real estate / property development  
   Live: https://noventra-portfolio.vercel.app/Dream%20Homes%20Realty/index.html
10. **Elysium Hospitality** — Boutique hotel / fine dining / private club  
    Live: https://noventra-portfolio.vercel.app/Ocean%20View%20Hotel/index.html
11. **Karma Impact** — High-end nonprofit / foundation / impact org  
    Live: https://noventra-portfolio.vercel.app/GreenLeaf%20Caf%C3%A9/index.html
12. **Apex Gaming** — Premium esports / gaming platform  
    Live: https://noventra-portfolio.vercel.app/FitLife%20Gym/index.html
13. **Verdant** — Sustainable / regenerative premium brand  
    Live: https://noventra-portfolio.vercel.app/FreshFarm%20Organics/index.html
14. **Quill Media** — Premium podcast / newsletter / thought leadership  
    Live: https://noventra-portfolio.vercel.app/WanderQuest%20Travel/index.html
15. **Vesper Professional** — Law firm / consulting / professional services  
    Live: https://noventra-portfolio.vercel.app/LegalEase%20Associates/index.html
16. **Cipher Web3** — Crypto / Web3 / DeFi project  
    Live: https://noventra-portfolio.vercel.app/PetCare%20Clinic/index.html
17. **Bloom Education** — Premium online courses / cohort learning  
    Live: https://noventra-portfolio.vercel.app/LearnSmart%20Academy/index.html
18. **Velora Fashion** — Contemporary / editorial fashion brand  
    Live: https://noventra-portfolio.vercel.app/Bella%20Fashion/index.html
19. **Summit Corporate** — Executive / corporate leadership site  
    Live: https://noventra-portfolio.vercel.app/City%20Dental%20Care/index.html
20. **Nova Signature** — High-ticket personal brand / speaker / coach  
    Live: https://noventra-portfolio.vercel.app/Kids%20World%20Preschool/index.html

See also `presets.md` and `catalogue.md`.

## Workflow

1. **Route first:** if the message is `show` / catalogue / demos → print the live catalogue and stop.
2. Parse preset (number and/or name). If missing or invalid, list presets (or run show) and ask once.
3. Parse brief. If missing, ask for industry, audience, and one-word feel (max 3 questions).
4. On **boom** (or clear go-ahead): generate the full site immediately — no partial drafts.
5. Save under a clear path when working in a project (e.g. `generated-websites/preset-06-solace-wellness/index.html`).
6. Report: preset used, key design choices, live demo link for that preset (from the catalogue), and how to open/preview the site.
