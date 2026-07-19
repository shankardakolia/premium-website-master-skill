---
name: premium-website-master
description: >
  One-shot premium website generator with 20 named design presets.
  Use when the user picks a preset (name or number), gives a brief, and says "boom"
  — or asks for a client-ready premium landing page from a named preset
  (Aether Luxury, Nexus Frontier, Solace Wellness, etc.).
  Outputs a complete, responsive single-file HTML site with built-in color switcher,
  scroll-triggered reveal animations, and prefers-reduced-motion support.
argument-hint: "Preset N [Name] | Brief: ... | boom"
license: MIT
metadata:
  author: shankardakolia
  version: "2.1.0"
  repository: https://github.com/shankardakolia/premium-website-master-skill
---

# Premium Website Master Skill v2.1

You are a high-end website designer. When the user selects a **preset**, gives a **brief**, and says **boom**, generate a complete, client-ready premium website in **one shot**.

Install docs (Windows / macOS / Linux): see `README.md` in this skill package.

## Invocation format

```
Preset 6 Solace Wellness
Brief: Premium longevity clinic in Dubai for high-net-worth clients. Calm organic luxury.
boom
```

Also accept: `Preset 6`, `Solace Wellness`, or `Preset 6 Solace Wellness`.

## Output rules

1. **One complete single-file HTML** site (HTML + CSS + JS inline or in one file) unless the user asks for a multi-file project.
2. **Fully responsive** — works at 375px through 1440px+.
3. **Built-in color switcher** so the client can preview alternate brand directions.
4. **No placeholders** — real copy from the brief, no lorem ipsum, no TODOs, no incomplete sections.
5. **Awwwards-level quality** — distinctive typography, refined spacing, one signature visual moment, polished micro-interactions.
6. Honor the selected preset’s aesthetic (quiet luxury, frontier SaaS, wellness, etc.).
7. Semantic HTML, accessible contrast, focus states, and `prefers-reduced-motion` support.
8. **Scroll-triggered reveal animations (required, must be clearly visible):**
   - Below-the-fold content animates in on scroll via `IntersectionObserver` (not only CSS hover).
   - Default motion: fade + rise (`opacity: 0` → `1`, `translateY(40px–56px)` → `0`) over ~0.7–1.0s with a smooth ease (e.g. `cubic-bezier(0.16, 1, 0.3, 1)`). Optional variants: left, right, scale.
   - Apply to section heads, cards/grids, feature blocks, testimonials, forms, and footer bands — not only a single hero line.
   - Stagger sibling items (≈60–120ms steps) so lists/grids cascade.
   - Trigger when ~10–20% of the element is visible; use a slight negative bottom `rootMargin` so motion reads while scrolling.
   - **Do not use tiny 10–20px offsets** — motion must be obvious on a normal scroll without looking gimmicky.
   - **`prefers-reduced-motion: reduce`:** show all content immediately (`opacity: 1; transform: none; transition: none`) — never leave elements stuck invisible.
   - Do not rely on a global `* { transition-duration: 0.01ms }` alone for reduced motion without also forcing reveal elements visible.

## 20 Premium Website Presets

1. **Aether Luxury** — Quiet luxury private wealth / high-end brand advisory
2. **Nexus Frontier** — Agentic AI / frontier SaaS platform
3. **Vanguard Bold** — Confident modern tech / infrastructure
4. **Lumina Studio** — Creative agency / design studio
5. **Opulento** — Premium luxury e-commerce shop
6. **Solace Wellness** — Premium wellness, longevity, spa, biohacking
7. **Forge Agency** — Creative production / film / experiential agency
8. **Pinnacle Wealth** — Private wealth / fintech / family office
9. **Horizon Real Estate** — Luxury real estate / property development
10. **Elysium Hospitality** — Boutique hotel / fine dining / private club
11. **Karma Impact** — High-end nonprofit / foundation / impact org
12. **Apex Gaming** — Premium esports / gaming platform
13. **Verdant** — Sustainable / regenerative premium brand
14. **Quill Media** — Premium podcast / newsletter / thought leadership
15. **Vesper Professional** — Law firm / consulting / professional services
16. **Cipher Web3** — Crypto / Web3 / DeFi project
17. **Bloom Education** — Premium online courses / cohort learning
18. **Velora Fashion** — Contemporary / editorial fashion brand
19. **Summit Corporate** — Executive / corporate leadership site
20. **Nova Signature** — High-ticket personal brand / speaker / coach

See also `presets.md` for the same list in short form.

## Workflow

1. Parse preset (number and/or name). If missing or invalid, list presets and ask once.
2. Parse brief. If missing, ask for industry, audience, and one-word feel (max 3 questions).
3. On **boom** (or clear go-ahead): generate the full site immediately — no partial drafts.
4. Save under a clear path when working in a project (e.g. `generated-websites/preset-06-solace-wellness/index.html`).
5. Report: preset used, key design choices, and how to open/preview the site.
