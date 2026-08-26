# Chapter 18: Defending the Design

**Summary:** *A design review is not a test of whether the design is good. It is a test of whether the people who have to approve it, fund it and build it can tell that it is. This chapter covers how to order a briefing so each audience gets what it can act on, what a decision record must contain to stay usable a year later, and what to do when the evidence says your sponsor is wrong.*

## Sequence Depth by What the Audience Must Do

One briefing, two audiences, and they need different things from the same material.

A sponsor owns the business consequence. They approve, they fund, they defend the choice to their own peers. **What they need is the decision and what it means for the business**, and then, only if they want it, the reasoning underneath.

Engineering leads own the implementation. They need to build the thing faithfully, which means **knowing which constraints drove the choice**, because a decision handed over without its rationale gets reimplemented as somebody's guess the first time reality pushes back.

The structure that serves both is a descent. **Lead with the decision and its business consequence, then go down into the technical rationale.** Anybody who has what they need can stop reading at their own depth.

Three failures show up as options, and each is a different way of refusing to sequence.

**Choosing one audience.** Pitch entirely at the sponsor and the engineers cannot implement faithfully. Pitch entirely at the engineers and the sponsor sits through detail they cannot act on and never hears the trade-off they are accountable for.

**Omitting the rationale.** This converts a communication into a directive. The engineers cannot tell what was traded away, and the sponsor cannot defend the choice to anybody who asks a follow-up question.

**Flattening both into one undifferentiated depth.** Equal weight throughout means each audience wades through the other's material and neither gets what it needed in the section that mattered to them.

Name the thing you are trying to avoid: **the uninformed approval** is a yes from somebody who could not have said no, because nothing in what they were shown would have told them to. It is the most dangerous outcome a review can produce, because it is indistinguishable from success and moves accountability precisely nowhere.

## What a Decision Record Must Carry

A decision record earns its place by staying useful after everybody has forgotten the meeting. That means content, and the distinction from packaging is what scenarios test.

**Two things add decision substance.**

**The rationale and the criteria.** Why this, judged how. Without it a future reader cannot tell whether the choice still holds when a constraint changes.

**The rejected alternatives.** Leave them out and a reader has no way to distinguish a path somebody weighed and rejected from one that never crossed anybody's mind. That distinction is the whole value of the record, and it is exactly what gets cut for brevity.

**Everything else on the usual list is packaging.** A standard template helps people find sections quickly and adds no substance. A distribution routine, a standing meeting, mandatory attendance by senior people: these are organisational routing choices. None of them says anything about whether the document itself sets out reasoning, the basis for judging, or a named owner. **A record built properly gets through to people who were nowhere near that meeting**, which is the only readership that still exists a year later.

**The named anti-pattern is deleting the rejected alternatives to keep the document short.** It removes precisely the part a future reader needs, and guarantees the team relitigates ground it already covered.

## Explain the Choice Through What They Already Care About

When a recommendation has to be justified to somebody who is not an engineer, the argument that survives is built from consequences they already track.

The weak version reaches for **relative cost alone**. It is often true, it is easy to say, and it has a fatal property: **it is overturned by a change in prices.** An argument that depends on today's rate card stops being an argument the moment the rate card moves, and the decision it supported becomes indefensible on grounds entirely unrelated to whether it was ever the right decision.

The strong version names consequences that persist:

- **Freshness.** Whether an answer reflects what is true today rather than what was true when something was last built.
- **Traceability.** Whether a human can follow any claim back to the thing it rests on.
- **Lag.** Whether a change in the business becomes usable immediately, or waits on a rebuild before anyone sees it.

Those are properties of the architecture rather than of the invoice, and they remain true next quarter.

## When the Evidence Says the Sponsor Is Wrong

The hardest scenario in this objective. You hold test results that contradict what somebody with authority has already decided or announced.

Four responses appear and three of them are failures.

**Proceeding while holding the contrary results** is the quiet override. It substitutes your judgement for the accountable owner's without telling them, and it leaves the organisation badly placed when the discrepancy surfaces, which it will.

**Overriding the decision yourself** relocates authority that is not yours. Being right does not transfer accountability.

**Withdrawing from the engagement** protects you and helps nobody.

**The correct move is to put the evidence they are missing in front of whoever owns that decision, and let them keep owning it.** That is the whole of it. You are responsible for their being informed. You are not responsible for their choosing what you would choose.

That formulation is worth holding precisely, because it is what separates the right answer from two plausible neighbours: one conceals information, the other relocates the authority. **The right answer does neither of those things, which is what makes it the right answer.**

## How Wrong Answers Are Built on Communication Questions

- **One audience served, the other abandoned.** **The test: after this briefing, can the sponsor approve and the engineers implement?**
- **A decision delivered without its reasoning.** **The test: could a reader tell what was traded away?**
- **Packaging offered as substance.** **The test: does this add anything to what the record says, or only to how it looks or travels?**
- **An argument that expires.** **The test: would this reasoning survive a change in prices?**
- **Authority relocated, or information withheld.** **The test: does the person accountable for this end up both informed and still deciding?**

| When the scenario says | The answer is usually | The trap is usually |
|---|---|---|
| One briefing must serve a sponsor and engineering leads | Lead with the decision and its business consequence, then descend into rationale | Picking one audience, or giving both the same depth throughout |
| A decision is being communicated | Include why it was chosen and what was traded away | Announcing the decision alone, which reads as a directive |
| A decision record must stay reviewable, two elements wanted | The rationale and criteria, and the rejected alternatives | Templates, distribution routines or mandatory attendance |
| The record is too long | Cut anything before you cut the alternatives considered | Removing rejected options, which is the part a future reader needs |
| A technical choice must be justified to a sponsor | Consequences they already track: freshness, traceability, and lag before a change lands | Relative cost alone, which a price change overturns |
| Your evidence contradicts an announced decision | Put it in front of whoever owns that decision and let them keep owning it | Proceeding quietly, overriding it yourself, or walking away |

The habit worth carrying: **before any review, write down what would have to be true for the audience to say no.** If nothing in your material would produce that answer, you are not presenting a decision.

## What to Remember

- **Order a briefing by what each audience has to do with it: the decision and its business consequence first, then the technical rationale beneath.** Anybody with what they need can stop at their own depth.
- **Three ways to get that wrong**: pitching at **one audience only**, **omitting the rationale**, which turns communication into a directive, and **giving both audiences identical depth**, which makes each wade through the other's material.
- **The uninformed approval is a yes from somebody who could not have said no.** It looks like success and transfers no accountability at all.
- **A decision record carries substance in exactly two things: the reasoning with the basis for judging, and the options that were turned down.** Templates, distribution routines and attendance rules are packaging, and **a record built properly gets through to people who were nowhere near the meeting.**
- **Never cut the rejected alternatives for brevity.** Leave them out and nobody can distinguish a path somebody weighed and rejected from one that never crossed anybody's mind, so the team argues settled ground again.
- **Justify a choice through consequences that persist**: freshness, traceability, and whether a change in the business becomes usable at once or waits on a rebuild. **An argument built on relative cost alone is overturned by a change in prices.**
- **When your evidence contradicts an announced decision, put it in front of whoever owns that decision and let them keep owning it.** Proceeding quietly conceals it, overriding relocates authority you do not have, and withdrawing helps nobody. **You owe them information, not agreement.**
