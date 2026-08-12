# Optional Reusable Capability Dependencies

Load this reference only when the selected minimum contract explicitly depends on a reusable Skill or Agent capability.

A reusable capability is an optional dependency, not a normative authority, implementation evidence source, or descriptive view.

## Resolution

1. Identify the capability by role and why the project contract depends on it.
2. Check the repository's selected platform location and any user-provided shared source location.
3. Record every exact path checked and any detected version or conflicting copy.
4. Use the authoritative installed copy when available.
5. When a shared source exists but the target installation does not, report `available but not installed` and pause only the dependent branch.
6. When no source exists, report the missing capability and pause only the dependent branch.
7. Ask which copy is authoritative when multiple conflicting versions exist.

Do not install, copy, or replace a capability unless the user explicitly authorizes that action. Do not claim a capability was invoked when its instructions were unavailable.

Dependency troubleshooting must not expand the target contract level. If the capability is optional, skip it and preserve the smaller contract.
