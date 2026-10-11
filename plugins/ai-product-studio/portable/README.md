# Using AI Product Studio outside Claude Code

`AI-PRODUCT-STUDIO.md` is the whole studio — start command, four skills, and every reference — compiled into one file. Regenerate it after editing any skill:

```bash
./scripts/build-portable.sh
```

| Host | How to install |
|---|---|
| **Claude Code** | Use the plugin itself (see the repository README). |
| **Claude.ai Projects** | Upload `AI-PRODUCT-STUDIO.md` as project knowledge; in the project instructions write: "Follow AI-PRODUCT-STUDIO.md for every product request." |
| **ChatGPT / ChatGPT Work (Custom GPT or Project)** | Upload `AI-PRODUCT-STUDIO.md` as a knowledge file. Instructions: "You are AI Product Studio. Follow the uploaded AI-PRODUCT-STUDIO.md exactly. Use Canvas/code execution and web browsing to build and curate media whenever available." |
| **OpenAI Codex / any AGENTS.md agent** | Copy to the repo root as `AGENTS.md` (or append it to the existing one). |
| **Cursor** | Save as `.cursor/rules/ai-product-studio.mdc` with front matter `alwaysApply: false` and `description: Product creation studio`, then invoke with `@ai-product-studio`. |
| **VS Code / GitHub Copilot agent mode** | Save as `.github/copilot-instructions.md`, or as `.github/instructions/ai-product-studio.instructions.md`. |
| **Windsurf / Cline / Roo** | Save as `.windsurfrules`, `.clinerules`, or the tool's rules file. |
| **Replit Agent / Lovable / Bolt / v0** | Paste into the project's custom-instructions / knowledge setting (trim the appendices if there's a length limit — keep the start command and four skills). Start each project with: "Run AI Product Studio on: …". |

Short-limit hosts: the start command and four skill sections alone (≈ the first half of the file) carry the method; the appendices add templates and checklists.
