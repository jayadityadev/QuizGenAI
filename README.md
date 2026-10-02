# QuizGenAI ⚡ 

> **🥈 2nd Prize Winner — Hackathon Project**  
> An AI-powered full-stack dynamic assessment and quiz generation platform built with an API-first backend architecture and structured LLM inference orchestration.

---

## 🏗️ Architecture & Engineering

QuizGenAI was designed under strict **API-contract-first** principles with clear service boundaries to enable high-velocity team development and loose coupling:

```
┌──────────────────┐       ┌──────────────────────┐       ┌──────────────────────┐
│  React Frontend  │ ◄───► │  FastAPI API Layer   │ ◄───► │  LLM Inference Svc   │
│  (UI / State)    │  REST │  (Orchestration / DB)│  JSON │  (RAG / Prompts)     │
└──────────────────┘       └──────────┬───────────┘       └──────────────────────┘
                                      │
                                      ▼
                           ┌──────────────────────┐
                           │ SQLite / Persistence │
                           │ (Users, Scores, Logs)│
                           └──────────────────────┘
```

### Key Highlights
- **Backend & DB Engineering** *(Jayaditya Dev)*:
  - Designed and implemented the REST API endpoints using **FastAPI** with strict Pydantic validation schemas.
  - Modeled the relational database layer (users, quizzes, historical attempts, leaderboard scoring).
  - Managed the full request/response lifecycle, error handling middleware, and interactive OpenAPI (Swagger) documentation.
- **LLM Service Pipeline**:
  - Dynamic question generation from user prompts, topic constraints, and difficulty parameters with strict JSON schema outputs.
  - Real-time response evaluation and scoring heuristics.
- **Client Application**:
  - Interactive quiz runner with dynamic question progression, countdown timers, and post-quiz analytics.

---

## 🛠️ Tech Stack

- **Backend**: Python 3.10+, FastAPI, Pydantic, Uvicorn
- **Database**: SQLite (SQLAlchemy / direct access layer)
- **AI / LLM**: Prompt engineering, JSON-mode structured output, OpenAI / Local LLM endpoints
- **Frontend**: React, JavaScript, TailwindCSS
- **Specification**: OpenAPI (Swagger), Contract-first schemas

---

## 🚀 Getting Started

### 1. Backend Setup
```bash
cd backend
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```
Interactive API documentation will be available at `http://localhost:8000/docs`.

### 2. Frontend Setup
```bash
cd frontend
npm install
npm run dev
```

---

## 👥 Authors & Collaborators

- **Jayaditya Dev** — Backend & Database Engineering, System Orchestration
- **Jaggu** — LLM Service & AI Pipeline
- **Arun Chavan & Aniket** — Frontend Engineering & UI Components
