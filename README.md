### Bonjour, I'm Fazal! 👋

**Software Engineer | French Dev in NYC 🗽🇫🇷**

Lead SWE @ Salesforce. 20+ years deterministic systems, now building and learning in public. Agent Evals, AI tooling and much more.

**Find me:** [shahfazal.com](https://shahfazal.com) | [LinkedIn](https://linkedin.com/in/shahfazalmohammed)

---

## Active Projects

### [CodeHaiku](https://github.com/shahfazal/lgtm-575) ![MIT](https://img.shields.io/badge/license-MIT-violet)

Eval-first fine-tuning: a Gemma 4 E4B model that writes PR review comments as 5-7-5 haiku (June 2026).

Built the eval harness before any training, then used the same harness to curate training data and gate a generate-check-revise loop around a Qwen3-30B-A3B teacher. A deterministic syllable checker (pyphen with snake_case decomposition, acronym overrides, low-confidence flags) catches form failures that loss curves cannot see.

**Tech stack:** Unsloth, TRL, PyTorch, pyphen, Python

**Shipped:**

- Fine-tuned model scored against a base-model floor and three golden numbers committed before training (bench-drop discipline)
- 5-7-5 form did not improve significantly (McNemar p=0.167); relevance and category cleared their pre-set targets
- Four-part blog series documenting the methodology and the audit of the eval itself
- [Project page](https://shahfazal.com/projects/codehaiku/) · [Writeup](https://shahfazal.com/posts/the-eval-before-the-model/)

---

### [CivicInsight](https://github.com/shahfazal/civicinsight) ![MIT](https://img.shields.io/badge/license-MIT-violet)

ARIA-ready descriptions for civic data visualizations. Submitted to the Kaggle Gemma 4 Good Hackathon (May 2026).

Fine-tuned [Gemma 4 E4B](https://huggingface.co/shahfazal/civicinsight-gemma4-e4b-it) on 61 hand-curated examples, paired with a deterministic verification layer that grounds extracted numbers against source CSV when available. Numbers from the model are treated as claims to be checked, not tokens to be trusted.

**Tech stack:** Unsloth, TRL, PyTorch, Modal, FastAPI, Python

**Shipped:**

- Fine-tuned model published to HuggingFace
- Deterministic verifier with four states (verified / partial / unverified / structural-issue)
- Live demo on Modal
- Two upstream vision DPO fixes contributed to [unslothai/unsloth#5196](https://github.com/unslothai/unsloth/issues/5196) (merged April 29, 2026)

---

### [Claudio](https://github.com/shahfazal/claudio) ![MIT](https://img.shields.io/badge/license-MIT-blue)

Session browser and observability tool for Claude Code. Eight shipped versions through v0.8.0:

- **v0.1-0.3:** Local session explorer, memory browser, compaction viewer
- **v0.4:** Resilience — environment health checks, session export endpoint, externalized pricing config
- **v0.5:** Stats dashboard — D3 heatmap, per-project cost bars, cumulative cost line, date-range filter
- **v0.6-0.7:** Guided help tour across nav surfaces; full session transcript rendering with per-session cost, todos, command history
- **v0.8:** Durable session store with background sync — mirrors live sessions into a persistent archive that protects history against Claude Code's retention sweeps, plus full-text search across archived transcripts

**Tech stack:** Python, Flask, Jinja2, D3.js, pytest

**Use case:** Browse and archive session history, review memory evolution, search transcripts, analyze cost and token usage across projects.

---

### [elections-municipales-2026](https://github.com/shahfazal/elections-municipales-2026) ![MIT](https://img.shields.io/badge/license-MIT-blue)

French municipal elections 2026 data viz.

- Live at [shahfazal.com/elections-municipales-2026](https://shahfazal.com/elections-municipales-2026/).
- [Submission](https://www.data.gouv.fr/reuses/prix-immobilier-et-resultats-electoraux-elections-municipales-2026) on data.gouv.fr.

**Data sources:** DVF (property prices), 2nd round results (Ministère de l'Intérieur)

**Stack:** Python + pandas (pipeline), Plotly.js (charts), Leaflet.js (maps), Driver.js (help tours), vanilla JS

**Shipped:**

- 5 interactive tabs: quintile breakdown, abstention box plot by bloc, Price distribution box plot, Paris-Lyon-Marseille choropleth, prix/m² vs abstention scatter plot with year toggle
- 838 communes analysed, DVF 2024 + 2025
- Guided tours, full French UI, accessibility attributes
- Published réutilisation on data.gouv.fr for the Défi 1 challenge

**Key lesson:** Declarative specs upfront beat imperative iteration. Full build log coming in blog series.

---

## Recent Contributions

### [datagouv/datagouv-mcp#115](https://github.com/datagouv/datagouv-mcp/pull/115) (merged)

Fixed `search_datasets` reporting `resources_count: 4` for every dataset. The v2 search API returns `resources` as a HATEOAS link dict, so the client was counting its 4 keys instead of reading `resources.total`. Found while using the MCP, isolated against the live API, locked with a regression unit test, and verified end-to-end through the local MCP loop (using the `call_tool.py` I shipped in #100).

**Impact:** Consuming models now see true per-dataset resource counts instead of a constant 4.

### [datagouv/datagouv-mcp#100](https://github.com/datagouv/datagouv-mcp/pull/100) (merged)

Reduced dev friction when testing the official French data.gouv.fr MCP server. Added a `/health` endpoint that runs a full MCP handshake plus tool call, and a `call_tool.py` script that replaces the manual 3-curl handshake with a single command.

**Impact:** Lowers barrier for contributors testing MCP integrations locally.

### [unslothai/unsloth#5199](https://github.com/unslothai/unsloth/pull/5199) (merged)

Filed [unslothai/unsloth#5196](https://github.com/unslothai/unsloth/issues/5196) reporting two vision DPO blockers on Gemma 4 (tokenization hang in `dataset.map` + data collator schema mismatch) with reproductions and documented workaround attempts. Fix merged into Unsloth main on April 29, 2026.

---

## Writing

Posts (and ramblings) at **[shahfazal.com/posts](https://shahfazal.com/posts)**:

- **["PR Reviews in Haiku, and the Eval That Mattered More"](https://shahfazal.com/posts/the-eval-before-the-model/)** (June 2026) - Four-part CodeHaiku writeup on building the eval before the model, and what format-constrained generation reveals that loss curves cannot see.
- **["Trained in America, Wrong in Paris"](https://shahfazal.com/posts/trained-in-america-wrong-in-paris/)** (May 2026) - Empirical study of LLM pretraining priors on civic data viz; five frontier models, systematic US-bias substitution.
- **["Engineering for Systems That Lie"](https://shahfazal.com/posts/engineering-for-systems-that-lie/)** (May 2026) - CivicInsight retrospective on fine-tuning, verification, and what 61 examples can and cannot teach a model.
- **["Nobody Tests the Steering Wheel"](https://shahfazal.com/posts/nobody-tests-the-steering-wheel/)** (2026) - Why agent evals need observe-first methodology.
- **Declarative Viz series (upcoming)** - Build log from elections-municipales-2026

---

## What I'm Working On

**Next up:** Decompressing from CodeHaiku. Picking up backlog projects.

**Backlog:**

- ADS-B + Gemma 4 voice assistant on Raspberry Pi (family collaborative project)
- TinyDiffusion (3-phase learning project: 1D scalar diffusion → 2x2 unconditional → 2x2 conditional)
- Public agent eval demo using datagouv-mcp
- AI workflow optimizer (analyzes Claudio session exports for inefficiency patterns)
- Plotly a11y toolkit

---

## ML Foundations

Before building production eval systems, rebuilt intuition from first principles:

- **[TinyNet](https://github.com/shahfazal/hello-neural-world)** - Neural net from scratch (Python, no frameworks)
- **[NYC EV LSTM](https://github.com/shahfazal/nyc-ev-charger-model)** - Spatio-temporal demand forecasting

These aren't production systems - they're foundational exercises to understand backprop, overfitting, and temporal modeling before applying those concepts to agent evaluation.

---

**Philosophy:** If it can't be measured, it can't be trusted. I apply 20+ years of production engineering rigor (observability, regression detection, test harness design) to the chaos of agentic systems.
