---
name: zero-tech-debt
description: "Use when the user explicitly invokes /zero-tech-debt while adding, removing, replacing, or reshaping functionality in a project, plugin, skill, app, or related artifact and wants a lean final-state result without speculative backward compatibility, migration machinery, historical wording, or process residue."
disable-model-invocation: true
---

# Zero Tech Debt

Treat invocation as approval for a clean break within the user's stated scope. Make the implementation and every touched artifact read as though the intended final state had existed from day one.

Do not broaden the task, erase user data, or break an external boundary silently. When an active external consumer or persisted-data constraint cannot be updated in the same change, state the concrete conflict and ask for direction instead of inventing compatibility machinery.

## Work from the final state

1. State the intended end state in one or two sentences.
2. Find current in-scope callers, persisted data, explicit contracts, and safety or integrity invariants.
3. Update all in-scope consumers together.
4. Remove the superseded implementation and its residue.
5. Verify the final behavior with the smallest relevant checks.

Optimize for the coherent result, not the smallest diff from the historical shape.

## Keep only current constraints

Retain something only when it serves a current, evidenced need:

- An active caller or consumer uses it.
- The user explicitly requires the contract.
- Current user-owned data depends on it.
- It protects a live security, safety, or integrity invariant.
- The artifact's present purpose is release history, audit, citation, or formal traceability.

Delete or rewrite compatibility paths, aliases, wrappers, adapters, fallbacks, transition flags, migration machinery, duplicate flows, and version-shaped names that exist only because of the route taken to reach the current design.

Do not preserve behavior for hypothetical consumers. Do not create a framework for one change.

## Clean every touched artifact

Apply the same final-state rule to code and non-code material, including comments, tests, documentation, prompts, skill instructions, examples, configuration, labels, messages, and user-facing text.

- Make comments explain a current non-obvious reason, constraint, or invariant. Remove change history and obsolete implementation narration.
- Make names and prose describe present product or domain intent. Remove internal planning, work-item, requirement, phase, and implementation-era language from ordinary artifacts.
- Make tests describe and protect current behavior. Remove tests whose sole purpose is preserving behavior the request replaces or deletes.
- Remove stale instructions, examples, cross-references, and duplicated guidance together with the superseded behavior.
- Keep historical wording only where recording history or traceability is the artifact's current job.

Prefer deleting a comment that merely restates the code over rewriting it.

## Decide cleanly

| Evidence | Action |
|---|---|
| All active consumers are in scope | Update them together and remove the old surface. |
| No current consumer exists | Delete the obsolete path. |
| The request replaces or removes behavior | Delete its implementation, documentation, and compatibility-only tests. |
| Compatibility is proposed only as a precaution | Do not add it. |
| A proven external or persisted-data boundary exists | Surface the boundary and request a decision. |
| Historical language appears in an operational artifact | Rewrite it around current intent. |
| History or traceability is the artifact's purpose | Preserve only the relevant record. |

## Verify proportionally

Test the intended behavior and current in-scope consumers. Search the touched scope for leftover compatibility, migration, version-history, and internal-process residue, then judge each hit by its current purpose.

Do not build a backward-compatibility matrix, migration suite, or broad audit unless the user explicitly requests one. Stop when the relevant checks prove the final state.

## Finish in the present tense

Report the resulting behavior, what obsolete surface was removed, and any constraint retained for a current reason. Do not turn the handoff into a migration narrative.
