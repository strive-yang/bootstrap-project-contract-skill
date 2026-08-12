---
name: bootstrap-project-contract
description: Discover a repository's current governance state, select the lowest sufficient Agent contract level, and create or repair an evidence-based contract. Use when explicitly bootstrapping a repository or reassessing governance in an existing one.
---

# Agent Repository Bootstrap

Decide how much Agent governance a repository actually needs. Preserve sound existing conventions, create only artifacts that solve identified problems, and make no material change when the lowest sufficient contract is already satisfied.

Treat files such as `README.md`, Agent instructions, plans, specs, and decision records as candidates, not requirements. Keep the core process platform-independent.

## Workflow

### 1. Discover the repository knowledge model

Inspect code, manifests, configuration, tests, runtime checks, documentation, existing Agent instructions, planning systems, requirements, and architectural records. Prefer repository evidence over assumptions in the request. Record absent files as facts rather than automatic work items.

Separate what you find into:

- normative authorities: what should be true;
- implementation evidence: what is demonstrably true;
- descriptive documentation: how the current or intended state is explained to people.

Identify how people and Agents currently work in the repository, including external authorities explicitly referenced by the project. Do not infer a platform only from a familiar filename.

Completion criterion: list evidence sources, normative authorities, descriptive views, existing governance artifacts, conflicts, drift, and unknowns without proposing new files yet.

### 2. Classify the current state on independent axes

Read [decision-matrix.md](references/decision-matrix.md). Classify the repository on three independent axes:

- project maturity: `empty`, `prototype`, `established`, or `mature`;
- observed governance state: `none`, `lightweight`, `structured`, or `governed`;
- delivery mode: `one-shot`, `iterative`, `staged`, or `continuous`.

Do not treat the observed governance state as the target. A currently ungoverned project may need a structured contract, and an over-governed repository may need a smaller target.

Completion criterion: assign one evidence-backed value to every axis or name the single missing decision that prevents classification.

### 3. Resolve repository knowledge roles

Read [file-contracts.md](references/file-contracts.md). Resolve normative authority for each applicable role:

- Agent policy;
- requirements;
- delivery planning;
- architecture decisions;
- scoped policy.

Then identify implementation evidence and descriptive views separately. Code, configuration, tests, manifests, and runtime checks establish actual behavior; a README or operational guide describes that behavior but does not override contradictory evidence. A file may serve more than one role only when the repository explicitly treats it that way.

Reuse a coherent authority. When normative authorities conflict, report the conflict instead of silently choosing. When descriptive documentation conflicts with implementation evidence, mark the documentation as drifted and distinguish actual from intended state.

Completion criterion: every applicable normative role has one authority, is explicitly unnecessary, or is blocked by a named conflict; evidence sources are listed; descriptive views are marked current, drifted, missing-but-needed, or unnecessary.

### 4. Select the lowest sufficient target contract

Start at Target Contract Level 0. Use the escalation algorithm in [decision-matrix.md](references/decision-matrix.md) to test whether each level leaves an identified collaboration, delivery, or risk need unsatisfied. Escalate one level at a time and stop at the first sufficient level.

Repository size, code volume, longevity, recurring Agent use, or architectural complexity alone cannot trigger Level 3. Each escalation must name the problem and explain why the lower level cannot solve it.

Recommend the evidence-backed minimum. Ask the user to choose between adjacent levels only when evidence cannot resolve a required predicate or when the user wants direct control. Honor an explicit user-selected level while recording how it differs from the minimum and which needs or costs that choice leaves exposed.

Define the gap between the observed governance state and target contract level. For each candidate artifact, select exactly one action: `create`, `reuse`, `revise`, `skip`, or `ask`. Apply a governance budget: every non-skip action must solve a named current problem. Prefer `reuse` and `skip`.

Use [platform-adapters.md](references/platform-adapters.md) only when a platform convention must be detected or selected.

Completion criterion: state the target level, every escalation decision, the current-to-target gap, governance budget, and a minimal action table with evidence for every non-skip action.

### 5. Apply a risk-based write gate

Write directly when the user explicitly requested the operation, the write set is unambiguous, no authority conflict exists, no source of truth is replaced, and the change is additive or a clearly bounded repair.

Request confirmation before substantially changing an existing authority, deleting or migrating governance artifacts, resolving conflicting authorities, or introducing a platform convention not already selected by the repository or user.

Ask one concise question when missing information changes the target level, knowledge-role mapping, platform mapping, or write risk. Do not add a second confirmation ceremony after a clear, low-risk authorization.

Completion criterion: classify the write as direct, confirmation-required, or blocked, and state the evidence for that classification.

### 6. Write idempotently

Create or revise only the approved minimum contract. Preserve project terminology, style, and unrelated user content. Patch the smallest semantic surface; do not reorganize a correct file for presentation alone.

Before writing, compare the desired semantic state with the current state. When they match, make no change. Do not create a governance artifact merely because this Skill knows how to create it.

Use `verified` for claims supported by implementation evidence, `designed` for normative decisions not yet evidenced in implementation, and `unknown` when neither applies. Exclude credentials, private data, customer content, and unsupported metrics.

Completion criterion: every material change traces to evidence or an explicit user decision, and an immediate second run would produce no material diff.

### 7. Validate

Read [validation-checklist.md](references/validation-checklist.md). Check current-versus-target separation, escalation predicates, knowledge-role boundaries, governance budget, authority uniqueness, link resolution, secret exposure, platform assumptions, and idempotency.

Run safe repository checks when they materially validate a documented claim; label anything not checked as unverified. Report the three-axis current state, target contract level, gap, knowledge model, files changed or skipped, write-gate decision, and remaining unknowns.

Completion criterion: every checklist item is `verified`, `not applicable`, or `unverified`, every residual risk is named, and a second-run plan contains only `reuse` or `skip` unless external facts changed.

## Optional branches

### Platform adapter

Read [platform-adapters.md](references/platform-adapters.md) when the repository already uses a platform convention or the user explicitly chooses one. Keep platform paths out of the core knowledge model.

### Reusable capability dependency

Read [optional-dependencies.md](references/optional-dependencies.md) only when the selected contract explicitly depends on a reusable Skill or Agent capability. Capabilities are optional dependencies, not normative authorities, and dependency troubleshooting is outside the default bootstrap flow.

## Stop conditions

- Stop when a conflict prevents selecting one normative authority and the user has not resolved it.
- Stop before destructive migration or replacement without explicit confirmation.
- Return `No additional governance required` when Level 0 is sufficient or the selected contract is already satisfied.
