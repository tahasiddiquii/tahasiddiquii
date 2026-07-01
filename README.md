# Taha Siddiqui

**AI Engineer building production LLM, RAG, and agentic systems.**

Most LLM prototypes work once, then break in production. The cause is rarely the model. It is
the missing scaffolding around it: retrieval you can measure, guardrails that stop prompt
injection, and eval gates that catch a regression before it ships. I build that layer and gate
CI on the numbers, so quality cannot degrade quietly.

Three years doing this for enterprise RAG and red-teaming in finance and healthcare.

Open to AI and LLM engineering roles: [work.tahasiddiqui@gmail.com](mailto:work.tahasiddiqui@gmail.com)

---

### Featured work

Standalone, runnable repos. Each one runs offline with no API keys, gates its own CI on a
quality metric, and reports numbers you can reproduce by running the code.

| Repo | What it does |
| --- | --- |
| [**soc-triage-agent**](https://github.com/tahasiddiquii/soc-triage-agent) | A full-stack agentic SOC analyst (OpenAI Agents SDK, FastAPI, Next.js) that triages alerts, maps them to MITRE ATT&CK, and proposes containment that never runs without a human approving it. The safety property is proven, not asserted: the eval gate shows zero containment actions executable without approval, at 0.95 verdict accuracy, and it defends against prompt injection in attacker-controlled alert text. |
| [**analytics-copilot**](https://github.com/tahasiddiquii/analytics-copilot) | A text-to-SQL analytics copilot as a graph workflow (Google ADK, FastAPI, Next.js). The point is the deterministic sqlglot validator between the model and the database: every generated query is parsed to an AST and cleared only if it is a single read-only, allow-listed, LIMIT-bounded statement, so a slipped-in DROP or a filesystem read is refused before it runs. It self-corrects on execution errors and declines hard questions rather than guess. Execution accuracy 0.85. |
| [**contract-review-agent**](https://github.com/tahasiddiquii/contract-review-agent) | A durable contract-review workflow (Pydantic AI, FastAPI, Next.js) that classifies clauses, scores deviations against a versioned playbook, drafts redlines, and holds high-risk contracts for human sign-off. The durable execution is the hook: it checkpoints after each stage and resumes after a restart without redoing work, and the eval proves no high-risk contract is auto-approved. Deviation recall 0.90. |
| [**ai-sdr-crew**](https://github.com/tahasiddiquii/ai-sdr-crew) | A CrewAI sales-development crew (researcher, qualifier, writer, reviewer) that qualifies accounts against an ICP and drafts outreach where every claim is grounded in a researched fact. The reviewer rejects any ungrounded claim and nothing is sent without a human, so the eval shows zero fabrication and zero auto-sends. Qualification accuracy 0.94. |
| [**llm-extraction-pipeline**](https://github.com/tahasiddiquii/llm-extraction-pipeline) | Treats LLM extraction as infrastructure: rules parse structured pages and only messy prose reaches a model, which is then validated, cost-capped, deduplicated, and loaded through an Airflow 3 DAG. Per-route metrics justify each routing decision, and 40% of documents never touch a model. Precision 1.00, recall 0.975. |
| [**support-copilot**](https://github.com/tahasiddiquii/support-copilot) | A customer-support agent built as a LangGraph supervisor with specialist handoffs. Refunds pause for human approval and every tool is deterministic, which is what lets the eval gate prove zero unsafe refunds and no injection getting through. Composes the four repos below. |
| [**invoice-ap-agent**](https://github.com/tahasiddiquii/invoice-ap-agent) | Accounts-payable automation where the LLM only extracts and the invoice, PO, and receipt three-way match stays deterministic code. That split is what lets a gate guarantee no bad invoice is ever auto-approved. The point is knowing when not to use the agent. |
| [**deep-research-agent**](https://github.com/tahasiddiquii/deep-research-agent) | A coordinator runs planner, searcher, synthesizer, fact-checker, and writer sub-agents as tools under a fixed step and search budget. Every claim traces back to a cited source, and CI gates on faithfulness and on staying within budget. |
| [**vendor-risk-agent**](https://github.com/tahasiddiquii/vendor-risk-agent) | Reviews a third-party security questionnaire against policy, scores the risk, and drafts a cited memo for human sign-off. A gate ensures no critical gap is ever auto-cleared. |
| [**llm-router**](https://github.com/tahasiddiquii/llm-router) | A gateway that caches semantically similar calls and routes by prompt difficulty, so easy requests skip the frontier model. Measured against an always-frontier baseline, it cuts spend by about 66% and latency by about 57%. |
| [**ai-harness**](https://github.com/tahasiddiquii/ai-harness) | A multi-stage request pipeline: intent, routing, guardrails, retrieval, memory, validation, then the agent. Every stage is traced in Langfuse and scored by LLM-as-judge evals. |
| [**llm-eval-observability**](https://github.com/tahasiddiquii/llm-eval-observability) | A RAG evaluation harness with retrieval metrics, RAGAS-style faithfulness and relevancy, and an LLM judge, each traced and scored per example. It includes an A/B study on retrieval depth behind a CI gate. |
| [**llm-guardrails-redteam**](https://github.com/tahasiddiquii/llm-guardrails-redteam) | Detects and redacts PII and secrets, grades prompt-injection and jailbreak attempts by severity, and applies an allow, redact, or block policy. A scored attack suite gates CI. |
| [**mcp-guardrail-gateway**](https://github.com/tahasiddiquii/mcp-guardrail-gateway) | A security gateway that sits in front of any MCP server, so every tool call clears one checkpoint: role-based access, argument constraints, prompt-injection and secret scanning on both arguments and results, PII redaction, and a tamper-evident audit log. The MCP spec leaves security to the implementor; this is that layer. A red-team suite gates CI at zero unsafe calls allowed, zero PII leaks, and every planted injection neutralized. |
| [**mcp-knowledge-server**](https://github.com/tahasiddiquii/mcp-knowledge-server) | A permission-aware knowledge MCP server that filters every retrieval by the caller identity before the model sees anything, answers only with grounded citations to accessible documents, and refuses across a permission boundary. The gate proves zero permission leaks and zero ungrounded citations, at full recall on the labeled set. |
| [**mcp-sql-guard**](https://github.com/tahasiddiquii/mcp-sql-guard) | A governed read-only text-to-SQL MCP server. Every statement is parsed to an AST and cleared only if it is a single read-only, allow-listed SELECT; a LIMIT is enforced, PII columns are masked unless the caller's role permits, and every decision is audited. The gate proves zero unsafe statements executed and zero PII exposed to a non-privileged role. |
| [**mcp-server-audit**](https://github.com/tahasiddiquii/mcp-server-audit) | An evaluation harness that scores any MCP server on tool-selection accuracy, schema-drift (breaking-change) detection, description quality, and production readiness, and runs as an MCP server that audits other servers. The gate proves it catches every breaking change and tells a well-built server (0.92 routing) from a weak one (0.25). |
| [**hybrid-graph-rag**](https://github.com/tahasiddiquii/hybrid-graph-rag) | Combines BM25, dense retrieval, and RRF fusion with graph multi-hop lookup, benchmarked on a labeled set for recall@k, MRR, and nDCG. Exposed through an MCP connector. |
| [**timeseries-forecasting**](https://github.com/tahasiddiquii/timeseries-forecasting) | Time-series forecasting with sktime, backtested on expanding-window cross-validation using MASE and sMAPE with leakage-safe features. The benchmark shows the complex model losing to the simple one. |
| [**tabular-ml**](https://github.com/tahasiddiquii/tabular-ml) | Tabular classification with leakage-safe scikit-learn pipelines, cross-validated model selection, and probability calibration. It ships an auto-generated model card and gates on a held-out metric. |
| [**timeseries-classification**](https://github.com/tahasiddiquii/timeseries-classification) | Time-series classification with sktime, comparing a majority baseline, KNN-DTW, and a feature-summary model, gated to beat the baseline. The classic distance method wins. |
| [**drift-detection**](https://github.com/tahasiddiquii/drift-detection) | Detects data and prediction drift with PSI and KS statistics written without SciPy, rolled up to one dataset verdict. The gate is asymmetric because missing real drift costs more than a false alarm. |
| [**neural-net-from-scratch**](https://github.com/tahasiddiquii/neural-net-from-scratch) | An MLP in pure numpy with hand-derived backprop and SGD, trained on a spiral dataset. A gradient check matches finite differences to 1e-8, which is the math running under model.fit(). |

> The common thread is simple: measure everything, gate CI on it, and never fabricate a
> number. Every metric in these READMEs comes from code you can rerun.

---

### What I work with

- **LLM and RAG:** retrieval (BM25, dense, hybrid RRF, reranking), RAGAS-style eval, LLM-as-judge, prompt design
- **Agentic:** LangChain, LangGraph, CrewAI, tool-calling, MCP (building servers, a security gateway, and clients)
- **Quality and safety:** evaluation harnesses, guardrails, prompt-injection red-teaming, CI quality gates
- **Observability:** Langfuse tracing, scoring, experiment comparison
- **Classic ML:** time-series forecasting and classification (sktime), scikit-learn, cross-validation, calibration, model cards, feature engineering
- **Data engineering:** LLM extraction pipelines (structured outputs, validation and repair), rule-vs-LLM routing, entity resolution and dedup, Airflow ETL, cost ceilings, model-drift detection
- **MLOps and fundamentals:** LLM cost routing and semantic caching, drift monitoring (PSI, KS), neural nets and backprop from scratch (numpy)
- **Engineering:** Python, pytest, ruff, GitHub Actions, Docker

---

### Connect

- **Website:** [heytaha.com](https://www.heytaha.com/)
- **Email:** [work.tahasiddiqui@gmail.com](mailto:work.tahasiddiqui@gmail.com)
- **LinkedIn:** [linkedin.com/in/connecttaha](https://linkedin.com/in/connecttaha)
