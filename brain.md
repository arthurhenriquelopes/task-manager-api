# FlyRank Internship & AI Builder Knowledge Base (`brain.md`)

## 📌 Executive Status Summary

* **Participant**: Arthur Henrique Lopes Feitosa (`arthurhenriquelopesf@gmail.com`)
* **GitHub Repository**: [`https://github.com/arthurhenriquelopes/task-manager-api`](https://github.com/arthurhenriquelopes/task-manager-api)
* **Active Tracks**:
  * **Backend AI Engineering**: 9/9 track assignments submitted (100%), Capstone submitted and **In Review**.
  * **General AI Fluency**: 14/26 assignments submitted (14/5 requirement met), Capstone submitted and **In Review**.
* **Bosnia Challenge 2026**:
  * **Status**: **ELIGIBLE & QUALIFIED** (Entries Unlocked for the Draw: 740 points ready for final pool).
  * **Requirements Met**: 5/5 evidence-backed track assignments + Same-track Capstone submitted + Rules accepted.

---

## 🗺️ Portal Architecture & Route Map

| Route / Path | Purpose & Functionality |
|---|---|
| `/intern` | Main dashboard displaying current week (Week 3), submitted assignments (24+), and next recommended actions. |
| `/intern/assignments` | All 42 program assignments broken down by week (1 to 8+) and by track. |
| `/intern/assignments?mode=capstones` | Capstone project options across Backend AI, AI Fluency, Frontend AI, and ML tracks. |
| `/intern/completion` | Credential wallet tracking certificate qualification, progress reports, and final evaluation documents. |
| `/intern/bosnia-challenge` | Bosnia Challenge qualification tracker, draw entry balances (740 entries), rules acceptance, and community tasks. |
| `/intern/submissions` | Complete audit log of all submitted artifacts, links, and mentor review feedback. |
| `/intern/announcements` | Real-time cohort notices and critical updates (e.g. deadline reminders, video drops). |
| `/intern/documents` | Generation of official completion certificate PDFs, verification letters, and builder ladder assessments. |

---

## 🏗️ Capstone Implementation Details (`task-manager-api`)

The Backend AI Engineering Capstone **"My 10x Solution"** implements 8 core production concepts:

1. **FastAPI CRUD Engine**: Full REST lifecycle with Pydantic validation, structured HTTP exceptions, and OpenAPI/Swagger documentation.
2. **PostgreSQL Relational Storage**: Schema with connection pooling, indexes, idempotency keys, and tables for tasks, triage jobs, and report jobs.
3. **Supabase Auth & JWT Security**: Bearer token authentication guard (`HTTPBearer`) protecting private endpoints.
4. **Background Job Orchestration**: Asynchronous execution via FastAPI `BackgroundTasks` and **Inngest** event-driven DAG workflows (`/api/inngest`).
5. **PDF Report Generator**: Background worker querying aggregated metrics and rendering downloadable PDF reports into static storage.
6. **Autonomous LLM SRE Triager Agent**: Pydantic structured output classification, 1-shot self-repair loops, and token/cost telemetry.
7. **Polite Web Scraper**: Subsystem with rate limiting, retry handlers, and structured JSON output.
8. **Interactive Visual UI**: React Flow + TailwindCSS + Vite visual canvas connecting prompt nodes directly to backend execution pipelines.

---

## 🛡️ Best Practices & Conventions

* **Submissions**: Submit repository URLs via accordion details forms (`textarea[name='deliverable_urls']`), accompanied by contextual notes and PDF reports.
* **Integrity**: Keep reference pipelines read-only, ensure temporal split integrity (no leakage), and maintain honest evaluation metrics.
