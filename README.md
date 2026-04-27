# Manus Skills Marketplace

Multi-AI plugin distribution: **770 skills** packaged as **14 themed plugins** for both Anthropic Claude Code and OpenAI Codex CLI. Same skills, two manifest formats — pick the one that matches your tool.

## Install — Claude Code / Cowork

```bash
/plugin marketplace add onfire7777/manus-skills-marketplace
```

Then activate any of the 14 plugins:

```bash
/plugin install manus-security@manus-skills-marketplace
/plugin install manus-reasoning-thinking@manus-skills-marketplace
# (see Categories table below for the full list)
```

## Install — OpenAI Codex CLI

Codex doesn't have a marketplace registry — its native install is flat. Copy from `ai-codex/plugins/` into `~/.codex/skills/`:

```bash
git clone https://github.com/onfire7777/manus-skills-marketplace.git
# All 770:
for plugin in manus-skills-marketplace/ai-codex/plugins/*/skills; do
  cp -r "$plugin"/* ~/.codex/skills/
done
# Or one category at a time:
cp -r manus-skills-marketplace/ai-codex/plugins/manus-reasoning-thinking/skills/* ~/.codex/skills/
```

Codex auto-discovers on next session.

## Layout

```
manus-skills-marketplace/
├── .claude-plugin/marketplace.json     # Claude marketplace registry
├── plugins/                            # CLAUDE plugin format (14 plugins)
│   ├── manus-security/
│   │   ├── plugin.json                 # Claude manifest
│   │   ├── README.md
│   │   └── skills/<slug>/SKILL.md
│   └── ... (13 more)
└── ai-codex/                           # OPENAI CODEX plugin format
    └── plugins/                        # (14 plugins, same skills)
        ├── manus-security/
        │   ├── .codex-plugin/plugin.json   # Codex manifest
        │   ├── README.md
        │   └── skills/<slug>/SKILL.md
        └── ... (13 more)
```

The same SKILL.md files appear in both `plugins/` and `ai-codex/plugins/`. Only the manifest format differs (each ecosystem expects its own).

## Categories

| # | Browse folder | Plugin name | Skills | Purpose |
|--:|---|---|--:|---|
| 01 | `01-security` | `manus-security` | 134 | Security: pentesting, exploits, hardening, crypto, AppSec/NetSec |
| 02 | `02-privacy-compliance` | `manus-privacy-compliance` | 55 | Privacy and compliance: GDPR/CCPA/HIPAA, DPIAs, AI Act, ISO 27701 |
| 03 | `03-frontend-design` | `manus-frontend-design` | 113 | Frontend and design: UI/UX, web frontend, design systems, accessibility |
| 04 | `04-backend-architecture` | `manus-backend-architecture` | 55 | Backend architecture: APIs, system design, distributed systems, databases |
| 05 | `05-devops-infra` | `manus-devops-infra` | 21 | DevOps and infrastructure: CI/CD, containers, cloud, IaC, SRE |
| 06 | `06-ai-prompt-engineering` | `manus-ai-prompt-engineering` | 32 | AI and prompt engineering: LLM apps, agents, RAG, evals |
| 07 | `07-data-analysis` | `manus-data-analysis` | 16 | Data analysis: analytics, viz, statistics, ML/data pipelines |
| 08 | `08-reasoning-thinking` | `manus-reasoning-thinking` | 72 | Reasoning and thinking: mental models, critical thinking, epistemics |
| 09 | `09-creativity-innovation` | `manus-creativity-innovation` | 23 | Creativity and innovation: creative writing, art, ideation |
| 10 | `10-planning-strategy` | `manus-planning-strategy` | 68 | Planning and strategy: PM, strategic planning, roadmaps, OKRs |
| 11 | `11-communication` | `manus-communication` | 25 | Communication: writing, presentations, facilitation, leadership |
| 12 | `12-quality-engineering` | `manus-quality-engineering` | 46 | Quality engineering: code review, testing, debugging, refactoring |
| 13 | `13-meta-skills` | `manus-meta-skills` | 109 | Meta-skills: skill creation, learning, productivity |
| 14 | `14-domain-specific` | `manus-domain-specific` | 1 | Narrow verticals: medical, legal, finance, scientific domains |


## Install everything in one command

Claude Code:
```
/plugin marketplace add onfire7777/manus-skills-marketplace
/plugin install manus-security@manus-skills-marketplace
/plugin install manus-privacy-compliance@manus-skills-marketplace
/plugin install manus-frontend-design@manus-skills-marketplace
/plugin install manus-backend-architecture@manus-skills-marketplace
/plugin install manus-devops-infra@manus-skills-marketplace
/plugin install manus-ai-prompt-engineering@manus-skills-marketplace
/plugin install manus-data-analysis@manus-skills-marketplace
/plugin install manus-reasoning-thinking@manus-skills-marketplace
/plugin install manus-creativity-innovation@manus-skills-marketplace
/plugin install manus-planning-strategy@manus-skills-marketplace
/plugin install manus-communication@manus-skills-marketplace
/plugin install manus-quality-engineering@manus-skills-marketplace
/plugin install manus-meta-skills@manus-skills-marketplace
/plugin install manus-domain-specific@manus-skills-marketplace
```

Codex CLI:
```bash
git clone https://github.com/onfire7777/manus-skills-marketplace.git /tmp/manus-mp
mkdir -p ~/.codex/skills
for d in /tmp/manus-mp/ai-codex/plugins/*/skills/*/; do cp -rn "$d" ~/.codex/skills/; done
rm -rf /tmp/manus-mp
```

## Companion repos

These three repos hold the **same 770 skills** in different layouts. Use whichever fits your workflow:

| Repo | Role | Layout |
|---|---|---|
| [`manus-skills-library`](https://github.com/onfire7777/manus-skills-library) | **Canonical store** | Flat `skills/<slug>/SKILL.md` |
| [`manus-skills-organized`](https://github.com/onfire7777/manus-skills-organized) | **Browse view** | Numbered category folders `skills/<NN-category>/<slug>/` |
| [`manus-skills-marketplace`](https://github.com/onfire7777/manus-skills-marketplace) | **Install distribution** | Plugin format for Claude Code (`plugins/`) and OpenAI Codex CLI (`ai-codex/plugins/`) |

## Naming convention (consistent across all three repos)

Same 14 category slugs everywhere. Prefix differs only by purpose:

- **Skill slug:** `aes-encryption`, `motion-canvas`, `thinking-bayesian` (kebab-case, no prefix)
- **Browse folder:** `01-security`, `02-privacy-compliance`, ... (numeric prefix sorts naturally for navigation)
- **Plugin identifier:** `manus-security`, `manus-privacy-compliance`, ... (`manus-` namespace prefix for plugin ecosystems)


## Format compatibility

Skills use the **Agent Skills standard** — adopted by Anthropic in October 2025 and OpenAI Codex/ChatGPT in December 2025, then released as an open spec on 2025-12-18. Same SKILL.md works in:

- Claude Code (this repo's `plugins/`)
- Cowork (same as Claude Code)
- OpenAI Codex CLI (this repo's `ai-codex/plugins/`)
- ChatGPT Skills (Business/Enterprise/Edu beta) — upload as ZIP via Settings → Skills
