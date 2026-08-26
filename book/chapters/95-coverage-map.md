# Coverage Map

**Summary:** *Every objective on the published blueprint, and the chapter that owns it. Use
this to find the chapter behind a weakness rather than reading in order. The domain weights
are the blueprint's own, and they are worth looking at before deciding where to spend an
evening.*

## Domain 1: Solution Design & Architecture (17% of the exam)

| Objective | Owned by |
|---|---|
| **1.1** Translate business problems into Claude-based AI solutions | Chapter 1, *What You Are Actually Being Asked to Decide* |
| **1.2** Design end-to-end architectures (input → processing → output → feedback loops) | Chapter 1, *What You Are Actually Being Asked to Decide* |
| **1.3** Select appropriate architectural patterns (workflow, agentic, augmented LLM) | Chapter 4, *Augmented Call, Workflow, Agent* |
| **1.4** Design multi-agent systems and orchestration strategies | Chapter 5, *When a Second Agent Is a Liability* |
| **1.5** Apply decomposition techniques for complex problem solving | Chapter 4, *Augmented Call, Workflow, Agent* |
| **1.6** Align solutions to business value pillars (efficiency, transformation, productivity, cost, performance SLAs) | Chapter 3, *Sizing, Scoping, and the Feasibility Verdict* |

## Domain 2: Claude Models, Prompting & Context Engineering (13% of the exam)

| Objective | Owned by |
|---|---|
| **2.1** Select appropriate Claude models based on trade-offs | Chapter 7, *Model, Context Window, Context Strategy* |
| **2.2** Design system prompts, templates, and guardrails | Chapter 8, *Prompts as Architecture* |
| **2.3** Apply prompt engineering techniques (zero-shot, few-shot, chain-of-thought) | Chapter 4, *Augmented Call, Workflow, Agent* |
| **2.4** Optimize context windows and manage token usage | Chapter 7, *Model, Context Window, Context Strategy* |
| **2.5** Implement prompt reuse strategies (caching, modular prompts, Skills) | Chapter 8, *Prompts as Architecture* |

## Domain 3: Integration (19% of the exam)

| Objective | Owned by |
|---|---|
| **3.1** Evaluate tool/agent configuration for capability bloat | Chapter 10, *Entry Points, Routes, and the Integration Layer* |
| **3.2** Analyze authentication and authorization requirements to identify security gaps | Chapter 10, *Entry Points, Routes, and the Integration Layer* |
| **3.3** Evaluate accuracy-latency trade-offs and justify configuration decisions | Chapter 11, *The Numbers Before You Build* |
| **3.4** Analyze observability challenges and select monitoring strategies at scale | Chapter 12, *Observability at Scale* |
| **3.5** Design a RAG pipeline with appropriate chunking and indexing strategies | Chapter 9, *Chunking, Indexing, and the Query You Did Not Anticipate* |
| **3.6** Apply retrieval strategies matched to data shape and query pattern | Chapter 6, *Reference Architectures and Retrieval Against Live State* |
| **3.7** Evaluate connection protocols and select the appropriate integration mechanism (MCP, API/CLI, agent-to-agent) | Chapter 10, *Entry Points, Routes, and the Integration Layer* |
| **3.8** Evaluate progressive discovery vs. monolithic context strategy | Chapter 7, *Model, Context Window, Context Strategy* |

## Domain 4: Evaluation, Testing & Optimization (16% of the exam)

| Objective | Owned by |
|---|---|
| **4.1** Define evaluation metrics (accuracy, latency, cost, safety, security) | Chapter 13, *Evals as Acceptance Criteria* |
| **4.2** Design evaluation datasets and test frameworks using mixed methodologies | Chapter 13, *Evals as Acceptance Criteria* |
| **4.3** Conduct A/B testing and iterative improvements | Chapter 14, *A/B, Shadow, and Not Overclaiming* |
| **4.4** Diagnose system issues (prompt failure, hallucinations, model mismatch) | Chapter 14, *A/B, Shadow, and Not Overclaiming* |
| **4.5** Optimize token usage, latency, and cost-performance trade-offs | Chapter 11, *The Numbers Before You Build* |
| **4.6** Monitor system performance using logging and observability tools | Chapter 12, *Observability at Scale* |

## Domain 5: Governance, Safety & Risk Management (14% of the exam)

| Objective | Owned by |
|---|---|
| **5.1** Implement guardrails and safety controls | Chapter 15, *The Safety Stack, and Where the Guardrails Sit* |
| **5.2** Identify risks, limitations, and failure modes of LLM systems | Chapter 15, *The Safety Stack, and Where the Guardrails Sit* |
| **5.3** Apply human-in-the-loop validation strategies | Chapter 16, *Human Review by Stakes, Not by Volume* |
| **5.4** Ensure compliance with regulations (e.g., GDPR, HIPAA, FedRAMP) | Chapter 17, *Proving It to Someone Who Was Not There* |
| **5.5** Address ethical AI considerations (bias, fairness, transparency) | Chapter 17, *Proving It to Someone Who Was Not There* |

## Domain 6: Stakeholder Communication & Lifecycle Management (14% of the exam)

| Objective | Owned by |
|---|---|
| **6.1** Conduct structured discovery and requirement gathering | Chapter 2, *Discovery Is Elicitation, Not Conversation* |
| **6.2** Communicate architectural decisions and trade-offs | Chapter 18, *Defending the Design* |
| **6.3** Manage stakeholder feedback loops and expectation alignment (including SLAs) | Chapter 19, *Feedback Loops and What You Owe When One Breaks* |
| **6.4** Document architectures and provide implementation guidance | Chapter 20, *Documentation That Survives Your Absence* |
| **6.5** Support lifecycle phases (discovery, design, handoff, monitoring, iteration) | Chapter 3, *Sizing, Scoping, and the Feasibility Verdict* |

## Domain 7: Developer Productivity & Operational Enablement (7% of the exam)

| Objective | Owned by |
|---|---|
| **7.1** Configure Claude tools and environments for teams (e.g., Claude Code) | Chapter 21, *Team Enablement and the Debugging Loop* |
| **7.2** Improve developer workflows using AI-assisted tooling | Chapter 21, *Team Enablement and the Debugging Loop* |
| **7.3** Support debugging and operational issue resolution | Chapter 21, *Team Enablement and the Debugging Loop* |

## Where the Weight Is

Reading order follows the decisions rather than the blueprint, so the weights are spread
across the book rather than concentrated. If you are rationing time, these are the numbers
that should drive it.

| Domain | Weight | Chapters covering it |
|---|---|---|
| 1 Solution Design & Architecture | **17%** | 1, 3, 4, 5 |
| 2 Claude Models, Prompting & Context Engineering | **13%** | 4, 7, 8 |
| 3 Integration | **19%** | 6, 7, 9, 10, 11, 12 |
| 4 Evaluation, Testing & Optimization | **16%** | 11, 12, 13, 14 |
| 5 Governance, Safety & Risk Management | **14%** | 15, 16, 17 |
| 6 Stakeholder Communication & Lifecycle Management | **14%** | 2, 3, 18, 19, 20 |
| 7 Developer Productivity & Operational Enablement | **7%** | 21 |

Total objectives: **38**, all of them owned by exactly one chapter.
