# Premium Website Master Skill v2.1

**One-shot premium website generator** with **20 named design presets**.

Turn any coding agent into a high-end website designer: pick a preset → give a brief → say **boom** → get a complete, client-ready single-file HTML site.

| Feature | Included |
|--------|----------|
| 20 unique design presets | Yes |
| Single-file HTML (CSS + JS inline) | Yes |
| Fully responsive (375px–1440px+) | Yes |
| Built-in color switcher | Yes |
| Scroll-triggered reveal animations | Yes (required) |
| Real copy from your brief | Yes |
| Cross-platform install (Windows / macOS / Linux) | Yes |

**Repository:** [github.com/shankardakolia/premium-website-master-skill](https://github.com/shankardakolia/premium-website-master-skill)

---

## Quick start

1. Install this skill (see [Installation](#installation) below).
2. In your agent chat:

```text
Preset 6 Solace Wellness
Brief: Premium longevity clinic in Dubai for high-net-worth clients. Calm organic luxury.
boom
```

3. The agent generates one complete `index.html` (or a path you specify).

Also accepted:

- `Preset 6`
- `Solace Wellness`
- `Preset 6 Solace Wellness`

---

## Installation

Works on **Windows**, **macOS**, and **Linux**. Choose the method that matches your agent.

### Option A — Clone with Git (recommended)

**macOS / Linux (Terminal):**

```bash
# User-level skills folder (Claude Code / many agents)
mkdir -p ~/.claude/skills
git clone https://github.com/shankardakolia/premium-website-master-skill.git \
  ~/.claude/skills/premium-website-master

# Or Agents / Cursor-style location
mkdir -p ~/.agents/skills
git clone https://github.com/shankardakolia/premium-website-master-skill.git \
  ~/.agents/skills/premium-website-master
```

**Windows (PowerShell):**

```powershell
# Claude Code skills
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills" | Out-Null
git clone https://github.com/shankardakolia/premium-website-master-skill.git `
  "$env:USERPROFILE\.claude\skills\premium-website-master"

# Or agents skills folder
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills" | Out-Null
git clone https://github.com/shankardakolia/premium-website-master-skill.git `
  "$env:USERPROFILE\.agents\skills\premium-website-master"
```

**Windows (Git Bash / WSL):** same commands as macOS/Linux.

### Option B — Download ZIP (no Git)

1. Open: [https://github.com/shankardakolia/premium-website-master-skill](https://github.com/shankardakolia/premium-website-master-skill)
2. Click **Code → Download ZIP**
3. Unzip the folder
4. Rename the folder to `premium-website-master` (optional but tidy)
5. Move it into one of:
   - **Claude Code:** `~/.claude/skills/` (Windows: `%USERPROFILE%\.claude\skills\`)
   - **Grok / Agents:** `~/.agents/skills/` (Windows: `%USERPROFILE%\.agents\skills\`)
   - **Project-local:** `your-project/.claude/skills/` or `your-project/skills/`

### Option C — npx skills (if you use the skills CLI)

```bash
npx skills add shankardakolia/premium-website-master-skill
```

> If the CLI asks for a skill path, point it at this repo or the folder that contains `SKILL.md`.

### Option D — Project-local copy

Copy the whole repo into your project so teammates share the same skill:

```bash
cd your-project
git clone https://github.com/shankardakolia/premium-website-master-skill.git skills/premium-website-master
```

Then reference `@skills/premium-website-master/SKILL.md` (or your agent’s attach syntax).

---

## Install by agent

### 1. Claude Code

1. Clone into `~/.claude/skills/premium-website-master` (see Option A).
2. Restart Claude Code or open a new session.
3. Invoke with `/premium-website-master` if listed, or:

```text
Use the premium-website-master skill.
Preset 9 Horizon Real Estate
Brief: Luxury coastal villas in Goa for HNI buyers.
boom
```

### 2. Cursor

**Global / user rules**

1. Clone or copy `SKILL.md` content.
2. Cursor Settings → Rules / Custom Instructions → paste `SKILL.md`.

**Project rules**

1. Put the skill folder in the repo, e.g. `.cursor/skills/premium-website-master/`
2. Or add a project rule that says: follow `skills/premium-website-master/SKILL.md`
3. In chat: `@SKILL.md` then your preset + brief + `boom`

### 3. Grok (xAI) / Grok Build

1. Clone into `~/.agents/skills/premium-website-master` (macOS/Linux) or `%USERPROFILE%\.agents\skills\premium-website-master` (Windows).
2. Start a new session so skills are discovered.
3. Ask: `use /premium-website-master` or “use the premium website master skill”.

### 4. Claude.ai Projects

1. Create a Project.
2. Upload `SKILL.md` (and optionally `presets.md`).
3. Project instructions:

> You are the Premium Website Master Skill v2.1. Follow SKILL.md exactly. When the user selects a preset, gives a brief, and says boom, generate a complete one-shot premium website.

### 5. Windsurf / Cascade

1. Cascade → Custom Instructions → paste `SKILL.md`, **or**
2. Add the folder to the workspace and `@` reference `SKILL.md`.

### 6. Continue.dev (VS Code / JetBrains)

1. Open Continue config (`~/.continue/config.json`).
2. Add skill content to `systemMessage`, or attach the folder in chat context.
3. Use the preset + brief + `boom` format.

### 7. Aider

```bash
aider
/read path/to/premium-website-master-skill/SKILL.md
```

Then send: `Preset 4 Lumina Studio` + brief + `boom`.

### 8. GitHub Copilot / VS Code

- Paste `SKILL.md` into `.github/copilot-instructions.md`, or
- Use Copilot Chat custom instructions with the skill text.

### 9. Any other agent (Lovable, v0, Replit, ChatGPT, etc.)

At the start of the chat:

```text
You are now the Premium Website Master Skill v2.1.
Follow these rules exactly:
[paste full SKILL.md]
```

Then:

```text
Preset 18 Velora Fashion
Brief: Contemporary menswear label, editorial, black and white with gold accent.
boom
```

---

## Usage

### Format

```text
Preset <number> <optional name>
Brief: <industry, audience, offer, tone>
boom
```

### Examples

```text
Preset 15 Vesper Professional
Brief: Boutique law firm in London focusing on startups and IP. Trustworthy, calm, modern.
boom
```

```text
Preset 13 Verdant
Brief: Organic skincare brand, regenerative farming story, soft eco-luxury.
boom
```

### What you get

- One complete **single-file HTML** site (unless you ask for multi-file)
- Responsive layout
- Color switcher (3–4 palettes)
- Clear **scroll reveal** animations (fade + rise, staggered cards)
- Real sections from your brief (no lorem ipsum)
- Accessible focus states + `prefers-reduced-motion` support

### Suggested save path

```text
generated-websites/preset-06-solace-wellness/index.html
```

---

## 20 presets

| # | Name | Best for |
|---|------|----------|
| 1 | **Aether Luxury** | Quiet luxury, private wealth, brand advisory |
| 2 | **Nexus Frontier** | Agentic AI, frontier SaaS, developer tools |
| 3 | **Vanguard Bold** | Modern tech, infrastructure, cybersecurity |
| 4 | **Lumina Studio** | Creative agency, design studio |
| 5 | **Opulento** | Premium e-commerce, luxury goods |
| 6 | **Solace Wellness** | Wellness, spa, longevity, biohacking |
| 7 | **Forge Agency** | Film, experiential, production |
| 8 | **Pinnacle Wealth** | Wealth management, fintech, family office |
| 9 | **Horizon Real Estate** | Luxury real estate, property development |
| 10 | **Elysium Hospitality** | Boutique hotels, fine dining, clubs |
| 11 | **Karma Impact** | Nonprofit, foundation, impact orgs |
| 12 | **Apex Gaming** | Esports, gaming platforms |
| 13 | **Verdant** | Sustainable / regenerative brands |
| 14 | **Quill Media** | Podcast, newsletter, thought leadership |
| 15 | **Vesper Professional** | Law, consulting, professional services |
| 16 | **Cipher Web3** | Crypto, Web3, DeFi |
| 17 | **Bloom Education** | Courses, cohort learning |
| 18 | **Velora Fashion** | Fashion, editorial lifestyle |
| 19 | **Summit Corporate** | Executive / corporate leadership |
| 20 | **Nova Signature** | Personal brand, speaker, coach |

Full list: [`presets.md`](./presets.md) · Full rules: [`SKILL.md`](./SKILL.md)

---

## Repository layout

```text
premium-website-master-skill/
├── README.md      ← You are here (install + docs)
├── SKILL.md       ← Agent instructions (required)
├── presets.md     ← Preset cheat sheet
└── LICENSE        ← MIT
```

---

## Updating

**Git install:**

```bash
cd ~/.claude/skills/premium-website-master   # or your install path
git pull
```

**Windows PowerShell:**

```powershell
cd $env:USERPROFILE\.claude\skills\premium-website-master
git pull
```

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Agent ignores the skill | Attach or `@` `SKILL.md` explicitly; restart the agent |
| No scroll animations in output | Remind: “follow SKILL.md rule 8 — scroll reveals required” |
| Wrong aesthetic | Use preset **number + name** and a clear brief |
| Skill not listed | Confirm folder contains `SKILL.md` and sits under a skills directory your agent scans |
| Windows path issues | Prefer `%USERPROFILE%\.claude\skills\...` and Git for Windows |

---

## Live demo catalogue

Example portfolio built with this workflow (20 demos + master catalogue):

**https://noventra-portfolio.vercel.app**

---

## License

MIT — free to use, modify, and share. See [LICENSE](./LICENSE).

---

## Author

Published by [shankardakolia](https://github.com/shankardakolia).

**Install once. Use on Windows, macOS, or Linux. Boom.**
