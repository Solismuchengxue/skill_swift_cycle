# Swift Cycle

[简体中文](README.zh-CN.md)

Swift Cycle is a manually invoked Agent Skill for maintaining personal and small software projects with a lightweight documentation framework and short verification loops.

It follows one practical rhythm:

> Scan quickly → make the smallest useful change → verify immediately → continue or revert.

## What it maintains

- A user-facing `README.md`.
- A concise `DESIGN.md` as the design entry point.
- Repository instructions such as `AGENTS.md`.
- Local, ignored `TODO.md` and `DEVLOG.md`; simple work keeps a normal TODO,
  while explicitly multi-PR or milestone-based work uses a current milestone
  and dependency-ordered PR queue.
- Shared detailed documentation under `docs/`.
- Candidate experiments, evaluation evidence, and important ADRs.
- End-of-project review and methodology extraction.

Small, local changes stay lightweight. Swift Cycle does not require an RFC, ADR, or design document for every edit.
Long-lived plans remain in committable shared documentation or the project's
issue tracker rather than relying on the local TODO as their only source.

## Install

GitHub CLI 2.90 or later can install the same skill for multiple agent hosts.

### Codex

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent codex --scope user
```

Invoke it with:

```text
$swift-cycle
```

### Claude Code

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent claude-code --scope user
```

Invoke it with:

```text
/swift-cycle
```

### GitHub Copilot

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent github-copilot --scope user
```

Invoke it with:

```text
/swift-cycle
```

For project-only installation, replace `--scope user` with `--scope project`. See [agent compatibility](docs/compatibility.md) for platform behavior and manual installation paths.

## Example requests

```text
$swift-cycle Initialize a lightweight maintenance framework for this repository.
```

```text
$swift-cycle Review the current documentation boundaries and fix only meaningful drift.
```

```text
$swift-cycle Maintain this three-PR migration as a current milestone and dependency-ordered PR queue.
```

```text
$swift-cycle Close out this project, reconcile the docs, and extract reusable methodology.
```

Use the invocation syntax supported by your agent host.

## Language support

The skill responds and creates project documents in the user's language while preserving the repository's established terminology. English is the canonical instruction language; Simplified Chinese terminology and document conventions are included in [`references/zh-CN.md`](skills/swift-cycle/references/zh-CN.md).

## Repository layout

```text
skill_swift_cycle/
├─ skills/swift-cycle/
│  ├─ SKILL.md
│  ├─ agents/openai.yaml
│  └─ references/zh-CN.md
├─ docs/compatibility.md
├─ README.md
├─ README.zh-CN.md
├─ DESIGN.md
├─ AGENTS.md
└─ LICENSE
```

The skill follows the open [Agent Skills specification](https://agentskills.io/specification).

Words in the repository name are separated with `_`. The Skill package and invocation keep `swift-cycle` because the Agent Skills specification permits only lowercase letters, digits, and hyphens in Skill names.

## License

Swift Cycle is released under the [MIT License](LICENSE).
