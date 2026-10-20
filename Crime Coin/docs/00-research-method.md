# Research method

This project studies a friend’s **trading playbook**. The question is whether any
of its processes rest on something we can state as a **fundamental** — a
mechanism, a measurable market fact, or a repeatable relationship — rather than
only a rule of thumb that has worked for him.

We do **not** start by improving the playbook. We start by understanding it.

## Two phases, in order

### Phase A — Understand the component

For one component at a time, write down:

1. **What he does** — the concrete action or check in his own terms.
2. **What he thinks it means** — the story behind the signal (operator control,
   short squeeze, distribution, etc.).
3. **What would have to be true** — the market fact or mechanism that would
   make that story hold.
4. **What we can actually observe** — data that exists, what is only inferred,
   and what we cannot see.
5. **Known limits** — where he already says the signal fails, is optional, or
   is hard to prove.

Phase A ends when that writeup is good enough that we could explain the
component to someone who has not read the PDF. No signal changes during Phase A.

### Phase B — Only then, choose one outcome

After Phase A, pick **one** of these. Leave the others unchosen until we have a
reason.

| Outcome | Meaning |
|---------|---------|
| **Add on** | Keep his signal. Look for an extra observation that supports or filters it. |
| **Replace** | His signal is a proxy. A more direct observation should stand in for it. |
| **Augment** | Keep the intent of the step, but change how it is measured, timed, or combined. |

“Do nothing yet” is allowed. If we cannot name the fundamental, we park the
component and move on.

## What we will not do early

- Build scanners, monitors, or bots before a component’s Phase A is written.
- Treat a backtest or a new indicator as the way to *understand* a step.
- Mix golden-crime, DWF-style, and old-coin processes in one component. They
  are separate playbooks until we say otherwise.

Heavy, long, or rising-cost work still needs an explicit go-ahead, including
during Phase B.
