### Bonjour, I'm Faz! 👋

**Software Engineer | French Dev in NYC 🗽🇫🇷**

Lead SWE @ Salesforce. 20+ years deterministic systems, now building and learning in public. Agent Evals, AI tooling and much more.

**Find me:** [shahfazal.com](https://shahfazal.com) | [LinkedIn](https://linkedin.com/in/shahfazalmohammed)

---

## Active Projects

### [Claudio](https://github.com/shahfazal/claudio) ![MIT](https://img.shields.io/badge/license-MIT-blue)

Session browser for Claude Code. Five shipped versions:

- **v0.1:** Local session explorer (parses `~/.claude/` directory)
- **v0.2:** Memory browser (reads project memory states)
- **v0.3:** Compaction viewer (analyzes context window compression)
- **v0.4:** Resilience — environment health checks, session export endpoint, externalized pricing config
- **v0.5:** Stats dashboard — D3 heatmap, per-project cost bars, cumulative cost line, date-range filter, graceful degradation on parse failures

**Upcoming:** Driver.js guided help tour across the nav surfaces
**Tech stack:** Python, Flask, Jinja2, D3.js, pytest

**Use case:** Browse session history, review memory evolution, analyze cost and token usage across projects.

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

### [datagouv/datagouv-mcp#100](https://github.com/datagouv/datagouv-mcp/pull/100) (merged)

Reduced dev friction when testing the official French data.gouv.fr MCP server. Added a `/health` endpoint that runs a full MCP handshake plus tool call, and a `call_tool.py` script that replaces the manual 3-curl handshake with a single command.

**Impact:** Lowers barrier for contributors testing MCP integrations locally.

---

## Writing

Posts (and ramblings) at **[shahfazal.com/posts](https://shahfazal.com/posts)**:

- **"Nobody Tests the Steering Wheel"** - Why agent evals need observe-first methodology
- **"Claude Gatekeep You Yet?"** - why it's important to stop and think before handing the reins to your coding agent.
- **Declarative Viz series (upcoming)** - Build log from elections-municipales-2026

---

## What I'm Working On

**Next up:** Public agent eval demo using `datagouv-mcp` as the skill under test. Goal: show how to treat LLM skills like code (version, test, regression-detect).

**Backlog:**

- AI workflow optimizer (analyzes Claudio session exports for inefficiency patterns)
- Supply chain security scanner for AI-suggested dependencies
- Plotly a11y toolkit

---

## ML Foundations

Before building production eval systems, rebuilt intuition from first principles:

- **[TinyNet](https://github.com/shahfazal/hello-neural-world)** - Neural net from scratch (Python, no frameworks)
- **[NYC EV LSTM](https://github.com/shahfazal/nyc-ev-lstm)** - Spatio-temporal demand forecasting

These aren't production systems - they're foundational exercises to understand backprop, overfitting, and temporal modeling before applying those concepts to agent evaluation.

---

**Philosophy:** If it can't be measured, it can't be trusted. I apply 20+ years of production engineering rigor (observability, regression detection, test harness design) to the chaos of agentic systems.
