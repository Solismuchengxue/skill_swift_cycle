# AGENTS.md

These instructions apply to the `skill_swift_cycle` repository.

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
- Keep knowledge-promotion and state-separation guidance project-agnostic and lightweight; do not encode project-specific workflows, mandatory state fields, or fixed status schemas.
- Keep scenario routes and document profiles progressive: `minimal` must remain usable without `standard` or `runtime_integration` artifacts.
- Keep Swift Cycle inside one project's engineering loop. Do not add portfolio routing, reviewer creation, capacity management, organizational acceptance, external registries, or cross-project runtime authorization.
- Treat templates as optional structures whose prose is adapted to the resolved file language. Do not create duplicate language-specific template trees.
- Keep the Blueprint as one shared tracked project-intent authority: new projects default to `docs/blueprint.md`, root-level Blueprint files are forbidden by default, and complete brownfield equivalents are mapped rather than copied.
- Keep Review Packets frozen and date- or milestone-bound; they must not become mutable current-truth documents.
- Do not add unsupported host claims; verify current behavior against first-party documentation.

## Language synchronization

- `README.md` is the English user entry point.
- `README.zh-CN.md` is the Simplified Chinese user entry point.
- Update both when installation, invocation, features, or repository layout changes.
- Update `skills/swift-cycle/references/zh-CN.md` when Chinese terminology or document responsibility changes.
- Do not duplicate the complete canonical Skill body into localized files.
- Do not define English as the only valid target-document language. Preserve the existing bilingual repository entry points while keeping conversation and file-language resolution in the canonical Skill.

## Validation

- Run the official OpenAI `quick_validate.py` against `skills/swift-cycle/`.
- Run `gh skill publish --dry-run` before publishing.
- Check Markdown links and `git diff --check`.
- Check the canonical Skill remains below 500 lines and each added template has one level-one heading.
- Check the Blueprint template has the stable required H2 sequence and assert the new-project docs path, brownfield equivalent reuse, tracked-asset boundary, and separation from README, DESIGN, TODO, DEVLOG, roadmap, Packets, runtime state, and Registry.
- Check new docs Markdown files and multiword directories use lowercase snake_case, the Blueprint default is `docs/blueprint.md`, and legacy renames require an approved documentation-hygiene package.
- Check scenario/profile coverage, language precedence, document-freshness triggers, Packet lifecycle, proportional evidence, and organizational boundary terms with focused assertions.
- Confirm local `TODO.md`, `DEVLOG.md`, and `METHODOLOGY.md` remain ignored.
- Report checks that were not run and do not claim unsupported compatibility.

## Source and deployment boundaries

- Treat `F:\70_Infrastructure_and_Operations\prompt_engineering\skill_swift_cycle` as the canonical
  source checkout. The previous source-path migration is complete, and retired
  migration-control paths are not current authority for this repository.
- Treat host-installed Skill copies and `gh skill` source metadata as external
  deployment state. Source changes do not authorize reinstalling, updating,
  relinking, or deleting an installed copy.

## Publishing

- Keep the default branch as `main`.
- Review the final diff before committing.
- Do not publish releases, change repository visibility, or add a license without explicit authorization.
