# My 10x Solution — Arthur Henrique Lopes Feitosa

**Project**: Task Manager AI & SRE Triager Platform  
**Repository**: https://github.com/arthurhenriquelopes/task-manager-api  
**Track**: Backend AI Engineering  
**Author**: Arthur Henrique Lopes Feitosa (`arthurhenriquelopesf@gmail.com`)  

---

## 1. Problem Statement & Overview
Modern engineering and operations teams face high volumes of incoming customer support tickets, operational alerts, and system issues. Triage is often done manually, leading to delayed response times, miscategorization, and lost revenue.

**The Solution**: An end-to-end, production-grade **AI-Powered Task Management & Autonomous SRE Triage Platform**. The platform combines high-throughput REST APIs, relational persistence, secure authentication, background job queues, PDF report generation, and an autonomous LLM triage engine with self-healing validation loops.

---

## 2. Core Program Concepts Implemented

The platform implements 8 core engineering concepts from the FlyRank Backend AI Engineering program:

### 1. High-Performance REST API
* Built with **FastAPI** in Python 3.11 with automatic OpenAPI / Swagger interactive documentation (`/docs`).
* Implements complete CRUD for tasks with validation via Pydantic models.
* Standardized error handlers and structured JSON responses across all routes.

### 2. Relational Database & Migrations
* Backed by **PostgreSQL 16** with indexed primary keys, unique idempotency constraints, and connection pooling.
* Schemas for tasks (`tasks`), asynchronous LLM jobs (`triage_jobs`), and background report generation (`report_jobs`).

### 3. Authentication & Security
* Integrated with **Supabase Auth** for JWT issuance and verification.
* Role-based token guard with `HTTPBearer` dependency injection protecting private routes (`/protected/profile`).

### 4. Background Job Processing & Orchestration
* Dual async execution model:
  * **FastAPI BackgroundTasks** for decoupled, non-blocking job creation (`202 Accepted`).
  * **Inngest Workflow Engine** (`/api/inngest`) for multi-step DAG flow execution (`ai_flow_execution`).

### 5. Automated PDF Report Generation
* On-demand, background PDF report generator (`/reports/generate`) using **FPDF/ReportLab**.
* Performs SQL aggregations on tasks and triage distribution, generates the PDF artifact into static storage, and exposes download URLs (`/static/reports/`).

### 6. LLM Autonomous Triage & Self-Repair Loops
* LLM SRE Triager Agent classifying input text into strict taxonomy (`billing`, `bug`, `feature`, `other`) and urgency (`low`, `normal`, `high`).
* Strict Pydantic JSON schema enforcement with **automatic repair prompt loop** on malformed responses.
* Quarantine logging (`logs/quarantine.jsonl`) and token/cost telemetry (`logs/cost.jsonl`).

### 7. Web Scraper Pipeline
* Dedicated polite web scraping subsystem (`scraper/`) with rate limiting, error recovery, and structured dataset exports.

### 8. Interactive Frontend Canvas
* **React Flow + TailwindCSS + Vite** visual canvas (`frontend/`) allowing drag-and-drop workflow execution connecting prompt nodes directly to backend execution pipelines.

---

## 3. Architecture & Data Flow

```
[ Frontend / React Flow / HTTP Client ]
                  │
                  ▼
         [ FastAPI Gateway ]
         ├── Auth Guard (Supabase JWT)
         ├── Task CRUD Controller ──────► [ PostgreSQL Database ]
         ├── Background Job Controller ──► [ Inngest / BackgroundTasks ]
         │                                       │
         │                                       ▼
         ├── PDF Report Engine ◄─────────────────┘
         │        └── Generates static PDF artifacts
         │
         └── LLM Triage Engine
                  ├── Structured Pydantic Parser
                  ├── 1-Shot Self-Repair Loop
                  └── OpenRouter / Gemini API Provider
```

---

## 4. Verification & Testing

* **API Health & Endpoints**: Fully tested on Docker Compose environment.
* **Eval Suite**: Ground-truth benchmark test cases in `evals/cases.json`.
* **Deployment**: Dockerized with multi-stage `Dockerfile` and `docker-compose.yml`.

---
*Submitted as the Capstone Project for the FlyRank Backend AI Engineering Track.*
