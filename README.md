# Career OPS

A job-market data platform I built for my own job search. Every night it collects open software jobs from employers' own hiring systems, ranks them against my resume, and drafts a tailored one-page resume for the best matches.

**Live page:** https://kaihuan-huang.github.io/career-ops-demo/

This page shows public job data only (counts, sources, recent public postings, what job descriptions ask for), refreshed every night. The full dashboard is private: it holds my resume and applications.

## What it does

1. **Collect** every company's job board (Greenhouse, Lever, Ashby, Workday, iCIMS, Oracle and more), employers' own systems first.
2. **Store** everything in SQLite and never delete: a posting is closed only after it is missing twice in a row.
3. **Score** each job against the resume with local open models (embeddings + a reranker) plus level and location rules.
4. **Tailor** a one-page resume for the best new matches: one bullet at a time, then plain checks decide what is kept (no invented numbers, no filler, no keyword stuffing).
5. **Brief** each morning: new roles, best matches, drafts, and questions to answer.

## Stack

Python (FastAPI, SQLAlchemy, Alembic), SQLite, Next.js + TypeScript, local open models, Docker Compose. Releases run every test, back up the database and roll back automatically if a check fails.
