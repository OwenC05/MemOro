# Benchmark plan

This draft measures whether MemOro helps people resume and verify complex work across sessions and agent clients, with less rework at an acceptable cost. See the [research register](RESEARCH.md) for the evidence and failure reports behind the design.

## Representative tasks

| Domain | Scenario | Evidence required to pass |
| --- | --- | --- |
| Software | Interrupt a code change, revise a requirement and the source revision, then resume in a fresh session. | The patch meets the current requirement. Targeted checks run against the submitted revision, and the handoff identifies any pending integration checks. |
| Research | Resume a claim review after a source update. Include conflicting passages and one missing piece of evidence. | The conclusion links to the exact source versions and passages, distinguishes disagreement from missing evidence, and gives the next reader enough material to verify it. |
| Creative | Resume production after the approved shot or reference changes. Leave a visual check pending when the session ends. | The work follows the current reference and preserves the agreed constraints. A reviewer can find the submitted artifact, the approval, and the pending visual check. |

Use sanitized or synthetic materials with attributable source versions. Within each domain, include an uninterrupted control and an interrupted variant. For the handoff demo, repeat the interrupted variant with a second client and inspect what state arrived there.

## Baselines and protocol

1. Compare a capable single agent using ordinary project files, the same agent with AgentMemory, and the closest existing harness for each task. Treat each setup as a separate baseline and document its configuration.
2. Pair runs by task snapshot and scenario. Pin the model version, tool access, budget, and environment where each harness permits it. Record differences when a comparison needs a native configuration.
3. Repeat paired runs with fresh sessions and record all outcomes, including partial and abandoned runs. Report variation alongside aggregate scores. Keep a holdout set for the final comparison.
4. Grade the resulting artifacts and run state against criteria fixed before execution. Use executable checks for software, passage-level support checks for research, and an agreed visual rubric for creative work. Use independent human review where judgment affects the result.
5. Record the starting revision or source state, context delivered, final artifact version, checks performed, and any human corrections. Rerun affected checks if their inputs change.

## Feature comparisons

Measure each addition against the same working baseline. First compare project state and verification records with ordinary handoffs. Then compare keyword, hybrid, and agent-driven retrieval under documented budgets. Test planning, delegation, and independent review separately so each can be kept where its benefit is measurable.

Compare a run with no consolidation against runs with reviewed dreaming proposals. Log the sources and changes behind each proposal, the review effort, and any rollback. Test later recall on both relevant tasks and superficially similar tasks where the lesson should stay out. Include the cost of generating and reviewing proposals when comparing the approaches.

## Failure cases

| Case | Passing behavior |
| --- | --- |
| A large memory exceeds the context budget. | The trace distinguishes retrieved records from delivered records. Required decisions reach the agent or the run flags the missing context. |
| Context compaction, a restart, or a client change interrupts work. | The next session recovers the current task, decisions, and outstanding checks. It can identify records that were superseded. |
| An input changes after downstream work has been recorded. | Affected results are recomputed or marked stale. Completed effects are reconciled before recovery can repeat them. |
| A research branch fails. | The result preserves successful sibling evidence and reports the failed branch as a gap in coverage. |
| Exact identifiers appear alongside similar names or aliases. | Exact lookup finds the intended record and preserves distinct entities where scope or source differs. |
| A correction conflicts with a prior decision, or two projects share similar vocabulary. | Active recall uses the applicable current decision and respects project boundaries. The run links to the source of the correction. |

## Scorecard and open decisions

Report verified completion, stale decisions used, wrong-project retrieval, evidence coverage, human attention and rework, elapsed time, context size, and total cost. Inspect regressions per domain before aggregating. Record the conditions under which an improvement holds.

Scoping still needs to settle fixture selection, repetition counts, pass thresholds, acceptable overhead, the initial second client, and the specific harness baselines. Freeze those choices before scoring the holdout.
