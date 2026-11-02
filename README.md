# Mengxiao Xu (Olivia)

**AI Engineer | LLM & Agent Systems | Evaluation & Reliability**

I design, evaluate and deploy AI systems — from business requirements and architecture to production safeguards and tested recovery. I bring **5+ years of data science and machine learning experience**, with a focus on making LLM and agent workflows reliable, measurable and useful.

**Based in the UK** · [LinkedIn](https://www.linkedin.com/in/mengxiao-xu/) · [Email](mailto:oliviaxu0401@gmail.com)

## Featured Projects

### 1. [Parent-Check — Bilingual Scam-Detection Agent](https://github.com/olivia0401/parent-check)
[**Live app**](https://parentcheck.duckdns.org) · Production AI · Security & recovery

A bilingual scam-risk checker for suspicious messages, links and screenshots.

- **Architecture:** Next.js frontend, Flask API, LangGraph analyst/verifier agents, PostgreSQL/pgvector RAG and Redis shared rate limiting; backend deployed on **AWS EC2**.
- **Production delivery:** Migrated credentials to **AWS Secrets Manager** with an EC2 IAM role and read-only Docker secret files, rotated the database password, and verified automatic secret retrieval and service recovery after a controlled EC2 reboot.
- **Failure boundaries:** Existing risk warnings survive LLM failures; protected requests fail closed when shared rate limiting is unavailable.
- **Evidence:** **196 backend tests** passed in a documented Linux CI run. Deterministic rules matched **61/61 fixed labelled cases**, including 31 scam examples — not a claim of end-to-end production accuracy.

### 2. LLM Brief Extraction & Evaluation — Monika (contract work)
*Applied evaluation · Agent workflows · Cost/quality trade-offs*

Designed a LangGraph workflow for extracting nine information categories from client brand briefs, with evidence checks, checkpoints and human review.

- Compared **6 models**, **9 tasks** and approximately **142 configurations** on **23 real briefs**, using paired statistical tests and bootstrap confidence intervals.
- Fixed an output/parser mismatch, improving successful keyword extraction **52% → 91%**; shortened the keyword prompt **63%**.
- Improved **offline** detection of low-quality fields **15% → 44%**, with increased human-review requirements; favoured lower-cost models where tests did not detect a meaningful quality difference.

*Client work summarised without linking to a public source repository.*

### 3. [LLM-to-Robot Planning for Battery Disassembly](https://github.com/olivia0401/battery-disassembly-llm-planning)
*System integration · ROS 2/MoveIt 2 · Debugging*

Connected LLM/RAG planning and deterministic skill validation to robotics software execution interfaces.

- Fixed controller configuration, collision-scene handling and asynchronous callback errors that blocked execution.
- RAG improved **planning exact match 44.1% → 52.9%**; a scripted baseline still performed better at **64.7%**.
- **17/18 feasible commands** completed the software execution path with **simulated controllers**. Added **48 automated tests** across evaluation and ROS components. This was not physical robot validation.

## Other Projects

| Project | Focus |
|---|---|
| [AI Job Scout](https://github.com/olivia0401/AI-Job-Scout) | Job discovery, sponsorship-aware screening and matching |
| [Sequential Recommender](https://github.com/olivia0401/sequential-recommender) | GRU4Rec, SASRec, baselines and off-policy evaluation |
| [UK Road Casualty Analysis](https://github.com/olivia0401/traffic-risk-prediction) | SQL, forecasting and data-leakage auditing |
| [Stroke Prediction ML Service](https://github.com/olivia0401/stroke-prediction-ml) | Imbalanced ML, FastAPI, Docker and CI |

## Engineering Approach

**Define the decision → Design the system → Evaluate against baselines → Test failure modes → Deploy and verify.**

I distinguish **offline metrics**, **simulated execution** and **real production evidence**. When an audit changes a headline result, I publish the correction rather than keep the more flattering number.

**Tools:** Python · TypeScript · LangGraph · RAG · MCP · FastAPI · Flask · Next.js · PostgreSQL/pgvector · Redis · Docker · AWS EC2 · pytest · GitHub Actions · OpenTelemetry · Prometheus · ROS 2/MoveIt 2
