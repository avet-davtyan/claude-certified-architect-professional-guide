# Glossary

**Summary**: *Two kinds of entry. The names this book coins for recurring shapes, which exist so you can recognise a pattern in a scenario you have not seen. And the platform terms whose precise definitions decide items, where being approximately right is the same as being wrong. Chapter references point at where each one is argued.*

## Names This Book Coins

**Chunk by corpus, index by query** (ch. 9). Two decisions that get made as one. Where you cut the material follows the structure of the material; how you match against it follows the questions people actually ask.

The **50-session winner** (ch. 14). A variant declared better on a sample too small to separate it from noise. The defect is not the sample size, it is that the stopping rule was chosen after somebody had seen the data.

The **delegation boundary** (ch. 1). The line separating work handed to the model from work kept under deterministic or human control. Drawing it is the design, not a step within it.

The **evidence artifact** (ch. 17). A record of one single interaction, holding everything that went into it, proof nobody edited it afterwards, and a lifespan matching what a regulator requires. The only thing that answers what happened on a specific transaction.

The **failure taxonomy** (ch. 12). The list of distinct ways a system can be wrong, each needing its own detection. Its defining feature here is that almost every entry reads as success to conventional monitoring.

The **feasibility verdict** (ch. 3). A written answer to whether this can be built inside the stated constraints, issued before the build starts. Comes in three flavours and only two ever get issued.

The **load-bearing control** (ch. 11). The one input that, when changed, actually moves the number you care about. Everything else is a knob you can turn all day.

**Retrieval applied to live state** (ch. 6). Pointing an index at data that changes faster than the index is rebuilt. Produces the worst available output: a confident, well-sourced, stale answer.

**Review by stakes** (ch. 16). Setting each gate according to what a mistake there would cost, judged on whether the outcome can be undone and how far it spreads. The alternative to reviewing by volume, which is unaffordable, or by convenience, which is unsafe.

The **signal that reaches a person** (ch. 19). The only part of a feedback loop that counts. Everything upstream is plumbing, and plumbing loses things quietly.

The **three readers** (ch. 20). The implementer, who needs what to build; the operator, who needs how to run and diagnose it; the reviewer, who needs why it was decided this way. Most documents serve one.

The **uncatchable failure** (ch. 5). A subagent returning a confident, well-formed, wrong result that the orchestrator has no independent means of doubting.

The **uninformed approval** (ch. 18). A yes from somebody who could not have said no, because nothing they were shown would have told them to. Looks exactly like success and transfers no accountability.

The **undocumented assumption** (ch. 2). A constraint that binds the design, was true before the project started, and has never been said aloud because nobody asked a question that would have surfaced it.

The **unencoded policy** (ch. 15). A rule that exists in intent, in prose or in a system prompt, but nowhere in machinery. Holds exactly as long as the model chooses to comply.

The **underspecification gap** (ch. 8). The distance between what you told the model and what you actually require. A contradiction in a prompt is that gap made visible; most of it is not visible at all.

The **verification checklist** (ch. 21). The short run of observations that pins down the faulty layer before anybody touches a setting. Exists because a change made before diagnosis destroys attribution.

The **working-memory cliff** (ch. 7). The point where adding context stops helping and starts costing you recall of what is already there. Silent, and not uniform across the window.

## Platform and Blueprint Terms

**Activity Feed** (ch. 17). The Compliance API's event stream. At-least-once, so deduplicate on activity id, and it offers no completeness signal.

**Architecture decision record (ADR)** (ch. 20). One decision to a record, carrying the **context** that made it necessary, the **decision**, the **alternatives considered**, the **consequences** accepted, and the **date and authors**.

**Adaptive thinking** (ch. 7). Reasoning with no fixed token budget, steered by effort. Requesting it on an extended-thinking-only model returns a 400.

**AI Fluency, the 4Ds** (ch. 1). **Delegation**, deciding what the model does at all; **Description**, telling it what you want; **Discernment**, judging what came back; **Diligence**, owning what you ship. Three named parts each, twelve in total.

**Approval rate parity** (ch. 17). Whether each group gets a yes at a similar rate. Silent on **who was refused in error**, which is **error rate parity**, a separate measurement.

**Agent** (ch. 4). The pattern that picks each next step by looking at what the last one returned. Not "more capable" or "more autonomous".

**Discernment observation** (ch. 1). A statement about the **output**, the **reasoning that produced it**, or the **system's behaviour**. A caveat about **sample size or study duration** is not one.

**Error rate parity** (ch. 17). Whether each group suffers **wrong decisions** at a similar rate. The measurement an approval-rate study leaves unmade.

**Minimum necessary** (ch. 17). The HIPAA rule that only the protected information a purpose requires may be used or disclosed. **Role-based access control implements it**.

**Augmented call** (ch. 4). A single model call given tools, retrieval, or both.

**Bare mode** (ch. 21). A non-interactive run that skips auto-discovery of hooks, skills, commands, subagents, plugins, servers and memory files. Without it, an untrusted repository's hooks and servers run with no prompt.

**Batch processing** (ch. 3, 11, 13). Asynchronous request handling at 50% of standard pricing, mostly finishing inside an hour. Order is not guaranteed; match on your own custom identifier.

**Best-of-N verification** (ch. 14). Running the same prompt repeatedly and comparing outputs, treating inconsistency as a hallucination signal. A detector, not a constraint.

**Cache breakpoint** (ch. 8). Where a cache write happens. A read walks backward from it across at most 20 positions, and a breakpoint on a block that changes every request finds nothing.

**Cache diagnostics** (ch. 8, 12). Comparison against a previous response id reporting the first point of divergence. Only the earliest is reported, so later ones hide behind it.

**Compaction** (ch. 7). Automatic summarisation of older context near the window limit. Drops all content blocks before the compaction block, triggers at a default of 150,000 input tokens, and custom instructions replace the default prompt entirely.

**Constrained decoding** (ch. 8, 13). The mechanism behind structured outputs. Does not guarantee the capitalisation of enum and const values, and breaks on a refusal or on hitting max_tokens.

**Context awareness** (ch. 7). Injection of the total token budget into every system prompt plus a remaining-capacity update after each tool call. Present on some models and absent on others, unrelated to capability.

**Context editing** (ch. 7). Selective clearing of conversation history. Removes rather than summarises, and clearing tool results invalidates cached prefixes.

**Context rot** (ch. 1, 7). Anthropic's name for accuracy and recall degrading as the token count grows.

**Context window** (ch. 7). Working memory rather than storage. Everything counts toward it, including tool definitions and cached prefixes.

**Effort** (ch. 7). Soft guidance on how much of the output allowance goes to thinking, with levels max, xhigh, high, medium and low, where high is the default. Controls how much the model thinks, not how much it says.

**Fast mode** (ch. 11). Up to 2.5x higher output tokens per second on Opus 5 and Opus 4.8 at premium pricing. Same weights, quicker inference configuration, no capability change.

**Files API** (ch. 6). Create-once, use-many: upload a file once and reference it by identifier rather than re-sending it.

**HIPAA readiness** (ch. 17). Requires a countersigned BAA and the arrangement enabled. Enforces feature restrictions automatically with a 400, is bound to the exact BAA version, and is permanent once enabled.

**Hooks** (ch. 21). Shell commands run at fixed lifecycle points, giving deterministic control so an action always happens rather than depending on the model choosing it.

**inference_geo** (ch. 17). The request parameter controlling where inference runs, `global` or `us`. Distinct from workspace geography, which is fixed at creation.

**Managed settings** (ch. 21). The highest layer of the settings precedence stack. Array settings merge, so developers can extend managed lists but not remove from them.

**MCP** (ch. 10). An open protocol connecting model applications to external data and tools over JSON-RPC 2.0, between hosts, clients and servers. The host controls permissions and consent; servers cannot read the whole conversation or see into other servers.

**Memory files** (ch. 21). Loaded at the start of every conversation and treated as context, not as enforced configuration.

**Model ID** (ch. 14). A pinned version whose underlying model stays constant for that ID's lifetime. A dateless ID is not an evergreen pointer; updates ship under a new ID.

**Permission mode** (ch. 15, 16). Which actions run without asking. Manual runs reads only, acceptEdits adds file edits and common filesystem commands, auto runs everything with background checks, dontAsk runs only pre-approved tools, bypassPermissions runs everything. Deny rules survive all of them.

**Plan mode** (ch. 16). Research and proposal with edits blocked until the plan is approved. The reviewer can edit the plan before approving it.

**Programmatic tool calling** (ch. 4). Model-written code that calls your tools from inside a code execution container, replacing a round trip per invocation.

**Prompt caching** (ch. 8, 11). Reuse of an identical prefix. Prefixes build tools, then system, then messages, so editing tool definitions invalidates everything. Reads cost 0.1x base input; a 5-minute write costs 1.25x and a 1-hour write 2x.

**Refusal** (ch. 11, 13, 15). Returned as a successful HTTP 200, not an error. Carries a policy category that may legitimately be null, and the context must be reset before continuing or refusals repeat.

**Skills** (ch. 8, 21). Versioned packages of instructions, scripts and resources. The body loads only when used. A new version is a complete snapshot, not a delta.

**Stop reason** (ch. 11, 12). The field saying why generation ended, with distinct values for a natural finish, the output limit, a stop sequence, a tool call, a pause, a refusal, and an exceeded context window. Not an error field.

**Structured outputs** (ch. 8, 16). Schema-constrained responses so downstream code receives parseable output. See constrained decoding for what it does not guarantee.

**Subagent** (ch. 5, 21). A delegated worker with its own prompt, tools and model. Worth defining only for work that recurs and needs non-default handling.

**Task budget** (ch. 5, 7). A token allowance for a whole agentic loop, shown as a countdown. A soft hint the model may exceed; the enforced ceiling remains the request's max_tokens.

**Token passthrough** (ch. 10). Forwarding a received token to a downstream service. Explicitly forbidden: it circumvents audience controls, misattributes identity in logs, and turns the server into an exfiltration proxy.

**Tool search tool** (ch. 9). Searching a large tool catalogue at request time and loading only what a task needs, by regular expression, by natural language against BM25, or by a custom embedding search.

**Webhooks** (ch. 19). Event delivery to endpoints subscribed at the moment of emission. Three attempts, then dropped rather than queued with no signal of loss, and no replay for events emitted while an endpoint was disabled.

**Workflow** (ch. 4). A fixed sequence of separately inspectable calls, chosen when the path through the work is settled before any request arrives.

**Workspace** (ch. 10). Separation of projects, environments or teams inside one organisation, with keys, members and resource limits assignable per workspace and central billing.

**Zero data retention** (ch. 17). Prompts and responses not stored at rest after the response returns. Does not block ineligible features; using one steps outside the arrangement for that data, silently.
