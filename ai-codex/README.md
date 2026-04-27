# Manus Skills — Codex Plugin Marketplace

OpenAI Codex CLI plugin marketplace bundling **770 skills** into **14 themed plugins**.

Compatible with the Anthropic-originated Agent Skills standard adopted by OpenAI Codex in December 2025.

## Install

### Option A — drop the whole library into Codex skills folder

```bash
git clone https://github.com/onfire7777/manus-skills-codex.git
for plugin in manus-skills-codex/plugins/*/skills; do
  cp -r "$plugin"/* ~/.codex/skills/
done
```

### Option B — install only the plugins you want

```bash
git clone https://github.com/onfire7777/manus-skills-codex.git
cp -r manus-skills-codex/plugins/manus-reasoning-thinking/skills/* ~/.codex/skills/
cp -r manus-skills-codex/plugins/manus-security/skills/* ~/.codex/skills/
# ...etc
```

## Plugins

| Plugin | Skills | Purpose |
|--------|------:|---------|
| [`manus-ai-prompt-engineering`](plugins/manus-ai-prompt-engineering/) | 32 | AI and prompt engineering: LLM apps, agents, RAG, evals |
| [`manus-backend-architecture`](plugins/manus-backend-architecture/) | 55 | Backend architecture: APIs, system design, distributed systems, databases |
| [`manus-communication`](plugins/manus-communication/) | 25 | Communication: writing, presentations, facilitation, leadership |
| [`manus-creativity-innovation`](plugins/manus-creativity-innovation/) | 23 | Creativity and innovation: creative writing, art, ideation |
| [`manus-data-analysis`](plugins/manus-data-analysis/) | 16 | Data analysis: analytics, viz, statistics, ML/data pipelines |
| [`manus-devops-infra`](plugins/manus-devops-infra/) | 21 | DevOps and infrastructure: CI/CD, containers, cloud, IaC, SRE |
| [`manus-domain-specific`](plugins/manus-domain-specific/) | 1 | Narrow verticals: medical, legal, finance, scientific domains |
| [`manus-frontend-design`](plugins/manus-frontend-design/) | 113 | Frontend and design: UI/UX, web frontend, design systems, accessibility |
| [`manus-meta-skills`](plugins/manus-meta-skills/) | 109 | Meta-skills: skill creation, learning, productivity |
| [`manus-planning-strategy`](plugins/manus-planning-strategy/) | 68 | Planning and strategy: PM, strategic planning, roadmaps, OKRs |
| [`manus-privacy-compliance`](plugins/manus-privacy-compliance/) | 55 | Privacy and compliance: GDPR/CCPA/HIPAA, DPIAs, AI Act, ISO 27701 |
| [`manus-quality-engineering`](plugins/manus-quality-engineering/) | 46 | Quality engineering: code review, testing, debugging, refactoring |
| [`manus-reasoning-thinking`](plugins/manus-reasoning-thinking/) | 72 | Reasoning and thinking: mental models, critical thinking, epistemics |
| [`manus-security`](plugins/manus-security/) | 134 | Security skills: pentesting, exploits, hardening, crypto, AppSec/NetSec |

## Source

Skills sourced from [`onfire7777/manus-skills-library`](https://github.com/onfire7777/manus-skills-library).

Same library, three distribution formats:
- [`manus-skills-library`](https://github.com/onfire7777/manus-skills-library) — flat canonical store
- [`manus-skills-organized`](https://github.com/onfire7777/manus-skills-organized) — categorized browse view
- [`manus-skills-marketplace`](https://github.com/onfire7777/manus-skills-marketplace) — Claude Code plugin marketplace
- [`manus-skills-codex`](https://github.com/onfire7777/manus-skills-codex) — **this repo** — OpenAI Codex plugin marketplace
