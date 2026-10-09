# Codebase Learning Route

Turn “I want to understand this codebase” into a learning route focused on a concrete mechanism, grounded in source code, and easy to resume.

This Agent Skill clarifies your learning goal by asking one question at a time, traces actual calls, state changes, and tests, then produces a reading route after independent review. Use it to explore an unfamiliar codebase, understand how a request executes, or study a system mechanism.

## What It Does

1. **Clarify the goal**: Identify the mechanism, concrete input, trace boundaries, priority questions, and time budget.
2. **Create a study directory**: Save the goal, source map, task status, and progress so you can continue later.
3. **Trace the mechanism**: Record call chains, data transformations, state changes, relevant tests, and unknowns; explore in parallel when authorized.
4. **Review independently**: Check central explanations against current source code and tests, then resolve issues before synthesis.
5. **Build the learning route**: Provide both a short route and a deep route. Each stop includes where to look, what to trace, a learning checkpoint, a small experiment, and the next step.

Explanations distinguish direct observations, documentation, experimental results, inferences, and unknowns. Route quality still depends on the repository, model, and actual verification; file format checks do not replace an assessment of learning outcomes.

## Installation

Give this to your Agent:

```text
Install this skill: https://github.com/MarkMrLi/codebase-learning-route/tree/main/skills/codebase-learning-route
```

## Usage Example

Ask Codex in the target codebase:

```text
Use $codebase-learning-route to help me understand how a request moves from its entry point to response generation in this project.
Focus on how state is passed along and how errors are handled. I have 45 minutes.
Ask me one question at a time to clarify the trace scope, then generate a reading route.
```

To authorize parallel exploration, add:

```text
You may use parallel subagents for exploration and independent review.
```

A typical study directory contains:

```text
<study-dir>/
├── README.md             # Study directory entry point
├── focus.md              # Learning goal and scope
├── context-map.md        # Source map
├── task-board.md         # Task status, ownership, and dependencies
├── progress-log.md       # Progress records
├── exploration/          # Exploration notes
├── findings/             # Reviewed explanations
├── reviews/              # Review records
└── learning-route.md     # Final reading route
```

## Repository Structure

```text
codebase-learning-route/
├── README.md
├── .gitignore
└── skills/
    └── codebase-learning-route/
        ├── SKILL.md
        ├── agents/openai.yaml
        └── references/harness.md
```

The README is for people installing and using the skill; `SKILL.md` and its references are for the Agent executing the workflow. Project materials generated during study belong in the target project's study directory.
