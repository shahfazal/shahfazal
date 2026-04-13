### Bonjour, I'm Faz! 👋

**Software Engineer | French Dev in NYC 🗽🇫🇷**

Lead SWE @ Salesforce. 20 years deterministic systems, now building and learning in public. Agent Evals, AI tooling and much more.

**Find me:** [shahfazal.com](https://shahfazal.com) | [LinkedIn](https://linkedin.com/in/shahfazalmohammed)

---

## Active Projects

### [Claudio](https://github.com/shahfazal/claudio) ![MIT](https://img.shields.io/badge/license-MIT-blue)

Session browser for Claude Code. Three shipped versions:

- **v0.1:** Local session explorer (parses `~/.claude/` directory)
- **v0.2:** Memory browser (reads project memory states)

- **v0.3:** Compaction viewer (analyzes context window compression)
  **Tech stack:** Python, Rich TUI, file parsing, session state reconstruction

**Use case:** Debug Claude Code workflows, review memory evolution, analyze token usage across compactions.

---

### [elections-municipales-2026](https://github.com/shahfazal/elections-municipales-2026) ![MIT](https://img.shields.io/badge/license-MIT-blue)

French municipal elections data viz. Live at [shahfazal.com/elections-municipales-2026](https://shahfazal.com/elections-municipales-2026/)

**Data sources:** DVF (property prices), Results from the 2nd tour of French municipal elections
**Stack:** Jupyter notebooks for data processing from raw to processed, Plotly, Vanilla JS, D3.

**Shipped:**

**Key lesson:** Declarative specs upfront beat imperative iteration. Full build log coming in blog series.

---

## Recent Contributions

### [datagouv/datagouv-mcp#100](https://github.com/datagouv/datagouv-mcp/pull/100)

PR in review for reducing dev friction when testing the official French data.gouv.fr MCP server. Reduced setup from 3-curl handshake to single command.

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

- **[TinyNet](https://github.com/shahfazal/tinynet)** - Neural net from scratch (Python, no frameworks)
- **[NYC EV LSTM](https://github.com/shahfazal/nyc-ev-lstm)** - Spatio-temporal demand forecasting

These aren't production systems - they're foundational exercises to understand backprop, overfitting, and temporal modeling before applying those concepts to agent evaluation.

---

**Philosophy:** If it can't be measured, it can't be trusted. I apply 20 years of production engineering rigor (observability, regression detection, test harness design) to the chaos of agentic systems.
