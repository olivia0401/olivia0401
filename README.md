Mengxiao Xu (Olivia)
AI Engineer | Agent Systems · Evaluation · Production Reliability

I turn business needs into measurable AI systems — from architecture and implementation to statistical evaluation, cloud deployment, and tested failure recovery. I bring 5+ years of data science and machine learning experience, with recent work focused on LLM/agent systems and reliable engineering delivery.

United Kingdom · LinkedIn · Email
Featured work
Parent-Check — Bilingual Scam-Detection Agent
Live application · Agent architecture · AWS production deployment

A bilingual application helping people assess suspicious messages, links and screenshots, designed not to offer false reassurance when AI fails.
- System: Next.js frontend, Flask API, LangGraph analyst/verifier agents, PostgreSQL/pgvector retrieval and Redis shared rate limiting. Backend deployed on AWS EC2 via Docker Compose.
- Production security: Completed migration to AWS Secrets Manager, EC2 IAM Role and read-only Docker secret files, including database password rotation.
- Recovery and safety: Verified automatic secret retrieval and service recovery after a controlled EC2 reboot, plus HTTPS and end-to-end checks. Existing scam warnings remain when AI fails; protected requests fail closed when shared rate limiting is unavailable.
- Evidence: A documented Linux CI run passed 196 backend tests. The deterministic rules matched 61/61 fixed labelled cases (including 31 scam cases). These are scoped test results, not a claim of long-term uptime or end-to-end production accuracy.
LLM Brief Extraction & Evaluation — Monika (contract work)
Evaluation · Cost-quality trade-offs · Workflow reliability

Built a LangGraph workflow to extract nine structured information categories from brand briefs with source evidence, format checks, checkpoints and human review.
- Compared 6 models, 9 tasks and around 142 prompt/context configurations on 23 real briefs using paired statistical testing and bootstrap confidence intervals.
- Fixed a model-output/parsing mismatch: successful keyword extraction improved from 52% to 91%; the keyword prompt was shortened by 63%.
- Increased offline detection of low-quality fields from 15% to 44%, with additional human-review cost.
- Prioritised lower-cost models when available evaluation data did not show a statistically significant quality difference.
Client work is summarised here without claiming an accessible public code repository.
LLM-to-Robot Planning for Battery Disassembly
System integration · Debugging · Honest evaluation

Connected LLM/RAG planning, deterministic validation and skill dispatch to ROS 2 / MoveIt 2 execution interfaces for a Kinova Gen3 robot configuration.
- Fixed controller configuration, collision-scene and asynchronous callback failures that blocked software execution.
- RAG raised planning exact match from 44.1% to 52.9%, while a scripted baseline reached 64.7%.
- In tests with simulated controllers, 17/18 feasible commands completed the software execution path. Added 48 automated tests across evaluation and ROS components.
- Clearly documented semantic-safety limitations; these results do not establish real-world autonomous battery disassembly.
More projects
Repository	Engineering focus
AI Job Scout	Job discovery, sponsorship-aware employer screening and matching; not a guarantee of sponsorship.
Sequential Recommender	GRU4Rec/SASRec, strong baselines and off-policy evaluation.
UK Road Casualty Analysis	SQL data work, forecasting and leakage audits.
Stroke Prediction ML Service	Imbalanced classification, reliable threshold evaluation, FastAPI and CI.


How I work
- Design for a decision: clarify the business problem, success criteria, constraints and consequences of failure.
- Measure beyond model accuracy: compare baselines and paired outcomes; test integration, workflows and review decisions.
- Engineer predictable failures: separate deterministic safety rules from AI, add recovery paths and choose graceful degradation or fail-closed behaviour based on risk.
- Document the evidence: distinguish offline test results, simulated execution, live deployment and business outcomes.
Tools: Python · TypeScript · LangGraph · RAG · MCP · FastAPI · Flask · Next.js · PostgreSQL/pgvector · Redis · Docker · AWS EC2 · pytest · GitHub Actions · OpenTelemetry · Prometheus · ROS 2 / MoveIt 2
Evaluation integrity
I correct headline metrics when audits reveal errors rather than presenting the most flattering number.
Project	Earlier result	Corrected result	Audit finding
Robot planning	Safety recall 12.4%	2.5%	Plan correctness had been conflated with safety labels.
Sequential recommender	SASRec Recall@10 0.994	0.804	Padding-mask / NaN behaviour distorted ranks.
Road casualty analysis	Macro-F1 0.76	0.35	Post-incident features created leakage.
Stroke classifier	F1 0.59	0.17	Threshold-selection leakage and feature-bin errors were corrected.


LinkedIn · Email · Live Parent-Check
