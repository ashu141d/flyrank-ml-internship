# ML Study & Repo Verification Coach (Personal AI Agent)

A source-grounded personal AI agent built on **Claude Desktop + Model Context Protocol (MCP)** that inspects local machine learning notebooks and Markdown study notes to verify data contracts, prevent feature leakage, and run Socratic concept checks before code is committed.

## Who It Is For
Designed for ML engineering interns and students working across multi-week notebook pipelines who want fast, file-grounded schema verification and study recall without hallucinated column names or accidental notebook edits.

## Architecture Overview

```text
[Deepak (User Prompt)]
         │
         ▼
[Claude Desktop Project: System Instructions + Guardrails]
         │
         ├──► [Filesystem MCP Server (Read-Only on work/notebooks/)]
         │         └─ Inspects w03_data_contract.ipynb, w04_baseline_score.ipynb, etc.
         │
         └──► [Filesystem MCP Server (Read + Confirmation-Gated Write on study-notes/)]
                   └─ Reads study notes; writes drafts ONLY after explicit user approval
