# Live demo catalogue

**Hub:** https://noventra-portfolio.vercel.app

When the user runs `/premium-website-master show` (or `show`, `catalogue`, `demos`, `list demos`), print this table **exactly** — every preset name and its live demo URL. Do not invent alternate URLs.

| # | Preset name | Demo site | Live demo URL |
|---|-------------|-----------|---------------|
| 1 | Aether Luxury | Bloom Florist | https://noventra-portfolio.vercel.app/Bloom%20Florist/index.html |
| 2 | Nexus Frontier | BrightTech Solutions | https://noventra-portfolio.vercel.app/BrightTech%20Solutions/index.html |
| 3 | Vanguard Bold | AutoPro Garage | https://noventra-portfolio.vercel.app/AutoPro%20Garage/index.html |
| 4 | Lumina Studio | Pixel Studio | https://noventra-portfolio.vercel.app/Pixel%20Studio/index.html |
| 5 | Opulento | HomeStyle Interiors | https://noventra-portfolio.vercel.app/HomeStyle%20Interiors/index.html |
| 6 | Solace Wellness | Healthy Bites | https://noventra-portfolio.vercel.app/Healthy%20Bites/index.html |
| 7 | Forge Agency | Spark Events | https://noventra-portfolio.vercel.app/Spark%20Events/index.html |
| 8 | Pinnacle Wealth | Smart Finance Advisors | https://noventra-portfolio.vercel.app/Smart%20Finance%20Advisors/index.html |
| 9 | Horizon Real Estate | Dream Homes Realty | https://noventra-portfolio.vercel.app/Dream%20Homes%20Realty/index.html |
| 10 | Elysium Hospitality | Ocean View Hotel | https://noventra-portfolio.vercel.app/Ocean%20View%20Hotel/index.html |
| 11 | Karma Impact | GreenLeaf Café | https://noventra-portfolio.vercel.app/GreenLeaf%20Caf%C3%A9/index.html |
| 12 | Apex Gaming | FitLife Gym | https://noventra-portfolio.vercel.app/FitLife%20Gym/index.html |
| 13 | Verdant | FreshFarm Organics | https://noventra-portfolio.vercel.app/FreshFarm%20Organics/index.html |
| 14 | Quill Media | WanderQuest Travel | https://noventra-portfolio.vercel.app/WanderQuest%20Travel/index.html |
| 15 | Vesper Professional | LegalEase Associates | https://noventra-portfolio.vercel.app/LegalEase%20Associates/index.html |
| 16 | Cipher Web3 | PetCare Clinic | https://noventra-portfolio.vercel.app/PetCare%20Clinic/index.html |
| 17 | Bloom Education | LearnSmart Academy | https://noventra-portfolio.vercel.app/LearnSmart%20Academy/index.html |
| 18 | Velora Fashion | Bella Fashion | https://noventra-portfolio.vercel.app/Bella%20Fashion/index.html |
| 19 | Summit Corporate | City Dental Care | https://noventra-portfolio.vercel.app/City%20Dental%20Care/index.html |
| 20 | Nova Signature | Kids World Preschool | https://noventra-portfolio.vercel.app/Kids%20World%20Preschool/index.html |

## Screen output format (required for `show`)

Print a clean, scannable list. Prefer this shape:

```text
Premium Website Master — Live catalogue
Hub: https://noventra-portfolio.vercel.app

 1. Aether Luxury
    https://noventra-portfolio.vercel.app/Bloom%20Florist/index.html
 2. Nexus Frontier
    https://noventra-portfolio.vercel.app/BrightTech%20Solutions/index.html
 ...
20. Nova Signature
    https://noventra-portfolio.vercel.app/Kids%20World%20Preschool/index.html

Pick a preset (name or number), add a Brief, then say boom.
```

Rules:
- Use the **exact** preset names above (spelling and capitalization).
- Use the **exact** URLs above (including `%20` and `Caf%C3%A9` encoding).
- Optionally show the demo site name on a middle line; never omit the preset name or URL.
- Do not generate a website when the only argument is `show` / `catalogue` / `demos`.
