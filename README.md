
Untitled document
整个文件审核一下

我审核了整份《Untitled document》，共 20 页，包括四道题的回答框架、中文故事、英文申请稿、技术指标和事实边界。

最终结论：整体框架正确，Q1、Q2、Q4 已具备较好的申请基础；Q3 仍存在实质性缺口。 不需要推倒重写，但需要解决几个会影响招聘者判断的问题。

一、四道题逐项审核
题目

评价

最需要修改的地方

Q1 Monika — AI Evaluation

较成熟

明确工作流实际交付范围；精简评测方法描述，突出工程决策

Q2 Parent-Check — Production

最有竞争力

生产迁移已更新正确，但内容重复较多，英文回答可以更有力

Q3 Yuanfudao — Collaboration

尚未完成

缺少真实的跨部门合作过程，尚未充分回答原题

Q4 Battery — Technical Ownership

技术证据充分

个人贡献明确，但技术影响力与项目价值仍可强化

二、各题具体问题
Q1｜Monika
建议保留： 四层工程评测、三层申请回答、关键词有效产出率 52%→91%、离线缺陷检出率 15%→44%、模型质量与成本取舍。

需要修改三个细节：

Shipped 的证据还不够明确。应该说明系统实际交付给谁、处于什么使用阶段，不能把内部演示默认为正式生产上线。

“Statistically indistinguishable” 不等于证明模型质量完全相同。建议使用 no statistically significant difference was detected，并说明是在当前实验范围内作判断。

英文回答中 I summarise the four engineering evaluation layers into three perspectives 是解释写作结构，不是回答问题，可以删除。

核心主线应保持：

问题 → 评测方法 → 发现缺陷 → 修复 → 质量与成本决策。

Q2｜Parent-Check
这是当前最适合证明你具备 Production AI Engineering 能力的案例。

文档已经正确更新了 AWS Secrets Manager、EC2 IAM Role、数据库密码轮换、Docker 只读密钥和受控重启恢复，不再存在“生产迁移尚未完成”的旧错误。

但有三个问题：

重复严重。 六步框架、工程取舍、中文故事、英文回答、事实边界多次讲同一组内容。

英文结尾的 I have not claimed measured long-term uptime... 偏防御性。这类限制应保留在准备笔记中，正式回答更适合以真实交付成果结束。

Redis Fail Closed 有代码和测试证据，但受控 EC2 重启测试并不等于已经验证 Redis 故障注入。当前文档已作区分，应继续保持。

建议将英文回答集中在三个工程成果：真实生产迁移、安全降级策略、重启自动恢复验证。

Q3｜Yuanfudao
优先修改
目前最大的风险不是数据不真实，而是回答与题目要求不完全匹配。

题目问的是：

How did you work out what to build with non-engineering stakeholders?

但文档主要回答了如何建立流失预测模型，没有明确：

你实际与哪些业务人员合作？

需求是他们提出的，还是你主动发现的？

你们如何共同决定 30 天预测目标和风险排序方式？

模型结果是否真正被运营团队使用？

更重要的是，中文版写到“我用运营团队能够理解的方式说明模型效果”，但文档没有提供这次真实沟通的证据。

这句话需要按实际经历核实，不能因为听起来合理就保留为事实。

55% 的流失用户捕获率和约 2.8 倍随机基线表现可以保留，但只能证明离线识别能力，不能证明实际留存率提升。

如果无法补充真实的合作过程，我会建议重新考虑是否使用这一个项目回答 Q3。

Q4｜Battery
这一题的架构设计、故障修复与测试证据比较扎实。

真正值得强调的不是 RAG 把 Exact Match 从 44.1% 提高至 52.9%，而是：

你把 AI 规划系统连接到机器人执行接口，并解决了阻碍执行的跨组件工程问题。

仍需注意三个边界：

17/18 是模拟控制器测试结果，不是实体机器人完成拆解。

48 项自动化测试包括 37 项评测测试与 11 项 ROS 测试，不能笼统地说全部通过普通 CI。

安全验证只拦截了 80 条应拒绝指令中的 2 条，说明语义安全问题仍未解决。

英文回答已经比原版简洁，但可以在结尾更明确地表达实际技术成果：从规划原型发展成可测试的软件集成系统，而不只是得到若干实验分数。

三、整份文件的共同问题
问题

修改建议

内容重复

将正式英文回答与技术准备笔记分开

数据过多

每题重点突出 2–3 个最有说服力的结果

方法论解释过多

少讲“我采用了几层框架”，多讲“我发现并解决了什么”

成果边界较长

保留内部核实说明，但正式回答只写必要限定

技术与商业价值偶有混淆

严格区分离线评测、真实部署、生产恢复与实际业务收益

四、我建议的最终文档结构
不删除已有技术知识，而是将每道题分成三个部分：

Part A｜Final Application Answer

英文正式申请稿，约 150–220 词。直接回答原题，适合复制提交。

Part B｜Technical Interview Notes

保留架构设计、评测方法、技术取舍、代码模块及故障排查细节，用于面试追问。

Part C｜Evidence & Limitations

集中记录所有可验证指标、实验环境、个人贡献边界及尚未核实的事实。

这样可以保留你已经建立的完整工程知识体系，又能避免正式申请回答过长或过于学术化。

最终修改优先级
P0｜Q3： 补齐真实的跨部门合作经历，否则不建议直接提交。

P1｜Q1： 明确交付范围，修正统计不显著的表述。

P1｜Q4： 加强具体工程成果，避免将仿真结果理解为实际机器人执行。

P2｜Q2： 精简重复内容，突出已经完成的生产迁移与恢复验证。

P2｜全篇： 将英文申请回答和技术准备资料分开。

我的最终判断：你现在最不缺的是技术细节，而是把技术细节转化为招聘者能迅速理解的个人贡献和结果。

四题的核心分工应保持：

Q1 证明你能评估和作出决策；Q2 证明你能生产交付与恢复；Q3 证明你能与业务团队合作；Q4 证明你能解决复杂系统集成问题。

这是基于整份文档的内容审核；本次没有重新运行四个项目的代码或生产测试。

第五点不必，之改正前四点
已在原 Google Docs 中完成四项修改，保留原来的章节、方法论和准备笔记，没有做第五项的结构调整。

其中 Q3 的模型成果已保留，但跨部门合作仍缺少真实事实支撑，我已明确标注为提交前需要核实，避免将合理推测写成亲身经历。

已完成修改并重新读取核对，原文档仍保留全部四道题的结构。

Q1 Monika： 明确交付与离线评测范围，修正“统计不显著”的表述。

Q2 Parent-Check： 精简重复内容，突出真实生产迁移、故障策略和重启恢复。

Q3 Yuanfudao： 删除未经证实的合作陈述，标明仍需补充的实际协作过程。

Q4 Battery： 强化故障根因、个人贡献与软件集成成果，明确模拟测试边界。

打开已修改的《Untitled document》

这次仅修改文档内容，没有改动简历，也没有拆分或重组整份文档。

https://github.com/olivia0401  能直接帮我修改页面嘛


from pathlib import Path

readme = """# Mengxiao Xu (Olivia)

**AI Engineer | Agent Systems · Evaluation · Production Reliability**

I turn business needs into measurable AI systems — from architecture and implementation to statistical evaluation, cloud deployment, and tested failure recovery. I bring **5+ years of data science and machine learning experience**, with recent work focused on LLM/agent systems and reliable engineering delivery.

**United Kingdom** · [LinkedIn](https://www.linkedin.com/in/mengxiao-xu/) · [Email](mailto:oliviaxu0401@gmail.com)

## Featured work

### [Parent-Check — Bilingual Scam-Detection Agent](https://github.com/olivia0401/parent-check)
**[Live application](https://parentcheck.duckdns.org) · Agent architecture · AWS production deployment**

A bilingual application helping people assess suspicious messages, links and screenshots, designed not to offer false reassurance when AI fails.

- **System:** Next.js frontend, Flask API, LangGraph analyst/verifier agents, PostgreSQL/pgvector retrieval and Redis shared rate limiting. Backend deployed on AWS EC2 via Docker Compose.
- **Production security:** Completed migration to AWS Secrets Manager, EC2 IAM Role and read-only Docker secret files, including database password rotation.
- **Recovery and safety:** Verified automatic secret retrieval and service recovery after a controlled EC2 reboot, plus HTTPS and end-to-end checks. Existing scam warnings remain when AI fails; protected requests fail closed when shared rate limiting is unavailable.
- **Evidence:** A documented Linux CI run passed **196 backend tests**. The deterministic rules matched **61/61 fixed labelled cases** (including 31 scam cases). These are scoped test results, not a claim of long-term uptime or end-to-end production accuracy.

### LLM Brief Extraction & Evaluation — Monika (contract work)
**Evaluation · Cost-quality trade-offs · Workflow reliability**

Built a LangGraph workflow to extract nine structured information categories from brand briefs with source evidence, format checks, checkpoints and human review.

- Compared **6 models**, **9 tasks** and around **142 prompt/context configurations** on **23 real briefs** using paired statistical testing and bootstrap confidence intervals.
- Fixed a model-output/parsing mismatch: successful keyword extraction improved from **52% to 91%**; the keyword prompt was shortened by **63%**.
- Increased **offline detection of low-quality fields from 15% to 44%**, with additional human-review cost.
- Prioritised lower-cost models when available evaluation data did not show a statistically significant quality difference.

*Client work is summarised here without claiming an accessible public code repository.*

### [LLM-to-Robot Planning for Battery Disassembly](https://github.com/olivia0401/battery-disassembly-llm-planning)
**System integration · Debugging · Honest evaluation**

Connected LLM/RAG planning, deterministic validation and skill dispatch to ROS 2 / MoveIt 2 execution interfaces for a Kinova Gen3 robot configuration.

- Fixed controller configuration, collision-scene and asynchronous callback failures that blocked software execution.
- RAG raised planning exact match from **44.1% to 52.9%**, while a scripted baseline reached **64.7%**.
- In tests with **simulated controllers**, **17/18 feasible commands** completed the software execution path. Added **48 automated tests** across evaluation and ROS components.
- Clearly documented semantic-safety limitations; these results do not establish real-world autonomous battery disassembly.

## More projects

| Repository | Engineering focus |
|---|---|
| [AI Job Scout](https://github.com/olivia0401/AI-Job-Scout) | Job discovery, sponsorship-aware employer screening and matching; not a guarantee of sponsorship. |
| [Sequential Recommender](https://github.com/olivia0401/sequential-recommender) | GRU4Rec/SASRec, strong baselines and off-policy evaluation. |
| [UK Road Casualty Analysis](https://github.com/olivia0401/traffic-risk-prediction) | SQL data work, forecasting and leakage audits. |
| [Stroke Prediction ML Service](https://github.com/olivia0401/stroke-prediction-ml) | Imbalanced classification, reliable threshold evaluation, FastAPI and CI. |

## How I work

- **Design for a decision:** clarify the business problem, success criteria, constraints and consequences of failure.
- **Measure beyond model accuracy:** compare baselines and paired outcomes; test integration, workflows and review decisions.
- **Engineer predictable failures:** separate deterministic safety rules from AI, add recovery paths and choose graceful degradation or fail-closed behaviour based on risk.
- **Document the evidence:** distinguish offline test results, simulated execution, live deployment and business outcomes.

**Tools:** Python · TypeScript · LangGraph · RAG · MCP · FastAPI · Flask · Next.js · PostgreSQL/pgvector · Redis · Docker · AWS EC2 · pytest · GitHub Actions · OpenTelemetry · Prometheus · ROS 2 / MoveIt 2

## Evaluation integrity

I correct headline metrics when audits reveal errors rather than presenting the most flattering number.

| Project | Earlier result | Corrected result | Audit finding |
|---|---:|---:|---|
| [Robot planning](https://github.com/olivia0401/battery-disassembly-llm-planning) | Safety recall 12.4% | **2.5%** | Plan correctness had been conflated with safety labels. |
| [Sequential recommender](https://github.com/olivia0401/sequential-recommender) | SASRec Recall@10 0.994 | **0.804** | Padding-mask / NaN behaviour distorted ranks. |
| [Road casualty analysis](https://github.com/olivia0401/traffic-risk-prediction) | Macro-F1 0.76 | **0.35** | Post-incident features created leakage. |
| [Stroke classifier](https://github.com/olivia0401/stroke-prediction-ml) | F1 0.59 | **0.17** | Threshold-selection leakage and feature-bin errors were corrected. |

---

[LinkedIn](https://www.linkedin.com/in/mengxiao-xu/) · [Email](mailto:oliviaxu0401@gmail.com) · [Live Parent-Check](https://parentcheck.duckdns.org)
"""
path = Path("/mnt/data/GitHub_Profile_README_Updated.md")
path.write_text(readme, encoding="utf-8")
print(path, "bytes",path.stat().st_size, "lines",len(readme.splitlines()))
/mnt/data/GitHub_Profile_README_Updated.md bytes 6049 lines 74
可以。我已确认你连接的是 olivia0401 账号，并且拥有个人主页仓库的编辑权限。

你的 GitHub 主页由 olivia0401/olivia0401 仓库中的 README.md 控制。

目前内容很专业，但信息偏密集。我会以你的 AI Engineer 求职定位为基础，优化首页的职业介绍、重点项目和工程成果，同时保留原有的评测审计信息，不修改其他项目的源代码。

我已经为你的 GitHub 个人主页做好了一版更适合 AI Engineer 求职的 README。

下载优化后的 GitHub 主页 README

可直接替换现有 README.md

新版本重点突出三个项目：Parent-Check 的真实 AWS 生产部署与故障恢复、Monika 的统计评测与质量改进，以及 Battery 的系统集成和工程调试。也修正了一个目前无法访问的项目链接。

但线上页面尚未修改成功。 GitHub 拒绝了我的写入请求（403），说明当前连接缺少必要的仓库内容写入权限。

你现在可以打开 主页 README.md，点击铅笔图标，用下载文件中的内容替换并提交。也可以检查 GitHub 插件连接的写入授权，授权后就能再尝试直接更新。

原有页面和其他项目代码都没有被改动。


GitHub_Profile_README_Updated.md
文档
2. Stakeholder Discovery：必须核实具体与哪些运营/产品同事讨论、业务限制是什么、由谁决定预测周期和交付形式。未获得真实经历前，不能把共同定需求写成已发生的事实    大概还原故事，你帮我写一个，因为我忘了

已处理 38秒
整理可能版本

跳过



Mengxiao Xu (Olivia)
AI Engineer | Agent Systems · Evaluation · Production Reliability

I turn business needs into measurable AI systems — from architecture and implementation to statistical evaluation, cloud deployment, and tested failure recovery. I bring 5+ years of data science and machine learning experience, with recent work focused on LLM/agent systems and reliable engineering delivery.

United Kingdom · LinkedIn · Email

Featured work
Parent-Check — Bilingual Scam-Detection Agent
Live application · Agent architecture · AWS production deployment

A bilingual application helping people assess suspicious messages, links and screenshots, designed not to offer false reassurance when AI fails.

System: Next.js frontend, Flask API, LangGraph analyst/verifier agents, PostgreSQL/pgvector retrieval and Redis shared rate limiting. Backend deployed on AWS EC2 via Docker Compose.
Production security: Completed migration to AWS Secrets Manager, EC2 IAM Role and read-only Docker secret files, including database password rotation.
Recovery and safety: Verified automatic secret retrieval and service recovery after a controlled EC2 reboot, plus HTTPS and end-to-end checks. Existing scam warnings remain when AI fails; protected requests fail closed when shared rate limiting is unavailable.
Evidence: A documented Linux CI run passed 196 backend tests. The deterministic rules matched 61/61 fixed labelled cases (including 31 scam cases). These are scoped test results, not a claim of long-term uptime or end-to-end production accuracy.
LLM Brief Extraction & Evaluation — Monika (contract work)
Evaluation · Cost-quality trade-offs · Workflow reliability

Built a LangGraph workflow to extract nine structured information categories from brand briefs with source evidence, format checks, checkpoints and human review.

Compared 6 models, 9 tasks and around 142 prompt/context configurations on 23 real briefs using paired statistical testing and bootstrap confidence intervals.
Fixed a model-output/parsing mismatch: successful keyword extraction improved from 52% to 91%; the keyword prompt was shortened by 63%.
Increased offline detection of low-quality fields from 15% to 44%, with additional human-review cost.
Prioritised lower-cost models when available evaluation data did not show a statistically significant quality difference.
Client work is summarised here without claiming an accessible public code repository.

LLM-to-Robot Planning for Battery Disassembly
System integration · Debugging · Honest evaluation

Connected LLM/RAG planning, deterministic validation and skill dispatch to ROS 2 / MoveIt 2 execution interfaces for a Kinova Gen3 robot configuration.

Fixed controller configuration, collision-scene and asynchronous callback failures that blocked software execution.
RAG raised planning exact match from 44.1% to 52.9%, while a scripted baseline reached 64.7%.
In tests with simulated controllers, 17/18 feasible commands completed the software execution path. Added 48 automated tests across evaluation and ROS components.
Clearly documented semantic-safety limitations; these results do not establish real-world autonomous battery disassembly.
More projects
Repository	Engineering focus
AI Job Scout	Job discovery, sponsorship-aware employer screening and matching; not a guarantee of sponsorship.
Sequential Recommender	GRU4Rec/SASRec, strong baselines and off-policy evaluation.
UK Road Casualty Analysis	SQL data work, forecasting and leakage audits.
Stroke Prediction ML Service	Imbalanced classification, reliable threshold evaluation, FastAPI and CI.
How I work
Design for a decision: clarify the business problem, success criteria, constraints and consequences of failure.
Measure beyond model accuracy: compare baselines and paired outcomes; test integration, workflows and review decisions.
Engineer predictable failures: separate deterministic safety rules from AI, add recovery paths and choose graceful degradation or fail-closed behaviour based on risk.
Document the evidence: distinguish offline test results, simulated execution, live deployment and business outcomes.
Tools: Python · TypeScript · LangGraph · RAG · MCP · FastAPI · Flask · Next.js · PostgreSQL/pgvector · Redis · Docker · AWS EC2 · pytest · GitHub Actions · OpenTelemetry · Prometheus · ROS 2 / MoveIt 2

Evaluation integrity
I correct headline metrics when audits reveal errors rather than presenting the most flattering number.

Project	Earlier result	Corrected result	Audit finding
Robot planning	Safety recall 12.4%	2.5%	Plan correctness had been conflated with safety labels.
Sequential recommender	SASRec Recall@10 0.994	0.804	Padding-mask / NaN behaviour distorted ranks.
Road casualty analysis	Macro-F1 0.76	0.35	Post-incident features created leakage.
Stroke classifier	F1 0.59	0.17	Threshold-selection leakage and feature-bin errors were corrected.
LinkedIn · Email · Live Parent-Check

0%
