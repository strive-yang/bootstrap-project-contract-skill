# Repository Knowledge Model

Separate normative authorities, implementation evidence, and descriptive documentation. Their relationships matter more than their filenames or platform locations.

## Normative authorities

Normative authorities answer: what should be true?

### Agent policy

Define repository-specific Agent behavior: precedence, safety boundaries, required checks, source-of-truth pointers, and scoped policy routing. Keep out transient status, duplicated requirements, credentials, and generic advice.

### Requirements

Define required behavior and scope. Reuse the repository's declared specification system, issue tracker, product document, or other explicit requirements authority. Tests are requirements authority only when the repository explicitly declares them contractual.

### Delivery planning

Define approved work, current stage, exit criteria, and next-step conditions when delivery requires durable coordination. Reuse an existing tracker or planning system.

A `project_task.md` boundary brief is one fallback for staged work without another planner, not a universal requirement. Keep it to goal/problem, current stage, approved scope, non-goals, constraints, exit criteria, open questions, and next-stage entry condition.

### Architecture decisions

Preserve the reasoning behind decisions that are costly to reverse, surprising without context, and the result of a real trade-off. Use an existing decision-record convention and create no record when those conditions are absent.

### Scoped policy

Apply a rule only where a real path, technology, platform, or workflow scope exists. Prefer an existing platform or repository convention and route the scoped policy from its parent Agent policy.

## Implementation evidence

Implementation evidence answers: what is demonstrably true now?

Use code, configuration, manifests, tests, generated artifacts, safe runtime checks, and deployment state when accessible. Evidence can be incomplete or contradictory; record the uncertainty instead of promoting a descriptive document to evidence.

Tests are evidence of exercised behavior by default. A runtime check can verify current operation without defining intended behavior. Evidence does not silently override an approved requirement; a mismatch is implementation drift that must be reported.

Do not modify implementation evidence as part of governance bootstrap unless the user separately authorizes a business or infrastructure change.

## Descriptive documentation

Descriptive views answer: how is the repository explained to people?

README files, operational guides, onboarding notes, and generated reference pages commonly serve this role. They should describe implementation evidence accurately and distinguish intended but unimplemented behavior.

When a descriptive view conflicts with evidence:

- use evidence for the actual state;
- use normative authority for the intended state;
- mark the descriptive view as drifted;
- revise it only when the write gate permits.

Do not create a descriptive artifact when no stable reader need exists. A `README.md` is common, not mandatory.

## State labels

- `verified`: supported by implementation evidence;
- `designed`: established by normative authority or explicit user decision but not yet verified in implementation;
- `unknown`: supported by neither authority nor evidence.

A descriptive view may contain all three labels but is not itself proof of `verified` state.

## Conflict handling

Report competing normative authorities with the behavior each would produce and ask which should win. Report authority-versus-evidence mismatches as implementation drift. Report documentation-versus-evidence mismatches as descriptive drift. Do not collapse these three conflict types into one generic inconsistency.
