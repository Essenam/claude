# AI Capability Patterns

AI should feel like intelligence inside the product, not a feature bolted on. Each pattern: what it does, how it appears in UI, and how to build it safely.

| Capability | In the UI | Build notes |
|---|---|---|
| **Contextual copilot** | Side panel aware of the current record ("Summarize this deal's risks", "Draft a reply") with suggested prompts tailored to the page | Pass structured page context server-side; scope retrieval to records the user is authorized to read |
| **Matching** | "Top matches" list with a score, 3 reasons, and Accept / Dismiss / Why? | Hybrid: hard filters (rules) + weighted scoring + embeddings similarity; store reasons; learn from accept/dismiss |
| **Recommendations / next-best action** | Inline cards on dashboards: action, why, impact, one-click do it | Rules + model ranking; every card links to the action route |
| **Document intelligence / extraction** | Upload → extracted fields with confidence and source highlights → human confirm | Parse (PDF/OCR) → LLM structured output (JSON schema) → validation → review queue |
| **Scoring** | Score badge with breakdown drawer (factors, weights, data sources) | Transparent formula; LLM only for qualitative sub-scores; version the model |
| **Semantic search** | Search bar that understands intent; results with highlighted passages | Embeddings (pgvector) + keyword (BM25) hybrid; authorization filter before ranking |
| **Summarization** | "Brief" blocks on long records/threads, with "Show sources" | Cache by content hash; cite source records |
| **Anomaly detection** | Flags on records/charts: "Revenue in deck differs 18% from accounts" | Rules/statistics first; LLM to explain |
| **Scenario analysis** | Sliders/inputs → projected outcomes with assumptions listed | Deterministic model in code; LLM narrates, never computes the numbers |

## Principles
- **Actionable:** every AI output has a next action.
- **Explainable:** reasons, sources, and confidence are always one click away.
- **Human in control:** consequential actions require confirmation; AI drafts, people decide.
- **Authorized:** retrieval respects the same permissions as the rest of the app.
- **Resilient:** deterministic fallback when the model/key is unavailable, so demos never break. Mark fallback outputs as simulated in the handoff.
- **Server-side only:** keys and prompts live on the server; validate model output against a schema.
- **Evaluated:** keep a small set of test cases for each AI feature and run them.
