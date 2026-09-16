# Hi, I'm Aaron Christian 👋

**AI Engineer & Generative AI Researcher | LangGraph · RAG · LLM Evaluation · Multi-Agent Systems · Python · SQL · BI**

I make AI prove itself before the business depends on it. 🚀

---

## 🧩 Expertise

[![](https://skillicons.dev/icons?i=python,fastapi,react,vite,postgres,mongodb)](https://skillicons.dev)

**LangGraph · RAG · GraphRAG · LLM Evaluation · Multi-Agent Systems · Text-to-SQL · Python · SQL · Pinecone · Neo4j · Snowflake · dbt · Power BI · Tableau**

---

## 🌐 Connect With Me

[![](https://skillicons.dev/icons?i=linkedin)](https://www.linkedin.com/in/aaronchristi7n)
[![](https://skillicons.dev/icons?i=github)](https://github.com/AaronFChristian)

📄 [Live Demo - ClariRAG](https://clarirag-ui.vercel.app) &nbsp;|&nbsp; 📄 [Live Demo — MetricMind](https://metric-mind-liart.vercel.app)

---

## ⚡ What I Build

- **Agentic RAG pipelines** with hybrid retrieval, citation validation, and sufficiency guardrails - systems that say "I don't know" instead of hallucinating
- **Governed text-to-SQL agents** scoped to certified dbt metrics, so the LLM cannot invent numbers that don't exist in the semantic layer
- **GraphRAG systems** combining Neo4j knowledge graphs with vector retrieval for multi-hop relationship reasoning flat vector search can't do
- **Multi-agent evaluation systems** that audit AI output before it reaches a human, with schema-validated contracts between agents
- **LLM observability stacks** scoring faithfulness, cost, latency, and hallucination rates with LangSmith, Langfuse, Ragas, and Grafana

---

## 🧠 Tech Stack

[![](https://skillicons.dev/icons?i=python,fastapi,react,vite,postgres,mongodb)](https://skillicons.dev)
[![](https://skillicons.dev/icons?i=git,github,linux,docker)](https://skillicons.dev)

**AI/ML:** LangGraph · LangChain · Anthropic Claude · RAG · GraphRAG · Pinecone · BM25 · Ragas · DeepEval · LangSmith · Langfuse · Cross-Encoder Reranking  
**Graph & Data:** Neo4j · Cypher · pgvector · DuckDB · Snowflake · dbt · Azure AI Search · ETL · Pandas · NumPy  
**BI:** Power BI · Tableau · Looker Studio · DAX  
**Infra:** FastAPI · FastMCP · Streamlit · Redis · Prometheus · Grafana · Docker · GitHub Actions · Vercel · Railway · Fly.io  

---

## 🚀 Featured Projects

### 📊 MetricMind - Governed Text-to-SQL Analytics Copilot
> The LLM cannot invent a metric that doesn't exist — every answer traces back to a certified dbt model

Business teams wait 3–7 days for analysts to answer questions like *"what is 30-day retention for the EU cohort, adjusted for refunds?"* The deeper problem is metric drift: "active user" means something different across five dashboards. MetricMind solves both.

- **5-node LangGraph pipeline**: Intent Classifier → 3-layer Guardrail → SQL Generator → DuckDB Executor → Response Node, with automatic self-correction on broken SQL
- **3-layer guardrail**: PII regex + SQL injection regex + metric allowlist via Claude Haiku — bad queries rejected for $0.0003 vs $0.006 for full pipeline (20x cheaper)
- **Governed semantic layer**: 6 certified metrics in a JSON catalog; the agent is physically scoped to only those — no hallucinated numbers, no schema drift
- **dbt Core**: 4 staging models + 4 mart models (DAU, cohort retention, revenue, funnel) with **40 dbt tests** catching 150+ dirty rows before any reach a prompt
- **100% eval accuracy** on 50-question golden set scored via sqlglot AST comparison · prompt caching on the 3,000-token metric catalog (90% cache hit rate, ~$0.006/query avg)
- **Dual anomaly detection**: 3-sigma rolling window + Prophet, with HITL commentary approval before publishing
- **Full LLMOps stack**: LangSmith traces every node · Prometheus scrapes FastAPI every 15s · Grafana dashboard (latency, cost, guardrail rejections) · Tableau Public dashboards
- React + Vite frontend · FastAPI backend on Railway · Vercel deploy · Docker Compose local stack

🔗 [Repo](https://github.com/AaronFChristian/MetricMind) · [Live Demo](https://metric-mind-liart.vercel.app)

---

### 🛡️ Attestor - Model-Risk Governance for GenAI & Agentic Systems
> An AI validation finding has to prove itself against real evidence, or it never gets written

Under the SR 26-2 model-risk regime, every GenAI and agentic system a bank runs needs conceptual soundness review, outcomes analysis, and ongoing monitoring. Most tools for this are LLM-as-judge systems, and a judge that hallucinates *"faithfulness collapsed to 0.42"* is dangerous precisely because it sounds credible. Attestor blocks ungrounded findings at write time.

- **LangGraph validation pipeline**: Supervisor (materiality-tier routing) → 3 parallel pillar nodes (Conceptual Soundness · Outcomes Analysis · Ongoing Monitoring) → adversarial Challenge node → Attribution Gate
- **Deterministic attribution gate**: every finding's evidence is resolved against Postgres and its cited metric checked against the stored eval run before persisting. A database lookup, not a second LLM call. `Finding.evidence_id` is `NOT NULL`
- **Dual-judge scoring**: Claude and Llama 3.1 (Groq) score each rubric criterion independently; disagreement beyond threshold escalates to mandatory human review
- **Real HITL interrupt/resume**: LangGraph `interrupt_before` on a Postgres checkpointer, so paused runs survive API restarts and are visible across replicas
- **Segregation of duties enforced server-side**: Keycloak OIDC + RBAC; validators can't validate models they own, and sign-off is MRM-Head-only
- SHA-256 hash-chained audit log · prompt-injection screening · deterministic materiality scorecard · rejected findings feed a self-governance golden set
- Integration tests prove negative controls are rejected: fabricated evidence, cross-model citations, misreported metrics
- Next.js 16 + React 19 · FastAPI · Qdrant · ARQ/Redis · isolated FastMCP server · Logfire + LangSmith · CI with bandit, gitleaks, dependency audit, and a blocking eval-regression gate

🔗 [Repo](https://github.com/AaronFChristian/attestor)

---

### 💰 LedgerLens - Multimodal Invoice Intelligence + GraphRAG
> Reads an invoice image → extracts clean structured data → answers multi-hop supplier questions that vector search can't

Finance teams manually key 50,000+ invoices/month at ~$3.50/invoice. Pure vector RAG can't answer *"which suppliers tied to delayed Q3 POs also had quality complaints in the past 18 months?"* — because it has no concept of graph structure. LedgerLens solves both halves.

- **Claude vision extraction** with per-field confidence scoring (0.0–1.0) and automatic human-review routing for low-confidence documents — no OCR pre-processing required
- **Neo4j knowledge graph** maps `Supplier → Invoice → LineItem → PO` for relationship reasoning across entities
- **LangGraph GraphRAG agent**: plan → retrieve → traverse → answer, returning the full Cypher traversal path as an auditable explanation
- **84.2% field extraction accuracy** · **99.7% cost reduction** vs $3.50/invoice manual baseline (~$0.008/invoice with Claude Sonnet)
- DeepEval/RAGAS eval harness · Langfuse span-level tracing + per-document token cost · FastAPI + React UI · Docker + Fly.io deploy

🔗 [Repo](https://github.com/AaronFChristian/LedgerLens)

---

### 🎬 Overture - Discovery Call to Grounded Demo
> Sales transcript in, cited and grounded live demo out, in minutes instead of days

Solution Engineers spend 5–25 hours a week hand-building demos in a prospect's language. Overture reads the discovery-call transcript, extracts what the prospect needs with every claim traced to an exact quote, and stands up a live Q&A demo that refuses to answer what the source can't support.

- **LangGraph extraction pipeline**: 4 parallel passes (pains · constraints · requirements · vocabulary) → scope classification → blueprint selection → config fill → validate → persist → embed → share token
- **Quote-grounded extraction**: every item must carry an exact transcript quote; anything the model can't ground is dropped
- **Deterministic where it matters**: blueprint picked by a keyword scorer, and the deploy validator has zero LLM imports, proven by a test that greps its own source
- **Grounded RAG Q&A** over pgvector with expandable citations; verified live refusing a prompt-override attempt to "just figure it out"
- **Azure via Terraform**: Container Apps · Postgres Flexible Server + pgvector · Key Vault via Managed Identity (zero stored secrets) · Application Insights
- Single container serves React SPA + FastAPI (no CORS surface in prod) · SSE streams live pipeline progress · swappable Claude / Azure OpenAI provider
- **75+ tests** · ruff + mypy strict · 50-entry `decisions.md` of real bugs, e.g. a flaky token-tamper test traced to base64 trailing-byte redundancy (6.6%, measured over 10,000 runs)

🔗 [Repo](https://github.com/AaronFChristian/overture)

---

### 🕸️ CaseWeave - Agentic AML Investigation Copilot
> Every sentence in the SAR narrative is provably grounded in evidence, or refused outright

Transaction monitoring alerts run 90–95% false positives, and a Suspicious Activity Report is a legal filing with FinCEN. A hallucinated sentence isn't a UX bug, it's a false statement to the government. CaseWeave is built around that constraint.

- **9-node LangGraph supervisor**: triage (Claude Haiku 4.5) → evidence gathering → narrative (Claude Sonnet 5) → per-sentence guardrail gate
- **Frozen EvidenceLedger**: every fact gets an ID before drafting, and the narrative model sees only the ledger, never raw rows
- **Sentence-level attribution validator** with independent judge entailment; below 90% coverage it refuses and returns an evidence-gap report. Caught a real hallucinated regulatory citation in live testing
- **Graph-only detection**: Neo4j Cypher catches circular fund flows invisible to SQL. Planted-subject recall **91% → 100%**
- **L0–L4 autonomy ladder** per rule; L4 auto-close only with golden-set evidence re-verified at runtime. Same alert: **13 LLM calls / $0.03** at L2 vs **0 / $0.00** at L0
- Redpanda streaming with DLQ · River online anomaly scoring · hybrid pgvector retrieval · DuckDB long-term memory of prior dispositions
- LangSmith + Logfire tracing down to individual guardrail sentence decisions · 5-tool read-only FastMCP server
- **69 tests** · CI with ruff, mypy strict, bandit, pip-audit, golden-set gate, and a reproducibility gate · React + Vite + Cytoscape.js review console · synthetic data only

🔗 [Repo](https://github.com/AaronFChristian/caseweave)

---

## 🎯 Currently Focused On

- Building production-grade **agentic AI evaluation frameworks**
- Deepening expertise in **LLM observability** (LangSmith, Langfuse, Ragas, DeepEval, Grafana)
- Expanding into **GraphRAG, multimodal AI, and governed analytics** for enterprise use cases
- Targeting **AI Engineer / AI Analyst** roles at the intersection of AI systems and analytics

---

## 🎓 Education

- 🎓 MS Information Systems — San Diego State University *(GPA: 3.7)*
- 🎓 B.Tech Computer Science & Business Systems — DY Patil College of Engineering *(GPA: 3.8)*

---

## 💡 The Way I Think About AI

Most people ask *"does the AI return an answer?"*  
I ask *"is the answer faithful, grounded, and verifiable — and what happens when it isn't?"*

---

⭐ If my work is useful, feel free to explore the repos!
