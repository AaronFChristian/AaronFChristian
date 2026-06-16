# Hi, I'm Aaron Christian 👋

**AI Engineer & Generative AI Researcher | LangGraph · RAG · LLM Evaluation · Multi-Agent Systems · Python · SQL · BI**

I don't just use AI — I build systems that make it reliable, evaluated, and production-ready. 🚀

---

## 🧩 Expertise

[![](https://skillicons.dev/icons?i=python,fastapi,react,vite,postgres,mongodb)](https://skillicons.dev)

**LangGraph · RAG · GraphRAG · LLM Evaluation · Multi-Agent Systems · Python · SQL · Pinecone · Neo4j · Snowflake · Power BI · Tableau**

---

## 🌐 Connect With Me

[![](https://skillicons.dev/icons?i=linkedin)](https://www.linkedin.com/in/aaronchristi7n)
[![](https://skillicons.dev/icons?i=github)](https://github.com/AaronFChristian)

📄 [Live Demo — ClariRAG](https://clarirag-ui.vercel.app)

---

## ⚡ What I Build

- **Agentic RAG pipelines** with hybrid retrieval, citation validation, and sufficiency guardrails — systems that say "I don't know" instead of hallucinating
- **GraphRAG systems** combining Neo4j knowledge graphs with vector retrieval for multi-hop relationship reasoning that flat vector search can't do
- **Multi-agent evaluation systems** that audit AI output before it reaches a human, with schema-validated contracts between agents
- **LLM benchmarking frameworks** scoring faithfulness, relevancy, and hallucination rates with Ragas, DeepEval, and LangSmith
- **BI dashboards & ETL pipelines** that turn raw data into executive-ready insights

---

## 🧠 Tech Stack

[![](https://skillicons.dev/icons?i=python,fastapi,react,vite,postgres,mongodb)](https://skillicons.dev)
[![](https://skillicons.dev/icons?i=git,github,linux,docker)](https://skillicons.dev)

**AI/ML:** LangGraph · LangChain · Anthropic Claude · RAG · GraphRAG · Pinecone · BM25 · Ragas · DeepEval · LangSmith · Langfuse · Cross-Encoder Reranking  
**Graph:** Neo4j · Cypher · pgvector · Azure AI Search  
**Data:** SQL · Snowflake · dbt · ETL · Pandas · NumPy  
**BI:** Power BI · Tableau · Looker Studio · DAX  
**Infra:** FastAPI · FastMCP · Streamlit · Docker · GitHub Actions · Vercel · Fly.io  

---

## 🚀 Featured Projects

### 🏥 ClariRAG — Production-Grade Agentic RAG System
> Clinical knowledge retrieval that shows its work, and knows when to stay quiet

Every claim is tied to a page number. Every citation is validated before it reaches the user. If the answer isn't in the corpus, the system says so — instead of guessing.

- **5-node LangGraph pipeline**: Analyser → Expander → Hybrid Retriever → Sufficiency Judge → Generator, with a conditional retry edge when context falls short
- **Hybrid retrieval**: BM25 (exact clinical terminology) + Pinecone dense vectors, fused with RRF and reranked by a cross-encoder on the top 20 candidates
- Retrieval hit rate improved from **58% → 81%**; hallucinated citations reduced to **zero** via hard guardrail validation
- Ragas faithfulness **0.86** · LangSmith node-level tracing · FastMCP server (usable from Claude Desktop) · React + Vite frontend on Vercel
- Corpus: 5 WHO clinical guideline PDFs · 299 pages · 1,911 chunks

🔗 [Repo](https://github.com/AaronFChristian/ClariRAG) · [Live Demo](https://clarirag-ui.vercel.app)

---

### 💰 LedgerLens — Multimodal Invoice Intelligence + GraphRAG
> Reads an invoice image → extracts clean structured data → answers multi-hop supplier questions that vector search can't

Finance teams manually key 50,000+ invoices/month at ~$3.50/invoice. Pure vector RAG can't answer questions like *"which suppliers tied to delayed Q3 POs also had quality complaints in the past 18 months?"* — because it has no concept of graph structure. LedgerLens solves both halves.

- **Claude vision extraction** with per-field confidence scoring (0.0–1.0) and automatic human-review routing for low-confidence documents — no OCR pre-processing required
- **Neo4j knowledge graph** maps `Supplier → Invoice → LineItem → PO` for relationship reasoning across entities
- **LangGraph GraphRAG agent**: plan → retrieve → traverse → answer, returning the full Cypher traversal path as an auditable explanation
- **84.2% field extraction accuracy** · **99.7% cost reduction** vs $3.50/invoice manual baseline (~$0.008/invoice with Claude)
- DeepEval/RAGAS eval harness · Langfuse span-level tracing · FastAPI + React UI · Docker + Fly.io deploy

🔗 [Repo](https://github.com/AaronFChristian/LedgerLens)

---

### 🏭 FabIQ — Azure-Ready Multi-Agent RAG for Engineering Knowledge
> Role-aware technical documentation intelligence with LLM-as-judge evaluation and a full CI/CD eval gate

Engineers at semiconductor manufacturers spend 2–3 hours per shift searching thousands of pages of machine manuals, fab process specs, and compliance guidelines. A wrong answer can stop a production line.

- **5-agent LangGraph pipeline**: Query Understanding → Privilege Check → Hybrid Retrieval → Citation Grounding → LLM-as-Judge Evaluation
- **Role-based access control (RBAC)** enforced server-side at the retrieval layer — not just at the API — so engineers only retrieve documents their role permits
- **Dual LLM architecture**: Azure OpenAI GPT-4o for generation, Anthropic Claude as a separate judge model for evaluation — keeping generation and scoring independent
- **HITL gate**: if confidence < 0.60, routes to human review instead of shipping a weak answer
- **65 passing tests** across chunker, loader, search, agent, and pipeline layers · 30-question golden eval dataset (3 tiers: factual, procedural, multi-hop) · CI-gated eval regression on every push
- Prompt versioning via JSON config registry · 3 chunking strategies with ADR documentation · Full operational runbook

🔗 [Repo](https://github.com/AaronFChristian/FabIQ)

---

### 🔍 SearchIQ — Executive Search Intelligence Platform
> Multi-agent pipeline that turns a plain-English hiring brief into an evaluated, export-ready candidate slate

Most AI pipelines stop at "the model returned valid JSON." SearchIQ treats that as the easy 10% of the problem.

- **4-agent pipeline**: Market Mapper → Profile Generator → Critic Agent → Exporter
- Critic agent scores every profile against **5 structured criteria** (title match, accountability ownership, credential specificity, brief-specific fit, domain translation risk) before any slate ships
- Schema-validated JSON contracts between agents; failed validation triggers a corrective retry with the error fed back into the prompt
- Multi-provider: Claude Sonnet / Haiku, GPT-4o, Gemini — swappable via a single config file
- Versioned prompts with v1 limitations documented inline, so the iteration reasoning is visible, not just the final result
- Streamlit UI · Google Sheets export with CSV fallback

🔗 [Repo](https://github.com/AaronFChristian/SearchIQ)

---

## 🎯 Currently Focused On

- Building production-grade **agentic AI evaluation frameworks**
- Deepening expertise in **LLM observability** (LangSmith, Langfuse, Ragas, DeepEval)
- Expanding into **GraphRAG and multimodal AI** for enterprise document intelligence
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
