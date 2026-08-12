# Adaptive Governance Decision Matrix

Classify the current repository before selecting a target contract. The three current-state axes describe independent properties and do not imply a matching target level.

## Project maturity

| Value | Current-state evidence |
| --- | --- |
| `empty` | No stable code, manifest, or project identity exists yet. |
| `prototype` | The project tests an idea and may change shape quickly. |
| `established` | A usable codebase, repeatable workflow, and recognizable boundaries exist. |
| `mature` | The project has sustained use, multiple integrations or owners, and meaningful change risk. |

## Observed governance state

| Value | Current-state evidence |
| --- | --- |
| `none` | No active governance authority is present. |
| `lightweight` | One or two concise authorities cover current collaboration needs. |
| `structured` | Distinct instruction, requirements, planning, or decision authorities are actively maintained. |
| `governed` | Formal policy, approval, traceability, or change-control authorities are actively enforced. |

This axis describes what exists now, including governance that is missing, stale, or excessive. It never selects the target by itself.

## Delivery mode

| Value | Current-state evidence |
| --- | --- |
| `one-shot` | The work is disposable or expected to finish in one bounded pass. |
| `iterative` | The project evolves through informal repeated changes. |
| `staged` | Work advances through approved phases and explicit exit criteria. |
| `continuous` | Ongoing delivery uses a durable tracker, release process, or operational loop. |

## Target contract levels

Start at Level 0 and escalate only when a lower level cannot satisfy an identified need.

| Level | Sufficient contract | Default governance budget |
| --- | --- | --- |
| Level 0 - None | No additional Agent governance is needed; existing repository knowledge may remain in place. | Create no governance artifact. |
| Level 1 - Lightweight | One durable instruction or descriptive view solves the identified knowledge or Agent-behavior problem. | Add at most one or two concise artifacts. |
| Level 2 - Structured | Recurring coordination requires distinct normative roles, staged/continuous planning, or a real scoped policy. | Maintain only the instruction, requirements, planning, decision, or scoped-policy roles the need requires. |
| Level 3 - Governed | Level 2 cannot satisfy a hard requirement for auditability, compliance, strict traceability, formal change control, high-risk approvals, or multi-team ownership boundaries. | Permit formal governance artifacts, with a named hard requirement for every addition. |

The budget is a ceiling, not a quota. Existing descriptive documentation does not by itself raise the target contract level.

## Lowest-sufficient escalation algorithm

Evaluate the levels in order and record each answer.

1. Start at Level 0. Identify a concrete unresolved Agent-behavior, durable knowledge, coordination, delivery, or risk problem. If none exists, stop at Level 0.
2. Test Level 1. Ask whether one concise instruction or descriptive view resolves every identified problem. If yes, stop at Level 1.
3. Test Level 2. Escalate only when recurring coordination requires two or more distinct normative roles, staged/continuous delivery needs durable planning, or a confirmed scoped policy cannot remain clear in one instruction authority. If Level 2 covers all needs, stop.
4. Test Level 3. Escalate only when at least one hard trigger exists: audit/compliance obligation, strict end-to-end traceability, formal change control, high-risk action approval, or multi-team ownership boundaries with enforcement needs. Also state why Level 2 cannot meet that trigger.
5. If evidence cannot distinguish adjacent levels, present the two definitions, recommend the lower level, and ask the user to select. If the user explicitly selects a level, record the override and its uncovered risks or added maintenance cost.

Code volume, repository age, architectural complexity, multiple integrations, or frequent Agent use can inform needs but cannot independently trigger escalation.

## Current-to-target gap

Compare observed governance state with the target contract level:

- target exceeds current: add only the missing roles required by the escalation evidence;
- target matches current: repair drift only when it blocks the target contract;
- target is lower than current: propose reuse or simplification, but require confirmation before deleting, migrating, or demoting an authority;
- current already satisfies target: return a no-op plan.

## Contract artifact actions

| Knowledge role | `create` | `reuse` | `revise` | `skip` | `ask` |
| --- | --- | --- | --- | --- | --- |
| Agent policy | A repository-specific behavior problem needs a durable rule | Existing policy is coherent and sufficient | Policy conflicts, drifts, or obscures active constraints | Default Agent behavior is sufficient | Platform, scope, or precedence is unclear |
| Requirements authority | Durable behavioral scope has no authority | Existing spec, issue system, or declared contract is canonical | Approved requirements changed | Work is trivial or another authority is adequate | Competing requirement sources exist |
| Delivery planning authority | Ongoing coordination has no canonical planner | Existing tracker or plan is active | Scope, stage, or exit criteria drifted | One-shot or informal work needs no planner | Two planners appear authoritative |
| Architecture decision authority | A qualifying decision lacks durable rationale | Existing decisions are current | A decision was superseded | No qualifying trade-off exists | Authority or supersession is unclear |
| Scoped policy | A concrete scoped constraint cannot remain clear in its parent policy | Existing scoped policy is accurate | Scope or trigger drifted | No real scoped problem exists | Platform convention or overlap is unclear |
| Descriptive documentation | Stable facts or workflows need a reader-facing view | Existing documentation matches evidence and intent | Evidence shows factual drift | No stable reader need exists | Intended or actual state cannot be established |

Implementation evidence is inspected, not created as governance. When evidence is missing, retain `unknown`; do not manufacture code, tests, configuration, or runtime results to make documentation look complete.

## Risk-based write gate

| Condition | Gate |
| --- | --- |
| Explicit user request, unambiguous low-risk write set, no conflict, no replacement | Write directly. |
| Existing authority will be substantially changed, replaced, moved, deleted, or demoted | Confirm exact migration. |
| Multiple normative authorities conflict | Ask which one wins before writing. |
| Platform convention would be introduced rather than reused | Confirm platform selection. |
| Critical facts are unknown and would change the target level or content | Ask one focused question. |
| Desired semantic state already exists | Make no material change. |

## Idempotency test

Before and after writing, recompute the escalation decisions and artifact action matrix. A successful immediate second run selects the same target and produces only `reuse` and `skip`. Formatting preferences, newly imagined abstractions, and optional governance features do not justify another change.
