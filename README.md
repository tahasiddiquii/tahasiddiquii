# Hi, I'm Taha 👋

**AI Engineer — production LLM/RAG & agentic systems, evaluation, guardrails, and observability.**

I build the *engineering scaffolding* around LLMs that makes them shippable: multi-stage
agent harnesses, retrieval that's actually measured, guardrails + red-teaming, and the
tracing/eval gates that keep quality from regressing in CI. ~3 years building production
AI for enterprise (RAG + red-teaming in finance & healthcare).

🔭 **Open to AI / LLM engineering roles.** Email me: [work.tahasiddiqui@gmail.com](mailto:work.tahasiddiqui@gmail.com)

---

### 🚀 Featured work — harness engineering & AI observability

These are standalone, runnable repos. Each one runs **fully offline with zero API keys**,
has a **green CI quality gate**, and reports **real, reproducible numbers** (never hand-waved).

| Repo | What it demonstrates |
| --- | --- |
| [**support-copilot**](https://github.com/tahasiddiquii/support-copilot) 🆕 | **Agentic workflow capstone** — a customer-support agent: LangGraph supervisor + specialist handoffs, deterministic tools, **human-in-the-loop refunds**, guardrails, and an embedded eval gate (zero unsafe refunds, every injection blocked). Composes the four repos below. |
| [**invoice-ap-agent**](https://github.com/tahasiddiquii/invoice-ap-agent) 🆕 | **Agentic finance** — accounts-payable automation: LLM extraction + deterministic 3-way match (invoice/PO/receipt) + human-in-the-loop, with a safety gate that no bad invoice is ever auto-approved. "An agent that knows when *not* to be an agent." |
| [**ai-harness**](https://github.com/tahasiddiquii/ai-harness) | Multi-stage agent harness: intent → routing → guardrails → retrieval → memory → validation → agent, with tools, LLM-as-judge evals, and Langfuse tracing. |
| [**llm-eval-observability**](https://github.com/tahasiddiquii/llm-eval-observability) | RAG evaluation harness — retrieval metrics + RAGAS-style faithfulness/relevancy + LLM-judge, per-example Langfuse traces & scores, and an A/B retrieval-depth study behind a CI gate. |
| [**llm-guardrails-redteam**](https://github.com/tahasiddiquii/llm-guardrails-redteam) | Guardrails + red-team harness: PII/secret detection & redaction, severity-graded prompt-injection/jailbreak rules, allow/redact/block policy, and a scored attack suite gating CI. |
| [**hybrid-graph-rag**](https://github.com/tahasiddiquii/hybrid-graph-rag) | Hybrid (BM25 + dense + RRF) and graph multi-hop retrieval with a labeled benchmark (recall@k · MRR · nDCG) and an MCP connector. |
| [**timeseries-forecasting**](https://github.com/tahasiddiquii/timeseries-forecasting) 🆕 | **Classic ML** — time-series forecasting (sktime) backtested with expanding-window temporal CV (MASE/sMAPE), leakage-safe feature engineering, and a benchmark gate. Includes the honest finding that the fancy model loses. |
| [**tabular-ml**](https://github.com/tahasiddiquii/tabular-ml) 🆕 | **Classic ML** — tabular classification done right: leakage-safe sklearn pipelines, cross-validated model selection, calibration, an auto-generated model card, and a held-out metric gate. |

> Common thread: **measure everything, gate on it, never fabricate the metric.** Every
> number in these READMEs is produced by code you can re-run.

---

### 🛠️ What I work with

**LLM/RAG:** retrieval (BM25, dense, hybrid/RRF, reranking), RAGAS-style eval, LLM-as-judge, prompt design
**Agentic:** LangChain · LangGraph · CrewAI · tool-calling · MCP
**Quality & safety:** evaluation harnesses, guardrails, prompt-injection red-teaming, CI quality gates
**Observability:** Langfuse tracing, scoring, experiment comparison
**Classic ML:** time-series forecasting (sktime), scikit-learn, cross-validation, calibration, model cards, feature engineering
**Engineering:** Python · pytest · ruff · GitHub Actions · Docker

---

### 📫 Connect

- **Email:** [work.tahasiddiqui@gmail.com](mailto:work.tahasiddiqui@gmail.com)
- **LinkedIn:** [linkedin.com/in/connecttaha](https://linkedin.com/in/connecttaha)

> AI is the new electricity — and I'm a restless learner driven by curiosity to build at the edge of it.
