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
- Fixed professional document names are explicit file-name exceptions: docs/PRD.md, docs/SAD.md, docs/BLUEPRINT.md, docs/ROADMAP.md, docs/MANUAL.md and docs/milestones/M{N}_PLAN.md with stable positive N. Other ordinary docs files and multiword directories keep lowercase snake_case; preserve existing complete equivalents unless migration is authorized.

## Change rules

- Read `README.md`, `DESIGN.md`, the canonical `SKILL.md`, and relevant compatibility documentation before editing.
- Preserve user changes and keep each modification traceable to the current request.
- Prefer a small shared-core change over duplicated agent-specific implementations.
- Keep the Skill body concise, imperative, and below 500 lines.
- Keep knowledge-promotion and state-separation guidance project-agnostic and lightweight; do not encode project-specific workflows, mandatory state fields, or fixed status schemas.
- Keep scenario routes and document profiles progressive: `minimal` must remain usable without `standard` or `runtime_integration` artifacts.
- Keep Swift Cycle inside one project's engineering loop. Do not add portfolio routing, reviewer creation, capacity management, organizational acceptance, external registries, or cross-project runtime authorization.
- Treat templates as optional structures whose prose is adapted to the resolved file language. Do not create duplicate language-specific template trees.
- Keep the BLUEPRINT as one shared tracked project-intent authority: new projects default to `docs/BLUEPRINT.md`, root-level BLUEPRINT files are forbidden by default, and complete brownfield equivalents are mapped rather than copied.
- Keep any requested review snapshot frozen and date- or milestone-bound; it must not become a mutable current-truth document.
- Writable project tasks require a local root tmp/ directory and an effective /tmp/ ignore rule. Put new controllable temporary work there; retain existing ignored validation/history paths. Read-only tasks only inspect. Use tool arguments or child-process temporary settings to reduce extra C-drive writes, without changing global environment/cache settings or treating tmp contents as automatically disposable.
- Do not add unsupported host claims; verify current behavior against first-party documentation.

## Project governance

- Keep one project owner (`L1`) for this project; the former fixed reviewer is retired.
- Establish an independent reviewer only when the user, the department lead, or current project rules explicitly require one.
- This role adjustment does not grant Git push, publishing, deployment, runtime, credential, cost, or deletion authority.

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
- Check all ten core templates against the approved H2 sequences in `docs/engineering_standard.md`; professional outlines remain candidates. Assert vision/confirmed-requirements separation, the new-project BLUEPRINT path, brownfield reuse, tracked-asset boundary, and separation from current plans, runtime state, review snapshots, and Registry.
- For README presentation changes, validate Emoji H2/H3, unique explicit navigation anchors, the six core responsibilities plus optional last Star History, and absence of contribution/disclaimer sections. Ignore teaching headings inside HTML comments; only README output URL slots may defer local target resolution. Check public-GitHub and non-Git static instances, including licensed/no-license-file bodies with truthful status and no unsupported badge/file link, without weakening real-link checks or altering the other nine core templates.
- For TODO/DEVLOG presentation changes, check the four progress/milestone TODO H2 sections against the standard, problem/blocker/exit-condition coverage, and honest no-milestone use without forcing a ROADMAP document. Check compact DEVLOG list entries, optional real-milestone H3 grouping, no per-entry headings or Emoji, event-driven TODO synchronization, and the existing initialization/record-preservation boundaries. Keep source assertions separate from actual agent behavior.
- For DESIGN template changes, check the approved overview H2 sequence against the standard, the required real UML structure diagram for new/authorized whole-document restructuring, editable architecture sources plus PNG/SVG, and conditional UML views. Check an annotated text-code-block directory tree using actual paths, without forcing physical layout or replacing UML. Preserve small-edit/brownfield boundaries, concise interfaces/data/delivery summaries, capability navigation and refactor regression rules. Template placeholders and source assertions do not prove actual drawing/export, rendering or adoption.
- For reference consolidation, check the single document-profiles.md authority and approved six-section structure, repaired routes/fragment links, absence of active references to the retired file, and preservation of initialization preflight, naming, reuse/refactor and recovery rules. Preserve historical evidence and installed copies; source assertions do not prove agent adoption or runtime behavior.
- Check requirements-change routing, one numbered formal milestone plan, TODO scope, per-package convergence, and Figma editable-source/export/layout conditions with proportional scenario tests; distinguish static assertions, simulations, helper execution, and real adoption.
- Check fixed professional filenames and stable M-numbered plan exceptions exactly, including disk filename case. Other new docs Markdown files and multiword directories use lowercase snake_case; BLUEPRINT defaults to `docs/BLUEPRINT.md`, and legacy renames require an approved documentation-hygiene package. Keep SAD architecture and independent ADR decisions distinct; MANUAL remains optional operational guidance, and no default evaluation template/creation route remains.
- Check scenario/profile coverage, ordinary-content language precedence, exact technical-identifier preservation, semantic visualization choice and review, document-freshness triggers, review-snapshot lifecycle, proportional evidence, and organizational boundary terms with focused assertions.
- For template retirement, check removed files and active links/creation routes are absent, preserve historical evidence, and retain proportional review/delivery evidence without introducing replacement templates or mandatory reports. Keep docs-home and ADR-index templates retired while retaining conditional navigation, the standalone ADR decision template and its adoption/naming boundaries.
- For document-identity synchronization, compare all ten core H2 sequences directly with the source standard; check current filenames and depth-first/A–Z order across responsibility/conditional tables and bilingual entry points. Reject obsolete document labels in active guidance, while preserving generic domain terms, historical records and fixed external example paths.
- For root-tmp changes, check writable/adoption/initialization enforcement, read-only non-mutation, Git ignore and non-Git handling, existing-content/tracking/path conflicts, child-process-only redirection, uncontrollable-path disclosure and retention boundaries. Distinguish static guidance assertions, actual local directory/ignore/tool probes and fresh-agent/consumer execution.
- Confirm local `TODO.md`, `DEVLOG.md`, and `METHODOLOGY.md` remain ignored.
- For initialization-rule changes, check valid root TODO/DEVLOG delivery, exact new-Git ignore, repeat/partial preservation, empty/placeholder rejection, non-Git and non-initialization routes, and safe policy/I/O conflicts in owned isolated fixtures. Artifact checks do not replace actual agent execution; report those layers separately.
- For structure-governance changes, use bounded fictional reuse, responsibility/dependency/placement and behavior-preservation scenarios; do not refactor a consumer project or create a parallel capability ledger.
- Report checks that were not run and do not claim unsupported compatibility.

## Source and deployment boundaries

- Treat `F:\60_Infrastructure_and_Operations\02_Skills\skill_swift_cycle` as the canonical
  source checkout. The previous source-path migration is complete, and retired
  migration-control paths are not current authority for this repository.
- Treat host-installed Skill copies and `gh skill` source metadata as external
  deployment state. Source changes do not authorize reinstalling, updating,
  relinking, or deleting an installed copy.

## Publishing

- Keep the default branch as `main`.
- Review the final diff before committing.
- Do not publish releases, change repository visibility, or add a license without explicit authorization.
