# Platform Adapters

Load this reference only when the repository already uses an Agent platform convention or the user explicitly selects one. Keep the core contract expressed as logical roles.

## Adapter contract

For a detected or selected platform:

1. Map logical roles to the platform's supported files or external systems.
2. Prefer existing repository conventions over creating a new platform layout.
3. State which conventions were detected and which were explicitly selected.
4. Treat platform migration or introduction as confirmation-required when it changes existing authorities.
5. Leave unsupported roles in repository-native or external authorities rather than inventing platform files.

## Illustrative mappings

These mappings aid detection; they are not creation requirements.

| Platform or mode | Agent instructions | Scoped instructions | Reusable capabilities |
| --- | --- | --- | --- |
| Generic/repository-native | Existing instruction document or a concise repository-selected file | Existing directory-local convention | Existing scripts, docs, or external capability registry |
| Codex | `AGENTS.md` when adopted by the repository | `.codex/rules/` when already used or explicitly selected | `.codex/skills/` when the contract explicitly depends on repository-local Skills |
| Claude Code | `CLAUDE.md` when adopted by the repository | Existing Claude-compatible scoped convention | Existing Claude-compatible capabilities |
| Cursor | Existing Cursor instruction file or rules directory | Existing Cursor scoped rules | Existing Cursor-supported capability mechanism |

Do not assume a platform from one filename alone. Inspect configuration, repository instructions, user intent, and tool context. Do not claim adapter support beyond conventions that can be verified in the current environment.

## Generic fallback

When no platform is selected, keep the contract repository-native. Reuse existing documentation and choose a new filename only when a durable instruction problem exists and the user has authorized the write. Do not create hidden platform directories as a generic fallback.
