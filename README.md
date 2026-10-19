# LeadForge

## Automated B2B Lead Generation, Enrichment, Outreach & CRM Pipeline

### Project Team

- **Project Lead:** Hikmatyar
- **Team Member:** Muhannad Ayaz Khan
- **Team Member:** Daniyal Hikmat

## Overview

LeadForge transforms raw business search queries into cleaned, enriched, scored and managed B2B leads. It combines discovery, website crawling, contact extraction, website auditing, AI-assisted analysis/personalization, outreach campaigns, inbox synchronization and CRM management.

## Core Workflow

```text
Search Query / CSV
        ↓
Google Maps Discovery
        ↓
Data Cleaning & Deduplication
        ↓
Website Crawling
        ↓
Contact + Social Extraction
        ↓
Website Audit + AI Analysis
        ↓
Lead Scoring (0–100)
        ↓
Hot / Warm / Cold
        ↓
Outreach Campaigns
        ↓
IMAP Reply Sync
        ↓
CRM Pipeline → Tasks → Revenue
```

## Main Features

- Google Maps lead discovery
- CSV/Excel query ingestion
- Lead cleaning and deduplication
- Website crawling and HTML archiving
- Email and phone extraction
- Owner/decision-maker detection
- Social profile discovery
- Automated website audits
- AI website analysis
- AI personalized outreach
- Deterministic lead scoring
- Hot/Warm/Cold classification
- Multi-sender SMTP campaigns
- Follow-up sequences
- IMAP inbox synchronization
- CRM Kanban pipeline
- Tasks and activity tracking
- Revenue tracking
- CSV/Excel/Google Sheets export

## Technology Stack

### Backend
- FastAPI
- SQLAlchemy 2.0
- Celery
- SQLite (WAL mode)
- Redis
- Playwright
- Pandas
- OpenAI

### Frontend
- Next.js 16 App Router
- React 18
- TypeScript
- Tailwind CSS
- TanStack Query
- DnD Kit
- Recharts

### Quality / Deployment
- pytest
- pytest-cov
- GitHub Actions
- Docker / Docker Compose

## Repository Structure

```text
leadforge/
├── .env.example
├── .gitignore
├── Dockerfile
├── docker-compose.yml
├── README.md
├── requirements.txt
├── run.py
├── run_worker.py
├── backend/
├── leadforge-ui/
├── tests/
├── docs/
│   └── LeadForge_Assignment_1_Requirements_v2.pdf
├── plans/
└── data/
```

## Assignment Documentation

The submission requirements document is:

`docs/LeadForge_Assignment_1_Requirements_v2.pdf`

## Local Development

### Backend

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

```bash
pip install -r requirements.txt
python -m playwright install chromium
```

Create `.env` from `.env.example`.

Start Redis:

```bash
docker compose up -d redis
```

Start the worker:

```bash
python run_worker.py
```

Start the API:

```bash
uvicorn backend.main:app --reload --port 8000
```

### Frontend

```bash
cd leadforge-ui
npm install
npm run dev
```

Frontend: `http://localhost:3000`

Backend: `http://localhost:8000`

### Docker

```bash
docker compose up --build -d
```

Stop:

```bash
docker compose down
```

## Testing

```bash
pytest -v
```

Coverage:

```bash
pytest --cov=backend --cov-report=term-missing --cov-fail-under=80
```

The documented project includes GitHub Actions CI for pushes and pull requests to `main`.

## Git Contribution Rules

Every team member must use their own GitHub account and make meaningful contributions.

Example:

```bash
git add .
git commit -m "Add lead scoring improvements"
git push origin main
```

Do not create artificial commits.

## Versioning

Initial development tag:

```bash
git tag -a v0.1.0 -m "Initial project version"
git push origin v0.1.0
```

Use Git history and tags for versions instead of creating duplicate project copies.

## Assignment 1 Submission

Submit:

1. Public GitHub repository link.
2. Requirements document PDF.
3. The same requirements PDF committed inside the repository.

One group member may submit on behalf of the group, but all members are responsible for contributing to and understanding the repository.
