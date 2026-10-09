# Study Harness Template

## Files

```text
<study-dir>/
|-- README.md             Guidance and clean-Agent entrypoint
|-- focus.md              Reviewed Focus Contract
|-- context-map.md        Seeded, then reviewed navigation map
|-- task-board.md         Current scheduling projection
|-- progress-log.md       Append-only transition history
|-- exploration/          One owned artifact per exploration task
|-- findings/             Reviewed deep explanations
|-- reviews/              Independent review records
`-- learning-route.md     Final question-driven study path
```

`README.md` records the objective, read order, active coordinator, file
ownership, task workflow, and repository verification commands.

`focus.md` records the mechanism, concrete scenario, start/end boundary,
priority questions, desired depth, and time budget.

`context-map.md` records likely entrypoints, component relationships, owning
tests, and open questions.

## Task Board

| Status | Meaning |
| --- | --- |
| `BLOCKED` | A named dependency prevents a valid claim |
| `READY` | Dependencies are complete; no owner is active |
| `IN_PROGRESS` | One named owner has claimed the task |
| `IN_REVIEW` | The artifact awaits independent review |
| `CHANGES_REQUESTED` | Review found unresolved blocking work |
| `DONE` | Exit criteria passed review |
| `DEFERRED` | The user or coordinator removed it from scope |

```markdown
| ID | Status | Owner | Claimed at | Depends on | Output | Exit criteria |
```

## Progress Log

```markdown
## <ISO timestamp> — `<task-id>` — `<event>`

- **Actor:**
- **Transition:** `<old> -> <new>` or `none`
- **Summary:**
- **Artifacts:**
- **Evidence:**
- **Verification:**
- **Decision:** <only when applicable>
- **Next:** <one concrete action>
```

## Artifact contracts

### Exploration

```markdown
# <task-id>: <question>

## Question and scope
## Source map
## End-to-end trace
## Inputs, outputs, state, and side effects
## Evidence labels
## Tests and open questions
```

### Finding

```markdown
# <task-id>: <question-oriented title>

## Question
## Execution trace
## Evidence table
## Design explanation
## Trade-offs
## Learning checkpoints
## Verification
```

### Review

```markdown
# <task-id> Review v<N>

## Verdict
- Result: PASS | CHANGES_REQUESTED
- Reviewed revision:
- Checks run:

## Findings
### P<0-3>: <concise title>
- Artifact claim:
- Current evidence:
- Why it matters for understanding:
- Minimum correction:

## Residual questions
## State transition
```

## Evidence language

- **Observed:** current source or test.
- **Documented:** maintained documentation.
- **Evaluated:** measured by a named workload.
- **Inference:** explanation derived from evidence.
- **Unknown:** not established by inspected evidence.
