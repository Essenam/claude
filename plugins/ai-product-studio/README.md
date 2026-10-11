# AI Product Studio

An autonomous product-creation agent packaged as a Claude Code plugin. It turns an idea, rough description, business requirements, PRD, screenshots, existing website, prototype, or codebase into a working digital product: a website, web app, SaaS platform, marketplace, portal, dashboard, enterprise app, AI product, interactive prototype, functional MVP, or production-ready application.

It works like one multidisciplinary team: strategy, product, UX, creative direction, UI, interaction, brand, front-end, back-end, data, AI, security, QA, and DevOps.

> **The quality test:** *Would a customer, investor, executive, or developer believe this is already a sophisticated real product?* If not, keep improving it.

## What's inside

| Component | Role |
|---|---|
| `/ai-product-studio:studio` | Start command. Runs the 10-stage pipeline: read → inspect → architect → direct → choose build level → build → inspect → improve → test → deliver. |
| `product-architect` skill | Personas, jobs-to-be-done, entities, workflows, separate role-specific environments, information architecture, page inventory, MVP scope, and integrations. |
| `experience-director` skill | Narrative, brand, type, color, curated photography and video, motion system, layout rhythm, and anti-template rules. |
| `product-builder` skill | Builds the product at the highest feasible level (L1 concept → L2 prototype → L3 MVP → L4 production): frontend, backend, database, auth, server-enforced authorization, files, AI, security, observability, tests, and a handoff that marks what is real and what is simulated. |
| `product-reviewer` skill | Runs and looks at the rendered product, scores 14 dimensions, fixes anything below 4/5, and repeats. |
| `portable/AI-PRODUCT-STUDIO.md` | All of the above in one file for ChatGPT, Codex, Cursor, VS Code, Replit, Lovable, Bolt, and other tools. |

## Install (Claude Code)

```text
/plugin marketplace add Essenam/claude
/plugin install ai-product-studio@essenam-plugins
```

To use a local checkout instead: `/plugin marketplace add /path/to/this/repo`.

## Use

```text
/ai-product-studio:studio A marketplace connecting diaspora investors with vetted SMEs in Ghana and Kenya. Build this.
/ai-product-studio:studio ./docs/PRD.pdf --level 3
/ai-product-studio:studio Redesign https://example.com into a premium product site with a working client portal
```

The skills also load on their own when a task matches. For example, "make this landing page feel less generic" triggers `experience-director`, and "QA this app before the demo" triggers `product-reviewer`.

## Operating principles

- **Build, don't just advise.** If the environment can create the product, the studio creates it.
- **Assume, then document.** It makes professional calls instead of asking about every detail, and lists its assumptions. It asks only when the answer would materially change the product or when there's real risk.
- **Every audience gets its own product.** Each one has its own landing page, dashboard, nav, KPIs, vocabulary, workflows, tools, and data. All of them share one design system.
- **Media is part of the product.** It curates photography and video with a consistent look, records licensing, and avoids AI clichés.
- **Realistic, clearly labeled demo data.** No "Project A" or "User 123".
- **Authorization is enforced on the server**, never by hiding UI.
- **It reviews the rendered product, not just the code.** Compiling doesn't mean it's good.
- **Honest handoff.** A REAL vs. SIMULATED table, the architecture, data model, APIs, environment variables, deployment notes, and what production still needs.

## Layout

```
plugins/ai-product-studio/
├── .claude-plugin/plugin.json
├── commands/studio.md
├── skills/
│   ├── product-architect/    SKILL.md + references/ (architecture template, multi-audience matrix)
│   ├── experience-director/  SKILL.md + references/ (creative direction, media curation, motion, anti-patterns)
│   ├── product-builder/      SKILL.md + references/ (demo data, AI patterns, checklists, handoff)
│   └── product-reviewer/     SKILL.md + references/ (scorecard)
├── portable/                 single-file version + per-tool setup
└── scripts/build-portable.sh regenerates the portable file
```
