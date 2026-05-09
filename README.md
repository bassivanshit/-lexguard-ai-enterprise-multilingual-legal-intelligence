 ⚖️## **Legal-Linguist: LexGuaed-AI-Enterprise-Mulitilingual-Lega-Intelligence** 🤖

> **Transforming Legal Complexity into Actionable Intelligence.** This system automates the analysis of the **CUAD (Contract Understanding Atticus Dataset)** using a sophisticated multi-agent state machine.

---

## 🏗️ System Architecture & Workflow
The system utilizes a **StateGraph** to manage the lifecycle of a legal query through specialized agents.



### 🧠 Methodology: The Multi-Agent Pipeline
* **Phase 1: The Gatekeeper** 🛡️
    * *Function:* Acts as the primary filter for incoming queries.
    * *Logic:* Performs language detection and semantic filtering to ensure the system only processes relevant legal inquiries, preventing "hallucination drift."
* **Phase 2: The Researcher** 🔍
    * *Function:* Orchestrates context retrieval.
    * *Logic:* Executes hybrid search (Dense Vector + Metadata) against the Qdrant DB and applies a **Cross-Encoder Re-ranker** to improve precision.
* **Phase 3: The Legal Critic** ⚖️
    * *Function:* Quality Assurance loop.
    * *Logic:* Evaluates the retrieved context for "answerability." If the context is insufficient, it triggers a recursive search or provides a structured refusal.

---

## 🛠️ Tools & Technologies
| Category | Stack | Purpose |
| :--- | :--- | :--- |
| **Orchestration** | LangGraph | Complex state management and agentic loops. |
| **Vector Engine** | Qdrant | High-performance semantic indexing and persistent storage. |
| **Embeddings** | BGE-M3 | State-of-the-art multilingual vector representation. |
| **Evaluation** | RAGAS | Quantitative assessment of Faithfulness and Answer Relevancy. |
| **Backend/UI** | FastAPI & Streamlit | Production-grade API endpoints and interactive visualization. |

---

## 🛡️ Industrial-Grade Implementations (Key Highlights)
*Unlike standard RAG demos, this project implements features required for real-world deployment:*

### 1. Data Persistence & Performance
- **Recursive Syntax Splitting:** Optimized chunking that respects legal paragraph structures rather than arbitrary character counts.
- **Persistent Storage:** Transitioned from volatile in-memory storage to a production-ready disk-based database (`qdrant_production_db`).

### 2. Resilience & Disaster Recovery (DR)
- **Snapshotting:** Automated logic to create compressed backups of the vector database.
- **Rotation Logic:** Implemented a 7-day retention policy for snapshots to ensure data durability.
- **Structured Logging:** JSON-based logs specifically for audit trails and system monitoring.

### 3. Security Layer
- **Middleware Integration:** Secured the FastAPI backend with `X-API-KEY` header validation to prevent unauthorized access to the LLM pipeline.

---

## 📈 Business Insights & Impact
- **Risk Mitigation:** Automatically identifies 41+ critical legal categories (e.g., Non-compete, Change of Control) to speed up M&A due diligence.
- **Scalability:** The multi-agent approach allows for asynchronous processing of hundreds of contracts simultaneously.
- **Cost Optimization:** Built-in simulation metrics allow for system testing and logic refinement without incurring continuous LLM API costs during the development lifecycle.

---

## 📂 Repository Structure
- **Done!.ipynb** — The core R&D pipeline from ETL to Multi-Agent logic.
- **app.py** — Streamlit frontend for real-time query visualization.
- **qdrant_production_db/** — Local persistent vector database.
- **qdrant_backups/** — Disaster recovery storage.

---

> **Note:** This project utilizes the Atticus Open Contract Dataset (CUAD) v1 under the Creative Commons Attribution 4.0 International license.
