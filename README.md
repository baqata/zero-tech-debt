# zero-tech-debt

A Claude Code skill for changes that add, remove, replace or reshape functionality, when the result should read as though its final state had existed from day one.

Calling it approves a clean break within the stated scope. Claude updates every in-scope consumer together and removes the superseded implementation along with its residue: compatibility paths, aliases, wrappers, fallbacks, transition flags, migration machinery, version-shaped names, and historical wording in comments, tests, docs, prompts and configuration.

## What it keeps

Only what serves a current, evidenced need:

- an active caller or consumer;
- a contract the user explicitly requires;
- current user-owned data;
- a live security, safety or integrity invariant;
- history in artifacts whose job is history, audit or traceability.

When an external consumer or persisted data cannot be updated in the same change, it names the conflict and asks, instead of inventing compatibility machinery. It does not broaden the task or erase user data.

## Install

As a plugin, inside Claude Code:

```
/plugin marketplace add baqata/zero-tech-debt
/plugin install zero-tech-debt@zero-tech-debt
```

Or as a personal skill:

```bash
git clone https://github.com/baqata/zero-tech-debt.git
cp -R zero-tech-debt/skills/zero-tech-debt ~/.claude/skills/
```

## Use

The skill runs only when called explicitly: `/zero-tech-debt` with the change you want (`/zero-tech-debt:zero-tech-debt` when installed as a plugin).

## License

MIT
