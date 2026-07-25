# AGENTS.md

These instructions apply to the `swift_cycle` repository.

## Repository purpose

- Maintain one portable Agent Skill for lightweight project governance.
- Keep the canonical package under `skills/swift-cycle/`.
- Do not add scripts, dependencies, generated assets, or vendor-specific copies unless a verified compatibility requirement justifies them.

## Naming

- Separate words in project, repository, and project-root names with `_`; do not impose a letter-case rule beyond the chosen project name.
- Keep the standards-defined Skill identifier, package directory, and invocation as `swift-cycle`; Agent Skills names do not permit underscores.
- Treat external syntax constraints as explicit exceptions rather than changing the repository naming rule.

## Change rules

- Read `README.md`, `DESIGN.md`, the canonical `SKILL.md`, and relevant compatibility documentation before editing.
- Preserve user changes and keep each modification traceable to the current request.
- Prefer a small shared-core change over duplicated agent-specific implementations.
- Keep the Skill body concise, imperative, and below 500 lines.
- Do not add unsupported host claims; verify current behavior against first-party documentation.

## Language synchronization

- `README.md` is the English user entry point.
- `README.zh-CN.md` is the Simplified Chinese user entry point.
- Update both when installation, invocation, features, or repository layout changes.
- Update `skills/swift-cycle/references/zh-CN.md` when Chinese terminology or document responsibility changes.
- Do not duplicate the complete canonical Skill body into localized files.

## Validation

- Run the official OpenAI `quick_validate.py` against `skills/swift-cycle/`.
- Run `gh skill publish --dry-run` before publishing.
- Check Markdown links and `git diff --check`.
- Confirm local `TODO.md`, `DEVLOG.md`, and `METHODOLOGY.md` remain ignored.
- Report checks that were not run and do not claim unsupported compatibility.

## Publishing

- Keep the default branch as `main`.
- Review the final diff before committing.
- Do not publish releases, change repository visibility, or add a license without explicit authorization.
