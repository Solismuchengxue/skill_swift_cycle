# Swift Cycle Design

## Status

- Status: active.
- Current conclusion: maintain one standards-based Skill and document host-specific installation instead of duplicating the workflow for each agent.
- Update trigger: revise this document when the Skill package, language strategy, invocation policy, or supported host boundary changes.

## Goals

- Keep personal and small projects coherent without importing heavyweight organizational process.
- Preserve one portable workflow across Agent Skills-compatible hosts.
- Support English and Simplified Chinese without duplicating the full Skill body.
- Keep installation and invocation behavior explicit.

## Structure

```text
skill_swift_cycle/
├─ skills/
│  └─ swift-cycle/
│     ├─ SKILL.md               # Canonical cross-agent workflow
│     ├─ agents/openai.yaml     # Codex interface and explicit-only policy
│     └─ references/zh-CN.md    # Simplified Chinese terminology
├─ docs/
│  └─ compatibility.md          # Host support and installation boundaries
├─ README.md                    # English user documentation
├─ README.zh-CN.md              # Simplified Chinese user documentation
└─ AGENTS.md                    # Repository maintenance rules
```

## Key boundaries

- Words in the project, repository, and root-directory names are separated with `_`; letter case follows the chosen project name. The standards-defined Skill identifier remains `swift-cycle` because underscores are not valid in Agent Skill names.
- `SKILL.md` contains the portable workflow and uses only standard required frontmatter fields.
- `agents/openai.yaml` contains Codex-specific interface metadata and disables implicit invocation for Codex.
- Other hosts use the same standard Skill package and their own installation conventions.
- Language behavior belongs in the canonical workflow; localized references clarify terminology without copying the whole workflow.
- Repository maintenance details do not belong in the Skill package.
- No scripts, runtime dependencies, MCP servers, or external services are required.

## Language strategy

- Use English for the canonical instructions so the package remains portable across hosts.
- Respond and generate documents in the user's language.
- Preserve terminology already established by the target repository.
- Load the Simplified Chinese reference only when Chinese wording or document conventions are needed.

## Compatibility strategy

- Follow the open Agent Skills directory and `SKILL.md` format.
- Validate the package with both the OpenAI Skill validator and `gh skill publish --dry-run`.
- Keep strict explicit-only behavior in Codex metadata.
- Document host-specific manual-invocation controls instead of adding non-standard fields to the canonical frontmatter.
