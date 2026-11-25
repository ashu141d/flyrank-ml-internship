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
---

### 2. 2–3 Minute Demo Video Script (`FL-09`)

Record a single **2–3 minute screen capture** (no background music, clear narration) following these four beats[cite: 20]:
1. **0:00 – 0:30 (What it is & setup):** Show your `README.md` and `claude_desktop_config.json` briefly, explaining that the agent runs on Claude Desktop connected to your local repo via Filesystem MCP[cite: 20].
2. **0:30 – 1:45 (Live real run + non-trivial exchange):** Run a real prompt in Claude Desktop asking it to compare column definitions between two notebooks in `work/notebooks/` and draft a note in `study-notes/drafts/`. Show the live MCP tool calls firing, the agent pausing before writing the file, and your explicit confirmation reply[cite: 20].
3. **1:45 – 2:15 (One design decision):** Explain *why* you scoped MCP permissions strictly to `study-notes/` and `work/` with a mandatory human confirmation gate before any file write—preventing the agent from ever corrupting `.ipynb` JSON cells[cite: 20].
4. **2:15 – 2:45 (One honest limitation):** State clearly that the agent inspects code statically rather than executing Python kernels, so runtime shape errors or dataset streaming issues still require running the notebook in Google Colab[cite: 20].

---

### 3. 400–600 Word Retrospective (`FL-10` — Written to Week-1 Deepak)

Save this as `RETROSPECTIVE.md` in your final package (485 words)[cite: 20]:

> **Dear Week-1 Deepak,**
>
> Eight weeks ago, you opened your first AI assignment thinking "being good with AI" mostly meant finding cleverer one-line prompts. You treated chat windows like magic vending machines: paste a problem in, copy whatever text came out, and hope the code ran or the summary sounded smart. Today, looking at the live portfolio site, the leak-free ML evaluation pipeline, and the personal MCP agent sitting in your repository, the biggest change isn't a secret prompt template—it is how you structure the work around the model.
>
> Here is what you can actually build and ship now that you couldn't on Day 1. You can take a messy 80-million-row search dataset, define a strict data contract before touching a classifier, catch target leakage with client-grouped cross-validation (`GroupKFold`), and deploy a reproducible research report on GitHub Pages. On the fluency side, you can design, scope, and wire a tool-connected personal agent using the Model Context Protocol (MCP) that reads real local files, enforces confirmation guardrails before writing anything to disk, and tests itself against pre-built evaluation cases. You also went from having zero web presence to shipping a live, mobile-tested, analytics-verified portfolio site with working backend form handling and an official credential badge.
>
> What changed most in how you work is moving from **prompting** to **systems thinking and verification**. You learned to separate workflows from true agents, to write down constraints and failure modes *before* choosing a tech stack, and to keep a human in the loop at every irreversible step. When you audited your own validation splits and stress-tested your portfolio on a real phone, you saw firsthand how easily unverified outputs hide silent bugs—whether that is group leakage inflating a PR-AUC score or a 14px input triggering mobile auto-zoom. Instead of defending first drafts, you now treat every output as a hypothesis to be tested against eval cases, peer critique, and real edge cases.
>
> If you were starting Week 1 over again, there is one thing you would do differently immediately: **build the evaluation harness and data/file structure on Day 1 instead of retrofitting them later.** Early on, you spent extra time cleaning up ad-hoc notes, renaming random deployment subdomains, and reorganizing folders after the fact. Writing down five concrete pass/fail test cases and locking a clean folder structure before writing the first line of code saves hours of rework.
>
> Keep that habit—scope tight, verify everything against real inputs, and never ship an uninspected output. Everything you built over these eight weeks proves you don't need hype to build reliable AI systems; you just need clear constraints and disciplined iteration.

---

### 4. Public Post & Final Submission Package Checklist (`FL-10`)

#### Public Post Copy (LinkedIn / X)
> Over the past 8 weeks in the FlyRank AI Internship, I shifted from writing one-off prompts to shipping verifiable AI systems.
>
> For my General AI Fluency capstone, I built a source-grounded **ML Study & Repo Verification Coach** on Claude Desktop using the Model Context Protocol (MCP). Instead of guessing schemas from memory, it inspects my local ML notebooks and study notes directly, quizzes me on validation concepts, and enforces a strict human-confirmation gate before writing any summary files.
>
> Alongside it, I shipped my live portfolio (`[https://deepak-chowdhary.netlify.app](https://deepak-chowdhary.netlify.app)`) and an end-to-end leak-free ML capstone paper on content decay prioritization (`[https://ashu141d.github.io/flyrank-ml-internship/](https://ashu141d.github.io/flyrank-ml-internship/)`).
>
> Full agent repo, setup guide, eval results, and demo walkthrough: `[https://github.com/ashu141d/flyrank-ml-internship](https://github.com/ashu141d/flyrank-ml-internship)`

#### Final Package Checklist (Before Clicking Submit)
Ensure your shared repo/folder contains all **5 required items**[cite: 20]:
1. `README.md` (above)[cite: 20]
2. `instructions.md` (your `FL-06` system instructions)[cite: 20]
3. `claude_desktop_config.json` (your MCP server config)[cite: 20]
4. `evals.md` (your 5 pre-build eval cases from `FL-06` + actual pass/fail results from running your agent)[cite: 20]
5. `RETROSPECTIVE.md` (above) + link to your 2–3 minute demo video[cite: 20]

Post both deliverables in the FlyRank **Show-and-Tell showcase thread**, publish your public social post, and paste your final package link + demo link into the **Add submission** box on this card[cite: 20].
