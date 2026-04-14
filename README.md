# pi-config

A minimal **Pi project template** built from two files:

- `.pi/SYSTEM.md`
- `AGENTS.md`

Use this repository as a GitHub template when you want to start a new repo with a custom Pi system prompt plus a repo-local operating contract already in place.

## What these files do

### `.pi/SYSTEM.md`

This file is the **custom Pi system prompt**.

In this configuration it tells Pi to:
- behave like a careful coding assistant inside Pi
- preserve developer agency and be explicit about what it read, changed, validated, assumed, and does not know
- follow Pi’s real lifecycle, hook names, prompt composition order, and tool semantics
- prefer minimal, inspectable changes
- use explicit execution phases: `ANALYSIS`, `BOOTSTRAP`, `RED`, `GREEN`, `REFACTOR`
- refuse shortcuts that violate bootstrap, TDD order, determinism, parity, structure, or safety constraints

It also documents the actual Pi runtime model, including:
- prompt assembly order
- `input` / `before_agent_start` ordering
- session and resource events
- tool lifecycle events
- parallel tool behavior
- file mutation guidance for custom tools
- mode semantics

### `AGENTS.md`

This file is the **repo-local project contract**.

In this configuration it tells Pi to:
- treat the repo as TDD-first
- establish a minimal automation foundation before production tests or production code
- maintain local/GitHub automation parity
- use one canonical source of validation rules
- enforce structure limits such as:
  - max production nesting depth: 3
  - max construct size: 30 LOC
  - max file size: 200 LOC
- optimize for deterministic, fast, safe feedback loops

`AGENTS.md` is appended as project context and is authoritative for the repo it lives in.

## How Pi uses this configuration

When Pi starts in a repo using this layout, the effective prompt is built from:
1. `.pi/SYSTEM.md`
2. optional `.pi/APPEND_SYSTEM.md` if present
3. discovered `AGENTS.md` / `CLAUDE.md` files from the global agent dir plus ancestor walk from `cwd`
4. loaded skills, if any
5. current date
6. current working directory

Important behavior from this setup:
- a custom `.pi/SYSTEM.md` replaces Pi’s default textual system prompt
- Pi’s default textual `Available tools` section is not automatically inserted when custom `SYSTEM.md` is used
- repo-local `AGENTS.md` is meant to define the project contract, not generic runtime semantics

## Recommended directory layout

Use this at the root of a repo:

```text
your-project/
├─ .pi/
│  └─ SYSTEM.md
└─ AGENTS.md
```

Optional additions later:

```text
your-project/
├─ .pi/
│  ├─ SYSTEM.md
│  ├─ APPEND_SYSTEM.md
│  └─ extensions/
├─ AGENTS.md
├─ skills/
└─ prompts/
```

## Use this template on GitHub

To create your own Pi project from this repo:

1. Open this repository on GitHub.
2. Click **Use this template**.
3. Choose the owner, repo name, and visibility for your new project.
4. Create the new repository from the template.
5. Clone your new repository locally.
6. Customize `.pi/SYSTEM.md` and `AGENTS.md` for your project.
7. Start Pi from the new repo root and run:

```text
/reload
```

If you prefer a direct link, GitHub also supports generating from:

```text
https://github.com/srinitude/pi-config/generate
```

## Copy this config into an existing repo

From the target repo root, copy in:
- `.pi/SYSTEM.md`
- `AGENTS.md`

Then start Pi from that repo root and run:

```text
/reload
```

## Quick sanity check inside Pi

After loading the config, verify:

```text
/reload
```

Then check that:
- Pi starts in the repo root you expect
- the startup header shows the expected context files
- the agent follows the phase protocol
- the agent checks bootstrap status before implementation work
- the agent does not claim tests/build/parity without verification

## When to edit which file

Edit `.pi/SYSTEM.md` when you want to change:
- Pi runtime assumptions
- agent behavior policy
- tool usage policy
- lifecycle/hook expectations
- execution protocol

Edit `AGENTS.md` when you want to change:
- repo-specific operating contract
- TDD/bootstrap rules
- automation and CI/CD policy
- structure constraints
- definition of done

## Notes

- Keep `.pi/SYSTEM.md` focused on Pi behavior and prompt/runtime policy.
- Keep `AGENTS.md` focused on repo policy.
- Avoid duplicating the same rule in both places unless technically necessary.
- If you add `.pi/APPEND_SYSTEM.md`, do it intentionally because it changes prompt meaning between `SYSTEM.md` and appended project context.
