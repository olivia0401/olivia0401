# Olivia (Mengxiao Xu)

AI Engineer building production LLM agents, evaluation systems, and safety-focused ML services.

I work on the gap between "the demo works" and "the system is safe to ship": agent runtimes, structured outputs, RAG, tool calling, evaluation, failure analysis, observability, security controls, and CI/CD.

[LinkedIn](https://www.linkedin.com/in/mengxiao-xu/) | [Email](mailto:oliviaxu0401@gmail.com) | UK - open to relocating to Belfast

## What I build

- **Production AI agents:** LangGraph, MCP, RAG, tool calling, OCR, verifier agents, and escalation-only safety controls
- **Evaluation and reliability:** golden datasets, rubric design, LLM-as-judge calibration, paired significance testing, confidence intervals, provenance, and regression gates
- **Applied ML services:** imbalanced classification, ranking, off-policy evaluation, forecasting, APIs, Docker, and CI/CD

## Featured projects

| Project | What it demonstrates |
|---|---|
| [Parent Check](https://parentcheck.duckdns.org) | Bilingual scam-safety agent for older adults. Deterministic rules set a risk floor; the LLM analyst and verifier can escalate risk but never lower it. Includes MCP, RAG, OCR, SSRF protection, OpenTelemetry, Prometheus, Terraform, and AWS. The repository is private; the live demo is available above. |
| Prompt Evaluation Framework | Private production-style evaluation build covering 23 client briefs, 6 models, approximately 142 prompt configurations, 12,298 model calls, 8 quality metrics, a 61-item golden dataset, multi-tenant API/worker/database/dashboard services, and CI gates backed by 256 pytest tests and 87 Playwright tests. |
| [LLM-to-Action Planning for Robotic Battery Disassembly](https://github.com/olivia0401/battery-disassembly-llm-planning) | LLM-to-ROS 2/MoveIt planning for a Kinova Gen3 robot, with RAG, safety validation, live execution probes, Wilson confidence intervals, McNemar/Holm correction, and reproducible failure analysis. |
| [AI Job Scout](https://github.com/olivia0401/AI-Job-Scout) | UK Skilled Worker sponsor job radar that ingests live ATS and aggregator roles, filters sponsor-eligible employers, and scores roles against a user's CV. Supports local use and Docker Compose multi-user deployment. |
| [Sequential Recommendation](https://github.com/olivia0401/sequential-recommender) | GRU4Rec and SASRec compared with popularity and Markov baselines on MovieLens-1M and RetailRocket, with ranking metrics plus SNIPS off-policy evaluation for the business question: would deployment actually lift conversion? |
| [UK Road Casualty Severity Analysis](https://github.com/olivia0401/traffic-risk-prediction) | SQL data engineering over UK Department for Transport records, time-series forecasting with ARIMA/SARIMA/Prophet/LSTM, and an explicit leakage audit separating retrospective analysis from deployable pre-incident prediction. |
| [Stroke Prediction ML Service](https://github.com/olivia0401/stroke-prediction-ml) | Leak-free imbalanced classification with XGBoost, SMOTEENN, cross-validated threshold tuning, FastAPI, Gradio, Docker, and GitHub Actions. Honest cross-validated AUC-ROC is 0.79, with F1 0.22 and recall 0.29. |

## I re-check my own headline numbers

| Project | First reported | After audit | What changed |
|---|---:|---:|---|
| [battery-disassembly-llm-planning](https://github.com/olivia0401/battery-disassembly-llm-planning) | safety recall 12.4% | **2.5%** | the earlier metric mixed safety labels with overall plan correctness and credited the validator for rejecting safe-but-non-canonical plans; the corrected view is 2 of 80 unsafe commands detected |
| [sequential-recommender](https://github.com/olivia0401/sequential-recommender) | SASRec Recall@10 0.994 | **0.804** | a left-padding mask produced `NaN` at the final position; `NaN` compared false against every negative and made the ranker look perfect |
| [traffic-risk-prediction](https://github.com/olivia0401/traffic-risk-prediction) | macro-F1 0.76 | **0.35** | features only known after a crash leaked into a framing that sounded like pre-incident prediction |
| [stroke-prediction-ml](https://github.com/olivia0401/stroke-prediction-ml) | F1 0.59 | **0.22** | the decision threshold was tuned on the same data used for scoring instead of inside cross-validation |

Four different causes, one habit: an evaluation system that never revises downward usually just is not looking.

## How I work

- Validate the data and decision rule before interpreting model performance
- Measure the noise floor and compare against strong baselines
- Separate format validity, semantic correctness, and real execution
- Keep raw data, provenance, assumptions, and correction logs visible
- Fail builds on regressions, malformed outputs, missing provenance, or too-small samples

## Toolbox

- **AI:** Python, LangGraph, MCP, RAG, tool calling, Anthropic/OpenAI SDKs, OCR, structured outputs
- **Evaluation:** golden datasets, LLM-as-judge, groundedness, error analysis, Wilcoxon/McNemar, confidence intervals, Cohen's kappa
- **Engineering:** FastAPI, Flask, pytest, Playwright, TypeScript/Node, GitHub Actions, OpenTelemetry, Prometheus
- **Cloud and data:** PostgreSQL/pgvector, Redis, Docker, Terraform, AWS, SQL
- **ML and robotics:** PyTorch, XGBoost, scikit-learn, ROS 2, MoveIt 2

UK | [LinkedIn](https://www.linkedin.com/in/mengxiao-xu/) | [Email](mailto:oliviaxu0401@gmail.com)
