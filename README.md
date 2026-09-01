# Project | Capstone | Round 1 | README
### John Adams

**Client:** Chleo Hair Studio, an independent premium hair salon in Prenzlauer Berg, Berlin
**Sector:** Hair & beauty services (Germany) · **Company size:** Micro business (2 owner-operators, 2 independent chair renters, 0 employees)

## Overview

Round 1 AI consulting pitch package: sector research, a BI dashboard, an automation POC with monitoring, cost and timeline estimates, and a presentation deck. Proposes three use cases (booking assistant, no-show recovery, retention and re-engagement), with a working POC and live monitoring built for the retention and re-engagement use case.

## Repo structure

```
research/            Sector research, opportunities/risks, use case proposals, source documents
dashboard/            5 CSVs, Tableau workbook, screenshot, documentation
n8n/                  Automation POC (workflow export, documentation)
langsmith/            LangSmith monitoring sample (notebook)
cost_estimation/      Cost analysis and timeline estimate
presentation/         Slide deck
feedback/             round1_decision.md (added after presenting to teaching staff)
data/                 Reserved for raw data, currently empty
```

## How to view each deliverable

- **Dashboard:** open `dashboard/dashboard.twbx` in Tableau Public. A screenshot is at `dashboard/dashboard.png`, full write-up in `dashboard/dashboard_documentation.md`.
- **Automation POC:** import `n8n/workflow.json` into n8n. What it does, why it fits the use case, and its limits vs. production are documented in `n8n/workflow_documentation.md`.
- **LangSmith monitoring sample:** open `langsmith/langsmith_monitoring_sample.ipynb`. Requires the dependencies below and a `.env` file with real API keys.
- **Presentation:** open `presentation/pitch-deck-slideshow.html` in any browser. Arrow keys or click to navigate. A static `presentation/presentation.pdf` is included as a backup if the interactive version can't be shown.
- **Research:** `research/sector_research.md`, `research/opportunities_risks.md`, `research/use_cases.md`.
- **Cost and timeline:** `cost_estimation/cost_analysis.md`, `cost_estimation/timeline_estimate.md`.

## Setup

```bash
pip install -r requirements.txt
cp .env.example .env
```

Fill in `.env` with a real `OPENAI_API_KEY` and `LANGSMITH_API_KEY` before running the LangSmith notebook. Never commit `.env`, it's excluded via `.gitignore`.

## Decision

See `feedback/round1_decision.md` for the keep/change call after presenting to teaching staff.
