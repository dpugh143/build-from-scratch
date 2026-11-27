# build-from-scratch

**Build From Scratch: a DevOps engineer learns to ship code.**

A six-week program (Nov 30, 2026 to Jan 10, 2027) to get fast at 4-level timed coding
assessments in Python, and to live the developer workflow from an empty folder to a deployed
service. The projects build toward a small deployment orchestrator, made with mock data so
everything here is safe to publish.

## Progress

Each week is a [milestone](https://github.com/dpugh143/build-from-scratch/milestones), and each
piece of work is an [issue](https://github.com/dpugh143/build-from-scratch/issues) with a
"done when" checklist.

| Week | Dates | Focus | Post |
|---|---|---|---|
| 0 | Nov 19 – 29 | Head start: reading `bisect.py` and `heapq.py` | |
| 1 | Nov 30 – Dec 6 | Setup and the key-value store | Dec 6 |
| 2 | Dec 7 – 13 | Layered config loader (`orch-config`) and the first timed baseline | Dec 13 |
| 3 | Dec 14 – 20 | Deployment planner: heapq, bisect, topological sort | Dec 20 |
| 4 | Dec 21 – 27 | Ticket batcher and work plan (`orch-plan`) | Dec 27 |
| 5 | Dec 28 – Jan 3 | Concurrency: threads, asyncio, a crawler | Jan 3 |
| 6 | Jan 4 – 10 | Capstone `mini-orch`, container, Kubernetes, mock interviews | Jan 10 |

## The rules

- **Build without AI, review with it.** I write every line of Python myself, then ask Claude to
  review it. Claude handles the README, issues and CI workflows so the time goes into the code.
- **Tests first, or at least alongside.** Every level of every problem gets a test before it's done.
- **Commit small and often.** One commit per level or feature, through a pull request with green CI.
- **Log the clock.** Every timed attempt is logged: levels passed, minutes per level, where the time went.

## Layout

One folder per project, sharing one CI workflow.

| Folder | What it is | Week |
|---|---|---|
| `kv_store/` | Key-value store, problem-bank #1 | 1 |
| `orch_config/` | Layered YAML config loader with a Typer CLI | 2 |
| `deploy_planner/` | Jobs, dependencies, parallel batches and failure handling | 3 |
| `orch_plan/` | Mock Jira export to `work-plan.json` | 4 |
| `env_health/` | Health checks: serial, threaded, async | 5 |
| `mini_orch/` | Capstone CLI with a FastAPI status endpoint | 6 |

`LESSONS.md` collects one line for every bug that cost more than 30 minutes, plus notes from the
weekly code reading.

## Running it

Once the project is scaffolded (week 1):

```bash
uv sync                 # install dependencies into .venv
uv run pytest           # run all tests
uv run ruff check .     # lint
```

## Decisions

**Repo: personal account, not the Staging-Ground org (Nov 26, 2026).** The plan named a
`staging-ground-builds` repo in the business org. This repo already existed, so the series lives
here to avoid setting up the business identity before week 1. *Alternative:* a new repo in the
Staging-Ground org. *Revisit:* before Post 1 links to it; transferring the repo keeps issues and
history, and GitHub redirects the old URLs.

## Ground rules for the series

Only original practice problems, never the content of a real company's assessment. No employer
code, data or hostnames: the orchestrator projects describe the pattern with mock data.
