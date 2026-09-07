# Agent compatibility

## Status

- Status: active.
- Current conclusion: distribute one Agent Skills-compatible package and use host-specific installation commands.
- Update trigger: recheck this document when Agent Skills paths, invocation syntax, or GitHub CLI support changes.

## Package format

The canonical package is `skills/swift-cycle/`. It contains a concise Simplified Chinese `SKILL.md`, references loaded only when their conditions apply, conditional document templates, and Codex-specific UI metadata.

The package follows the open [Agent Skills specification](https://agentskills.io/specification).

## Supported hosts

| Host | User-scope installation | First-party documented explicit invocation | Notes |
| --- | --- | --- | --- |
| Codex | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent codex --scope user` | ChatGPT desktop: select the Skill with `@`; Codex CLI / IDE extension: `$swift-cycle` | Package-relative `agents/openai.yaml` (repository path `skills/swift-cycle/agents/openai.yaml`) disables implicit invocation. |
| Claude Code | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent claude-code --scope user` | `/swift-cycle` | Claude Code supports filesystem-based Agent Skills. |
| GitHub Copilot | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent github-copilot --scope user` | Copilot CLI: `/swift-cycle`; no shared slash syntax is claimed for other surfaces | Copilot supports Agent Skills across multiple surfaces, but `/swift-cycle` is documented only for Copilot CLI. |

GitHub CLI supports additional agent hosts. Run `gh skill install --help` to inspect the currently supported `--agent` values rather than relying on a static list.

Invocation syntax is surface-specific. The installation commands install from the same canonical source package for each host; they do not imply byte-identical installed artifacts or one command syntax across every UI.

The `gh skill install` command form, agent values, and `--scope user` flag above are documented by the first-party manual and matched local GitHub CLI 2.96.0 help output on 2026-09-07. A real remote install was not authorized or run, so remote-install verification remains **NOT_VERIFIED**. Local authentication state is environment-specific and is not compatibility evidence.

## Invocation policy

Swift Cycle uses two explicit layers rather than semantic implicit invocation:

- **Host or system selection remains deliberate and explicit.** An unadopted project must not load Swift Cycle merely because a request resembles its workflow. Codex enforces this boundary with `allow_implicit_invocation: false` in package-relative `agents/openai.yaml` (repository path `skills/swift-cycle/agents/openai.yaml`).
- **Project adoption is one explicit action.** After adoption, the project's `AGENTS.md` may persistently require later project tasks to load the `swift-cycle` Skill. In Codex-facing instructions the identifier is written `$swift-cycle`; this is a repository binding, not a claim that ChatGPT desktop users invoke it with `$`.
- Claude Code supports direct `/swift-cycle` invocation, and Copilot CLI supports `/swift-cycle`. Other Copilot surfaces support Agent Skills, but this document does not claim that they expose the Copilot CLI slash syntax. Project-instruction, persistent-binding, and automatic-invocation behavior remains host-specific.

The host-specific field above is not included in the canonical package because the OpenAI validator intentionally accepts a narrower portable frontmatter set.

## Manual installation

If `gh skill` is unavailable, copy the complete `skills/swift-cycle/` directory into the host's supported project or user Skill directory. Do not copy only `SKILL.md`; keep referenced files and metadata together.

## First-party references

- [Agent Skills specification](https://agentskills.io/specification)
- [Build skills with Codex](https://learn.chatgpt.com/docs/build-skills)
- [Extend Claude Code with skills](https://code.claude.com/docs/en/slash-commands)
- [Add agent skills for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills)
- [GitHub Copilot CLI command reference](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference)
- [GitHub CLI `gh skill install` manual](https://cli.github.com/manual/gh_skill_install)
