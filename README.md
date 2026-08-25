## Olivia (Mengxiao Xu)

AI/ML engineer. I build LLM agents and applied ML — and the evaluation that
decides whether they are good enough to ship.

### I re-check my own headline numbers

| Project | First reported | After re-analysis | What was actually wrong |
|---|---|---|---|
| [battery-disassembly-llm-planning](https://github.com/olivia0401/battery-disassembly-llm-planning) | safety recall 12.4% | **2.5%** | one field merged "unsafe command" with "non-canonical plan", so 11 of 13 catches were false alarms on legitimate commands |
| [sequential-recommender](https://github.com/olivia0401/sequential-recommender) | SASRec Recall@10 0.994 | **0.804** | a masking bug produced `nan`, and `nan` compares false against every negative — so the ranker scored a perfect rank 1 |
| [traffic-risk-prediction](https://github.com/olivia0401/traffic-risk-prediction) | macro-F1 0.76 | **0.35** | features that only exist after the crash |
| [stroke-prediction-ml](https://github.com/olivia0401/stroke-prediction-ml) | F1 0.59 | **0.22** | the decision threshold was tuned on the same data it was scored on |

Four different causes, one habit. An evaluation system that never revises
downward usually just is not looking.

### How I work

- Measure the noise before setting any threshold
- Fix the decision rule before seeing the data
- Include a control condition, so a metric cannot pass on the task alone
- Fail a build on too small a sample rather than pass it
- Write down what I could not measure, instead of letting it go quietly missing

### Live

[parentcheck.duckdns.org](https://parentcheck.duckdns.org) — a bilingual scam-safety
agent for older adults: rule engine sets a risk floor, the LLM layer can escalate it
but never lower it, and a 61-case golden set blocks the deploy in CI if accuracy or
scam recall regresses.

UK · [LinkedIn](https://www.linkedin.com/in/mengxiao-xu/)
