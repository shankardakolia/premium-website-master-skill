# Premium Website Master Skill v2.3.3

**One-shot premium website generator** with **20 named design presets** and a **live demo catalogue**.

Turn any coding agent into a high-end website designer: pick a preset → give a brief → say **boom** → get a complete, client-ready single-file HTML site.

| Feature | Included |
|--------|----------|
| 20 unique design presets | Yes |
| Live demo catalogue (`show`) | Yes |
| Single-file HTML (CSS + JS inline) | Yes |
| Fully responsive (375px–1440px+) | Yes |
| Built-in color switcher | Yes |
| Dark / light mode toggle (navbar) | Yes |
| Temporary stock images on first gen | Yes (swap later) |
| Scroll-triggered reveal animations | Yes (required) |
| Real copy from your brief | Yes |
| Cross-platform install (Windows / macOS / Linux) | Yes |

**Repository:** [github.com/shankardakolia/premium-website-master-skill](https://github.com/shankardakolia/premium-website-master-skill)

---

## Quick start

1. Install this skill (see [Installation](#installation) below).
2. **Browse live demos** (optional):

```text
/premium-website-master show
```

Prints all 20 exact preset names with hosted demo links (e.g. `https://noventra-portfolio.vercel.app/Bloom%20Florist/index.html`).

3. In your agent chat, generate a site:

```text
Preset 6 Solace Wellness
Brief: Premium longevity clinic in Dubai for high-net-worth clients. Calm organic luxury.
boom
```

4. The agent generates one complete `index.html` (or a path you specify).

Also accepted:

- `Preset 6`
- `Solace Wellness`
- `Preset 6 Solace Wellness`
- `show` / `catalogue` / `demos`

---

## Installation

Works on **Windows**, **macOS**, and **Linux**. Choose the method that matches your agent.

### Option A — Clone with Git (recommended)

**macOS / Linux (Terminal):**

```bash
# Grok CLI (global — available in every folder/session)
mkdir -p ~/.grok/skills
git clone https://github.com/shankardakolia/premium-website-master-skill.git \
  ~/.grok/skills/premium-website-master

# Claude Code / many agents
mkdir -p ~/.claude/skills
git clone https://github.com/shankardakolia/premium-website-master-skill.git \
  ~/.claude/skills/premium-website-master

# Agents / Cursor-style location (also discovered by Grok)
mkdir -p ~/.agents/skills
git clone https://github.com/shankardakolia/premium-website-master-skill.git \
  ~/.agents/skills/premium-website-master
```

**Windows (PowerShell):**

```powershell
# Grok CLI (global)
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.grok\skills" | Out-Null
git clone https://github.com/shankardakolia/premium-website-master-skill.git `
  "$env:USERPROFILE\.grok\skills\premium-website-master"

# Claude Code skills
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills" | Out-Null
git clone https://github.com/shankardakolia/premium-website-master-skill.git `
  "$env:USERPROFILE\.claude\skills\premium-website-master"

# Agents skills folder
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
   - **Grok CLI (global):** `~/.grok/skills/` (Windows: `%USERPROFILE%\.grok\skills\`) — **required for the skill to appear in every Grok session**
   - **Claude Code:** `~/.claude/skills/` (Windows: `%USERPROFILE%\.claude\skills\`)
   - **Agents:** `~/.agents/skills/` (Windows: `%USERPROFILE%\.agents\skills\`)
   - **Project-local:** `your-project/.grok/skills/` or `your-project/.agents/skills/`

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

**Global install (recommended — works in every folder):**

1. Clone into **`~/.grok/skills/premium-website-master`** (macOS/Linux) or `%USERPROFILE%\.grok\skills\premium-website-master` (Windows).
   - Optional mirror: also install to `~/.agents/skills/premium-website-master`.
2. Open a **new** Grok session in any project folder (skills reload from disk; existing sessions may not pick up a new install).
3. Confirm: `grok inspect` should list `premium-website-master` as `user`.
4. Run:

```text
/premium-website-master show
```

or

```text
/premium-website-master
Preset 6 Solace Wellness
Brief: …
boom
```

If the slash menu is crowded (many skills), type `/premium` to filter.

**Why it only appeared in the skill repo before:** installing only under a project path (or only updating the git repo) does not register a user skill. Grok’s global skill directory is `~/.grok/skills/`.

### 4. Claude.ai Projects

1. Create a Project.
2. Upload `SKILL.md` (and optionally `presets.md`, `catalogue.md`).
3. Project instructions:

> You are the Premium Website Master Skill v2.3.3. Follow SKILL.md exactly. On `show`, print the live catalogue. When the user selects a preset, gives a brief, and says boom, generate a complete one-shot premium website.

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
You are now the Premium Website Master Skill v2.3.3.
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

### Show live catalogue

```text
/premium-website-master show
```

Output: every exact preset name + live demo URL from the hosted portfolio  
(hub: https://noventra-portfolio.vercel.app). Full map: [`catalogue.md`](./catalogue.md).

### Format (generate)

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
- **Dark / light mode** toggle in the navbar (persisted)
- Temporary stock photography on first generation (replace with brand assets later)
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
├── catalogue.md   ← Live demo URLs for /show
└── LICENSE        ← MIT
```

---

## Updating

**Git install:**

```bash
cd ~/.grok/skills/premium-website-master   # or ~/.claude/... / ~/.agents/...
git pull
```

**Windows PowerShell:**

```powershell
cd $env:USERPROFILE\.grok\skills\premium-website-master
git pull
```

If you keep a copy of the skill repo elsewhere, re-sync into the install path after edits:

```bash
cp SKILL.md presets.md catalogue.md README.md LICENSE ~/.grok/skills/premium-website-master/
# optional mirror
cp SKILL.md presets.md catalogue.md README.md LICENSE ~/.agents/skills/premium-website-master/
```

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| Skill only works in the skill repo folder | Install to **`~/.grok/skills/premium-website-master`**, then open a **new** session elsewhere |
| Skill not listed in other folders | Run `grok inspect` — should show `premium-website-master` as `user`. If missing, reinstall under `~/.grok/skills/` |
| Slash command hard to find | Type `/premium` to filter; or open `/skills` |
| Agent ignores the skill | Invoke `/premium-website-master` explicitly; restart the agent |
| No scroll animations in output | Remind: “follow SKILL.md rule 8 — scroll reveals required” |
| Wrong aesthetic | Use preset **number + name** and a clear brief |
| Windows path issues | Prefer `%USERPROFILE%\.grok\skills\...` and Git for Windows |

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
