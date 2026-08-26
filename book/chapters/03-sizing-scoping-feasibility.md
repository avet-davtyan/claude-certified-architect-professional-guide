# Chapter 3: Sizing, Scoping, and the Feasibility Verdict

**Summary:** *Two things get decided badly at the start of a project and both are recoverable only at great expense. The first is whether this is worth building, which turns on naming the kind of value being claimed rather than asserting that value exists. The second is whether it can be built at all inside the constraints, which is arithmetic you can do in an afternoon and which most teams postpone until it is a discovery instead of a decision. This chapter covers the five value pillars, the elimination gate that outranks all of them, and what each phase of the lifecycle owes the next one.*

## Three Feasibility Verdicts, and the Two That Never Get Issued

A feasibility assessment has three possible outcomes, and in practice you will see one.

**Yes.** Buildable inside the constraints as stated.

**Yes, if.** Buildable once something specific changes: a constraint relaxes, a data source becomes available, a target moves. This verdict is only useful when the "if" is written down and has an owner, otherwise it decays into "yes" within about two meetings.

**No.** Not buildable inside the constraints as stated, and the constraints are not moving.

Name the deliverable: **the feasibility verdict** is a written answer to whether this can be built inside the stated constraints, issued before the build starts, and it is a real deliverable rather than a mood. The reason the third verdict almost never appears is not that it is rarely true. It is that no organisation funds a line item for work it correctly declined to begin, so the cost of the absent "no" surfaces somewhere else entirely, half a year on, filed under a different cause.

The habit that makes the verdict honest is small: **say what would have to be true for the answer to change.** A "no" with no conditions attached is an opinion. A "no" that names the two constraints which, if either moved, would make it a "yes" is an engineering result, and it is also the thing that gets the constraint moved.

## Sizing Is Arithmetic You Can Do Before Writing Anything

Most feasibility questions are settled by four numbers, and all four are obtainable before a line of code exists.

How much has to fit at once. Context windows differ by model. Some carry a 1M-token window and others 200k, and a single request tops out at 600 images or PDF pages, or 100 on the smaller-window models.<sup>[1]</sup> If a single unit of work does not fit, no amount of prompt craft rescues it and the design needs retrieval or decomposition. That is a structural finding, not a tuning problem.

How many tokens the work actually is. There is an endpoint that returns the input token count for a message before you send it, accepting the same structured payload a real request would, system prompt and tools and images and PDFs included.<sup>[2]</sup> So the size of your workload is measurable today, with your actual documents, at zero inference cost. A team that estimates this by eye has chosen to, and the humans who later discover the estimate was wrong will not be the ones who made it.

What it costs. Input and output tokens are priced separately on every tier.<sup>[3]</sup> That separation matters more than it looks: a workload that reads 50 pages and emits a sentence has completely different economics from one that reads a sentence and emits 50 pages, and a single blended per-request estimate hides which one you have.

Whether it has to be synchronous. Asynchronous batch processing costs 50% less, and most batches complete inside an hour.<sup>[4]</sup> Whether the work is interactive is therefore a pricing decision as well as a user-experience one, and it is worth asking explicitly rather than defaulting to synchronous because that is how the prototype was built.

One more number belongs in the verdict and it is about time rather than money. Anthropic publishes which models are active, deprecated or retired, with retirement dates and recommended replacements, gives at least 60 days notice before retiring a publicly released model, and fails requests sent to a model after its retirement date.<sup>[5]</sup> **A design pinned to a specific model has a shelf life, and the notice period is the planning horizon you are given.** Build the migration path in, or accept that you have scheduled an outage you have not put in the plan.

## An SLA Is an Elimination Gate, Not a Fifth Thing to Trade

This is the single highest-value distinction in this chapter, because it changes the shape of the analysis rather than one input to it.

When a scenario states a performance commitment, that commitment is not a factor you weigh against cost and quality. **It is a filter you apply first.** Architectures that cannot meet it are removed from consideration, and only then do you compare what survives on value and cost.

Get this backwards and the analysis produces an answer that scores beautifully and cannot meet its own stated commitment. That failure is invisible in the scoring, because a weighted-average approach lets a strong cost result compensate for a latency shortfall, and the average has no way to know that one of those two is a promise with a consequence attached.

**The named anti-pattern is treating a stated commitment as a soft target that tuning will close later.** It is seductive because it is occasionally true and because it defers an unwelcome conversation. Ask instead what is owed when the number is missed. If something is owed, it is a gate.

## The Five Value Pillars, and the Two Everyone Confuses

Business value comes in five kinds, and the exam-relevant skill is not reciting them. It is reading a described outcome and naming which kind it is, because most of the difficulty lives in one distinction.

| Pillar | What is being claimed | The measurement that proves it |
|---|---|---|
| **Efficiency** | The same work now costs less time or money | Time or money consumed per unit of work |
| **Productivity** | The same people now produce more | Output per person, per period |
| **Transformation** | Work that was not previously possible now happens | A capability exists that did not exist before, at any cost |
| **Cost** | Total spend changes | Spend, including spend the new system introduced |
| **Performance SLA** | A commitment with a consequence attached | The committed number, and what is owed when it is missed |

Efficiency and productivity are the pair that gets swapped, and the test is mechanical: look at the denominator.

If the claim is measured per unit of work, it is efficiency. Four hours to review a contract becomes forty minutes: the work is a contract, the measure is time per contract, the pillar is efficiency.

If the claim is measured per person, it is productivity. An analyst who used to process 30 purchase orders a day now processes 90: the measure is output per analyst, the pillar is productivity.

Two consequences fall out of that test and both are worth carrying.

**Eliminating a role is efficiency, not transformation.** The same work is being done for less. Nothing new became possible.

**Time saved is not automatically value realised.** When hours per document drop and billable output stays flat, the efficiency gain is real and the productivity gain did not happen. That is not a rounding error, it is the most common way a successful pilot produces no business result, and naming it as unrealised productivity is what lets somebody go and fix it.

## What Each Lifecycle Phase Owes the Next One

The lifecycle runs discovery, design, handoff, monitoring, iteration. The useful way to hold it is not as a sequence of activities but as a chain of obligations: **a phase output is only real if a later phase consumes it.**

That is the test that separates a genuine deliverable from a ceremonial one. A reusable evaluation set is consumed later. A distilled set of findings is consumed later. A status deck, an announcement, a frozen snapshot of a document nobody opens again, all record or celebrate what already happened and hand nothing forward.

Handoff has the sharpest definition of the five and it is worth memorising. It is finished when the team taking the thing over can run it day to day, work out what went wrong when it misbehaves, and change it without breaking something, none of that requiring access to whoever built it. Three artifacts get you there: the reasoning behind each design decision, the operating procedures, and a set of checks the new team can run to find out whether a change broke anything.

Three things are conspicuously absent. The project's own history, the log of who argued what, and the timeline are all interesting, occasionally political, and of no use whatever to somebody trying to work out why the system just did that.

Monitoring has an equally sharp definition and three named wrong answers. Sound practice looks at the system on a schedule, judges what it finds against a set of test cases topped up from real traffic, and lets that judgement decide whether a change ships. The three failures are acting on the calendar, acting because a vendor shipped something, and acting when a human complains. The first two move without evidence. The third is not monitoring, it is waiting.

## Iteration Versus Redesign: One Test

Teams argue about this for weeks and there is a one-line test.

**A signal forces redesign only when it names a requirement the current decomposition cannot express. Everything absorbable inside the existing boundaries is iteration.**

Accuracy is below target on a subset of cases: the components are still the right components, so that is iteration. Latency is 40% over on the slowest path: still iteration. A new requirement arrives that the system has no place to put, because no component owns that concept and no interface carries it: that is redesign, and calling it iteration means you will spend three months adding a fourth parameter to something that needed a new part.

Volume alone almost never forces redesign. A change in what the system must be able to say usually does.

## How Wrong Answers Are Built on Sizing and Value Questions

Four families cover almost everything here.

- **The wrong denominator.** The option assigns an outcome to a pillar by picking up its most striking noun rather than its measurement. Time per document sounds like productivity because it involves people getting more done. It is efficiency, because the measure is per document. **The test: what is the outcome measured per? Per unit of work is efficiency, per person is productivity, and a capability that did not previously exist at all is transformation.**
- **The commitment demoted to a preference.** The option trades a stated service level against cost or quality, or defers it to tuning. **The test: is something owed when the number is missed? If yes, it eliminates rather than scores.**
- **The artifact that hands nothing forward.** The option produces a record, an announcement, a snapshot or a history. It looks like diligence and no later phase consumes it. **The test: name the phase that will open this and the decision it will make with it.** If you cannot, it is ceremony.
- **The change with no evidence behind it.** The option acts on a schedule, on a vendor release, or on a complaint. **The test: is there a measurement that would have detected this, and does the change get gated on it?**

| When the scenario says | The answer is usually | The trap is usually |
|---|---|---|
| An outcome stated as time or cost per item of work | Efficiency | Reading it as productivity because people are involved |
| An outcome stated as output per person per period | Productivity | Reading it as efficiency because the work got faster |
| A role was removed, or the same work now costs less | Efficiency | Calling it transformation, which requires something newly possible |
| Time was saved but the business output did not move | The efficiency gain is real and the productivity gain was not realised | Recording it as a second efficiency win, or as a failure of the system |
| A response time, availability or throughput commitment is stated | Apply it as an elimination gate before any scoring | Weighing it against cost and quality, or trusting tuning to close it |
| A workload might not fit the context window | Measure it with the token counting endpoint before deciding anything | Estimating by eye, or assuming prompt work will make it fit |
| Work does not have to be interactive | Batch it and take the 50% reduction | Defaulting to synchronous because the prototype was |
| The design names one specific model | Plan the migration; retirement comes with notice, not with mercy | Treating the model choice as permanent |
| A new requirement has arrived mid-build | Iteration, unless no existing component can express it | Calling any hard change a redesign, or any redesign an iteration |
| A team is receiving a system somebody else built | Design rationale, operating procedures, and a set of checks they can run | Project history, timelines and decision logs, none of which help operate anything |
| Something should trigger a change to the system | A refreshed evaluation set, observed on a schedule, gating the change | The calendar, a vendor release, or a user complaint |
| A system works correctly and nobody uses it | The work around the tool was designed badly | Any option that looks for a defect in the tool |

The habit worth more than the table: **when an option names a benefit, ask what number would go up and who would notice.** Most wrong answers here describe a benefit that nobody would be able to detect after the fact.

## What to Remember

- **A feasibility verdict has three outcomes: yes, yes-if, and no.** A "yes, if" is only real when **the condition is written down and has an owner**, and a "no" is only useful when it **names what would have to change to make it a yes**. The missing verdict is almost always "no", because nobody funds the project that should not have started.
- **Sizing is arithmetic available before you build.** The token counting endpoint returns the input token count for a real payload before you send it; **context windows are 1M tokens on some models and 200k on others**, capped at 600 images or PDF pages per request, or 100 on the smaller ones. If one unit of work does not fit, that is a structural finding.
- **Input and output tokens are priced separately**, so a workload that reads a lot and writes a little has different economics from the reverse. **Asynchronous batch processing costs 50% less and most batches finish within an hour**, which makes "does this have to be interactive?" a pricing question.
- **A model has a retirement date and at least 60 days notice, after which requests to it fail.** A design pinned to one model has a shelf life, so the migration path belongs in the plan.
- **A stated SLA is an elimination gate applied before value scoring, not a fifth factor to trade against cost and quality.** The test for whether something is a real commitment: **something is owed when the number is missed.**
- **Five value pillars: efficiency, productivity, transformation, cost, performance SLAs.** Efficiency and productivity are separated by the denominator: **per unit of work is efficiency, per person is productivity**, and **transformation requires work that was not previously possible at any price**. Removing a role is efficiency.
- **Hours saved is not value realised.** When time per item falls and business output stays flat, that is **unrealised productivity**, and naming it that way is what lets somebody act on it.
- **A lifecycle phase output is only real if a later phase consumes it.** Records, announcements and frozen snapshots hand nothing forward.
- **Handoff is finished when the team inheriting the system can run it, diagnose it and change it safely with nobody from the original team available.** That takes **design rationale, operating procedures, and a runnable set of checks**. Project history, timelines and decision logs do none of that work.
- **Iteration becomes redesign only when a requirement arrives that the current decomposition cannot express.** Anything the existing components and interfaces can absorb is iteration, however difficult.
- **Sound monitoring means looking on a schedule, judging against test cases topped up from real traffic, and letting that judgement gate the change.** Acting on the calendar or on a vendor release moves without evidence, and acting on a complaint is not monitoring at all.

## Endnotes for this chapter

1. Context window sizes differ by model, with a 1M-token window on some models and a 200k-token window on others, and a single request can include up to 600 images or PDF pages, or 100 on models with the smaller window. Anthropic, *Context windows* (Claude Platform Docs, accessed 2026-08-25), [https://platform.claude.com/docs/en/build-with-claude/context-windows](https://platform.claude.com/docs/en/build-with-claude/context-windows)

2. The token counting endpoint returns the input token count for a message before it is sent, accepting the same structured input as a message creation request, including system prompts, tools, images, and PDFs. Anthropic, *Token counting* (Claude Platform Docs, accessed 2026-08-25), [https://platform.claude.com/docs/en/build-with-claude/token-counting](https://platform.claude.com/docs/en/build-with-claude/token-counting)

3. Input and output tokens carry separate published rates on every model tier, and Anthropic directs readers to its live pricing page for the current figures. Anthropic, *Pricing* (Claude Platform Docs, accessed 2026-08-25), [https://platform.claude.com/docs/en/about-claude/pricing](https://platform.claude.com/docs/en/about-claude/pricing)

4. The Message Batches API processes large volumes of requests asynchronously, reducing cost by 50 percent, with most batches finishing in less than an hour. Anthropic, *Batch processing* (Claude Platform Docs, accessed 2026-08-25), [https://platform.claude.com/docs/en/build-with-claude/batch-processing](https://platform.claude.com/docs/en/build-with-claude/batch-processing)

5. Anthropic publishes which models are active, deprecated, or retired along with retirement dates and recommended replacements, gives at least 60 days' notice before retiring a publicly released model, and fails requests sent to a model after its retirement date. Anthropic, *Model deprecations* (Claude Platform Docs, accessed 2026-08-25), [https://platform.claude.com/docs/en/about-claude/model-deprecations](https://platform.claude.com/docs/en/about-claude/model-deprecations)
