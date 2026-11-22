# Scoping handoff

## Where the project stands

MemOro is the project home for the framework direction and research developed from the Agent Workflow Kit. The user expanded the original memory proposal into a research-grounded framework across software, research, and creative production. Storage, retrieval, dreaming, research tools, planning, implementation, and review are within the design space. The scope and implementation choices are still open.

The strongest current product hypothesis is dependable continuity between sessions and clients. The research also surfaced existing tools that already provide portable memory, source history, background consolidation, durable execution, and delegation. Use the comparisons in the [research register](RESEARCH.md) when deciding what to build or reuse.

Prior use of AgentMemory established that startup context and explicit recall are distinct paths. In the recorded setup, startup injection worked in tested cases while task-specific search depended on an explicit request. Use AgentMemory and ordinary project files as baseline candidates. Recheck product behavior in the test environment before drawing head-to-head conclusions. [AgentMemory documentation](https://github.com/rohitg00/agentmemory)

## Decisions for the next specification

1. **Audience and first workflow.** Pick the first user and a task long enough to need a handoff. Define which decisions, evidence, and checks a fresh agent must recover.
2. **Portable records.** Specify project identity, record scope, source locators, task dependencies, supersession, and export and recovery behavior. Keep the first record format small enough to inspect.
3. **Integration and activation.** Choose the first supported client, the retrieval trigger, and the expected behavior after compaction or restart. Define which data the client receives and which events can propose durable updates.
4. **Consolidation and authority.** Decide what dreaming may suggest, who can approve promotions, how to reverse updates, and how to measure benefit against its full cost.
5. **Evidence and evaluation.** Select frozen test fixtures, the baseline setup, the checks and graders, and acceptable trade-offs across quality, human attention, and cost. Record what is held out from development.

The next deliverable is a first-release specification with one end-to-end handoff, a small set of acceptance criteria, and an evaluation protocol. Start with the [project brief](PROJECT-BRIEF.md), [working workflow](WORKFLOW.md), and [benchmark proposal](BENCHMARK.md).
