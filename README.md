# Manus Skills Marketplace

Multi-AI plugin marketplace bundling **771 skills** into **14 themed plugins**, with format adapters for both Anthropic Claude Code and OpenAI Codex CLI.

The underlying skills are identical across both formats — same SKILL.md files. Only the plugin manifests differ to match each ecosystem's plugin loader.

## Layout

```
manus-skills-marketplace/
├── .claude-plugin/marketplace.json       # Claude Code marketplace registry
├── plugins/                              # CLAUDE CODE plugins (14, plugin.json format)
│   ├── manus-security/
│   ├── manus-reasoning-thinking/
│   └── ... (12 more)
└── ai-codex/                             # OPENAI CODEX plugins (same skills, .codex-plugin/plugin.json format)
    └── plugins/
        ├── manus-security/
        ├── manus-reasoning-thinking/
        └── ... (12 more)
```

## Install — Claude Code / Cowork

```bash
/plugin marketplace add onfire7777/manus-skills-marketplace
/plugin install manus-reasoning-thinking@manus-skills-marketplace
# (repeat for any of the 14 plugins, see the bottom of this README for the full list)
```

## Install — OpenAI Codex CLI

```bash
git clone https://github.com/onfire7777/manus-skills-marketplace.git
# install all
for plugin in manus-skills-marketplace/ai-codex/plugins/*/skills; do
  cp -r "$plugin"/* ~/.codex/skills/
done

# or install one at a time
cp -r manus-skills-marketplace/ai-codex/plugins/manus-reasoning-thinking/skills/* ~/.codex/skills/
```

Codex auto-detects the new skills at the start of the next session.

## Plugins (same 14 in both formats)

| Plugin | Skills |
|---|---:|
| `manus-ai-prompt-engineering` | 32 |
| `manus-backend-architecture` | 55 |
| `manus-communication` | 25 |
| `manus-creativity-innovation` | 23 |
| `manus-data-analysis` | 16 |
| `manus-devops-infra` | 21 |
| `manus-domain-specific` | 1 |
| `manus-frontend-design` | 113 |
| `manus-meta-skills` | 109 |
| `manus-planning-strategy` | 68 |
| `manus-privacy-compliance` | 55 |
| `manus-quality-engineering` | 46 |
| `manus-reasoning-thinking` | 72 |
| `manus-security` | 134 |

## Companion repos

- [`manus-skills-library`](https://github.com/onfire7777/manus-skills-library) — flat canonical store of 771 skills
- [`manus-skills-organized`](https://github.com/onfire7777/manus-skills-organized) — categorized browse view (14 numbered folders)
- **`manus-skills-marketplace`** — this repo — multi-AI plugin distributions

## Format compatibility

Skills use the **Agent Skills standard** — adopted by Anthropic in October 2025 and OpenAI Codex in December 2025, then released as an open spec on December 18, 2025. The same SKILL.md files work in:

- Claude Code (via the `plugins/` tree + `.claude-plugin/marketplace.json`)
- Cowork (same as Claude Code)
- OpenAI Codex CLI (via `ai-codex/plugins/` tree, `.codex-plugin/plugin.json` manifests)
- ChatGPT Skills (Business/Enterprise/Edu plans, beta) — upload as ZIP

For ChatGPT Skills upload bundles, see the chatgpt-bundles directory in the build output (or generate them with the build script in the source).
