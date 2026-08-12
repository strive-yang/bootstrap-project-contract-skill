# Minimum Contract Validation

Mark every item `verified`, `not applicable`, or `unverified`. An unverified item must retain its uncertainty in the final report.

## Current state and target

- [ ] Project maturity, observed governance state, and delivery mode are classified independently.
- [ ] Observed governance state describes what exists now and is not reused as the target level.
- [ ] Target contract level is stated separately, with the current-to-target gap.

## Lowest-sufficient escalation

- [ ] Evaluation started at Level 0.
- [ ] Every escalation names a concrete unsatisfied need and explains why the lower level fails.
- [ ] Level 2 is supported by recurring coordination, durable planning, or a real scoped-policy need.
- [ ] Level 3 has a named hard trigger and an explanation of why Level 2 is insufficient.
- [ ] Code volume, age, complexity, integrations, or frequent Agent use did not independently trigger escalation.
- [ ] An explicit user level override records uncovered risks or added maintenance cost.

## Repository knowledge model

- [ ] Normative authorities, implementation evidence, and descriptive views are listed separately.
- [ ] Every applicable normative role has one authority or is explicitly unnecessary.
- [ ] Code, configuration, tests, manifests, and runtime checks are treated as evidence unless explicitly declared normative.
- [ ] Descriptive documentation is not used as proof of actual implementation state.
- [ ] Authority conflicts, implementation drift, and descriptive drift are distinguished.
- [ ] Reusable Agent capabilities remain outside the authority map.

## Minimum governance

- [ ] Every created or revised artifact solves a named current problem.
- [ ] The artifact set stays within the target level's governance budget.
- [ ] Optional specs, decisions, scoped policies, context files, and capabilities were skipped unless evidence justified them.
- [ ] Level 0 or `No additional governance required` was considered as a valid result.

## Authority integrity and platform neutrality

- [ ] No external tracker, spec system, or repository-native authority was duplicated for convenience.
- [ ] Platform-specific paths were reused only when detected or explicitly selected.
- [ ] No platform directory or dependency structure was created merely because an adapter supports it.

## Content, safety, and state labels

- [ ] Relative links resolve.
- [ ] Documented commands and operational claims are verified or labeled unverified.
- [ ] `verified`, `designed`, and `unknown` match evidence and authority status.
- [ ] Existing user content and terminology are preserved unless change was authorized.
- [ ] No secrets, credentials, private data, customer content, or fabricated metrics were added.

## Idempotency

- [ ] Desired semantic state was compared with current state before writing.
- [ ] Cosmetic reorganization was not treated as a necessary repair.
- [ ] Recomputing the target level and artifact actions produces the same target with only `reuse` and `skip` unless an external fact changed.

## Report

Report the three-axis current state, target contract level, escalation decisions, current-to-target gap, knowledge model, governance budget, actions taken, skipped artifacts, write-gate decision, unverified claims, and second-run result.
