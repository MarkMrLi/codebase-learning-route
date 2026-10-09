---
name: codebase-learning-route
description: Create a targeted code-reading route by interviewing the user, building a resumable study Harness, running parallel source exploration, reviewing the findings, and producing a source-anchored learning path.
---

# Codebase Learning Route

## Workflow

### 1. Grill the learning goal

Inspect the repository overview, then ask one question at a time until these are
clear:

- the mechanism the user wants to understand;
- one concrete input, event, command, or behavior to trace;
- where the trace starts and ends;
- the two or three highest-priority questions;
- desired depth and time budget.

Write the answers as `focus.md`.

### 2. Create a resumable study Harness

Read [references/harness.md](references/harness.md). Create or reuse the study
directory and initialize:

- `README.md` for clean-Agent guidance;
- `focus.md` for the agreed question;
- `context-map.md` for likely source routes;
- `task-board.md` for ownership and dependencies;
- `progress-log.md` for append-only transitions;
- `exploration/`, `findings/`, and `reviews/` for owned artifacts.

### 3. Explore by mechanism, in parallel where useful

Create independent tasks around vertical questions such as entry/call flow,
state and data transformation, variants, and tests. Claim the tasks on the
board, then run parallel Agents when the request authorizes parallel work.

Each Agent owns one exploration file and records:

- one end-to-end trace;
- files, symbols, and focused tests;
- inputs, outputs, state changes, and next calls;
- `Observed`, `Documented`, `Evaluated`, `Inference`, and `Unknown` claims;
- verification results and open questions.

### 4. Review before synthesis

Turn the explorations into focused findings. Assign an independent reviewer to
check each central claim against current source and tests. Apply requested
changes and repeat review until `PASS`. The coordinator records every state
transition in the board and progress log.

### 5. Produce the learning route

Create `learning-route.md` from the reviewed findings. Start with the concrete
scenario, then provide a short route and a deep route. Every stop contains:

```markdown
### Stop <N>: <question>
- Open: <path>::<symbol or test>
- Follow: <input -> state/decision -> output/next call>
- Checkpoint: <question to answer>
- Try: <focused test or small experiment>
- Next: <what this unlocks>
```

### 6. Handoff accurately

Verify the route's file/symbol links and focused tests. Update the Task Board and
Progress Log, then report the Guidance entrypoint, reviewed findings, learning
route, verification results, and current worktree state.
