# Agent compatibility

## Status

- Status: active.
- Current conclusion: distribute one Agent Skills-compatible package and use host-specific installation commands.
- Update trigger: recheck this document when Agent Skills paths, invocation syntax, or GitHub CLI support changes.

## Package format

The canonical package is `skills/swift-cycle/`. It contains a required `SKILL.md`, an optional localized reference, and Codex-specific UI metadata.

The package follows the open [Agent Skills specification](https://agentskills.io/specification).

## Supported hosts

| Host | User-scope installation | Manual invocation | Notes |
| --- | --- | --- | --- |
| Codex | `gh skill install Solismuchengxue/swift-cycle swift-cycle --agent codex --scope user` | `$swift-cycle` | `agents/openai.yaml` disables implicit invocation. |
| Claude Code | `gh skill install Solismuchengxue/swift-cycle swift-cycle --agent claude-code --scope user` | `/swift-cycle` | Claude Code supports filesystem-based Agent Skills. |
| GitHub Copilot | `gh skill install Solismuchengxue/swift-cycle swift-cycle --agent github-copilot --scope user` | `/swift-cycle` | Copilot supports the Agent Skills format and GitHub CLI installation. |

GitHub CLI supports additional agent hosts. Run `gh skill install --help` to inspect the currently supported `--agent` values rather than relying on a static list.

## Invocation policy

Swift Cycle is designed for deliberate, manual use.

- Codex enforces manual invocation through `agents/openai.yaml`.
- The canonical description tells other agents to use the Skill only after explicit user invocation.
- Claude Code and GitHub Copilot also support `disable-model-invocation: true` in their local Skill frontmatter when a user needs host-enforced manual-only behavior. This host-specific field is not included in the canonical package because the OpenAI validator intentionally accepts a narrower portable frontmatter set.

## Manual installation

If `gh skill` is unavailable, copy the complete `skills/swift-cycle/` directory into the host's supported project or user Skill directory. Do not copy only `SKILL.md`; keep referenced files and metadata together.

## First-party references

- [Agent Skills specification](https://agentskills.io/specification)
- [Build skills with Codex](https://learn.chatgpt.com/docs/build-skills)
- [Extend Claude Code with skills](https://code.claude.com/docs/en/slash-commands)
- [Add agent skills for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills)
