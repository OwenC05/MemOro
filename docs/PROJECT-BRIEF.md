# MemOro project brief

## Purpose

People working with agents lose time reconstructing decisions, reviewing repeated work, and checking what happened after an interrupted run. MemOro aims to make that continuity dependable across software, research, and creative production. Its first users are people already working with agent clients who need to switch projects, sessions, or tools without re-explaining the work.

The product thesis is that a shared record of decisions, evidence, approvals, and verification can reduce human rework. Memory retrieval is one part of that loop. The benchmark should be able to show where the thesis holds, when a simpler setup works as well, and what extra time or cost the framework adds.

## Capabilities under consideration

| Capability | Proposed behavior |
| --- | --- |
| Project state and storage | Keep stable project and task identities. Store current decisions, supersession links, unresolved questions, approvals, and pointers to external artifacts. Preserve the difference between a user decision, a source claim, an observed result, and an agent inference. |
| Retrieval | Fetch relevant records for the current task with project scope, time, and source references. Record which results the agent actually receives. Compare direct file access, keyword search, hybrid retrieval, and on-demand evidence gathering. |
| Dreaming | Review accumulated records and propose useful merges, corrections, and reusable lessons. Preserve the source and scope of each proposal, make changes inspectable and reversible, and measure effects on later tasks. |
| Research | Select discovery and reading tools for the question. Carry exact source locators, conflicting evidence, and unresolved coverage through handoffs and into synthesis. |
| Planning and delegation | Record the objective, acceptance criteria, dependencies, and ownership. Use a capable single agent by default and delegate separable work when an integration owner can verify it. |
| Implementation, review, and recovery | Record source revisions, artifact changes, checks, and observed results. Reconcile actual state after interruptions, invalidate work affected by changed inputs, and surface partial completion or uncertainty. |
| Client integration | Start with a native Windows workflow in Codex. Test a second client against the same project state. Use supported host capabilities for agent execution, permissions, and sandboxing. |

## First proposed release

Build one complete handoff. Record a decision with its source, finish part of a task, interrupt it, revise a decision, then resume and verify the result in a fresh session. A single-agent path with explicit saves and search is enough to make the initial comparison. Demonstrate the same handoff in a second client before making claims about portability.

A local SQLite store with full-text search is a candidate baseline. Add hybrid retrieval, automated capture, and dreaming as separate experiments with measured benefits. Keep storage, interfaces, automation triggers, permissions, and packaging open until the first specification. [SQLite FTS5 documentation](https://sqlite.org/fts5.html)

## Success criteria

- A fresh session recovers the current decision and its source, then resumes from the actual unfinished state.
- Projects stay scoped. Explicitly shared preferences have a defined scope, and superseded details stay out of ordinary retrieval.
- The run distinguishes work attempted, artifacts produced, checks passed, and outcomes accepted. Reviewers can inspect the evidence for consequential claims.
- Evaluation compares verified task completion, stale or wrong-project recall, evidence coverage, human rework, time, and cost against practical baselines.
- A public, reproducible demo uses safe fixtures and includes baseline results and known failure cases.

See the [working workflow](WORKFLOW.md), [research register](RESEARCH.md), and [benchmark proposal](BENCHMARK.md) for the inputs to scoping.
