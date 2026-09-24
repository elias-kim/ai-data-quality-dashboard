# AI Training Data Quality Dashboard

A data modeling + spreadsheet portfolio project that tracks the quality of AI training data across annotators, tasks, responses, and reviewer scores.

## 🎯 Objective
Model an AI data-labeling pipeline end-to-end — from task assignment to scored output — and surface quality insights by annotator and domain.

## 🧱 Data Model
annotators → assignments → responses → quality_scores
(1-to-many at each stage, linked by foreign keys)

| Table | Key Fields | Purpose |
|---|---|---|
| annotators | annotator_id (PK), name, region, skill_domain, joined_date | Who does the work |
| tasks | task_id (PK), project_name, task_type, difficulty, created_at | What needs labeling |
| assignments | assignment_id (PK), annotator_id (FK), task_id (FK), status, assigned_at, completed_at | Who worked on what |
| responses | response_id (PK), assignment_id (FK), response_text, model_version, submitted_at | The actual output |
| quality_scores | score_id (PK), response_id (FK), accuracy, tone, completeness, reviewer_id, scored_at | How good the output is |

## 📊 Sample Data
See the `/data` folder for CSV exports of each table.

## 🔍 Key Insight
Annotators in **Code eval** average **4.6 accuracy** vs **3.9** for **Prompt writing** — suggesting domain-specific reviewer calibration is needed.

## 🛠 Tools
Google Sheets (formulas, pivot tables), SQL-style schema design, data validation.

## 🚀 Live Dashboard
[View the dashboard](https://YOUR-USERNAME.github.io/ai-data-quality-dashboard/)
