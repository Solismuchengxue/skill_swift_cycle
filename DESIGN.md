# Swift Cycle Design

## Status

- Status: active.
- Current conclusion: maintain one standards-based, explicit-invocation Skill as a project-internal scenario router, proportional document configurator, and verification/learning loop. Keep organizational coordination outside the Skill.
- Scope: canonical workflow, document profiles, optional templates, language resolution, host compatibility, and source/deployment boundaries.
- Update trigger: revise this document when the Skill package, scenario routes, document profiles, language strategy, invocation policy, or supported host boundary changes.

## Goals

- Keep personal and small projects coherent without importing heavyweight organizational process.
- Preserve one portable workflow across Agent Skills-compatible hosts.
- Support English and Simplified Chinese without duplicating the full Skill body.
- Keep installation and invocation behavior explicit.
- Keep simple work minimal while giving complex project, runtime, and integration work a reusable document shape.
- Detect documentation drift and promote confirmed failure guards without creating a second project state machine.

## Structure

```text
skill_swift_cycle/
├─ skills/
│  └─ swift-cycle/
│     ├─ SKILL.md               # Canonical cross-agent workflow
│     ├─ agents/openai.yaml     # Codex interface and explicit-only policy
│     ├─ references/
│     │  ├─ zh-CN.md            # Simplified Chinese operational terminology
│     │  └─ document-profiles.md # Profile selection and document shape
│     └─ templates/             # Optional profile-aligned starting points
├─ docs/
│  └─ compatibility.md          # Host support and installation boundaries
├─ README.md                    # English user documentation
├─ README.zh-CN.md              # Simplified Chinese user documentation
├─ AGENTS.md                    # Repository maintenance rules
└─ LICENSE                      # MIT license
```

## System shape

Swift Cycle routes one project task through a short engineering loop and emits bounded evidence for any external coordinator:

```mermaid
flowchart LR
    Request[Project request] --> Inspect[Inspect real state]
    Inspect --> Route[Select scenario and profile]
    Route --> Package[Shape finite work package]
    Package --> Change[Implement smallest useful change]
    Change --> Verify[Verify proportionally]
    Verify --> Learn[Promote learning or revert]
    Learn --> Packet[Work package / Review Packet / Closeout Packet]
```

The diagram describes project-internal engineering. It does not assign departments, create reviewers, grant runtime authority, accept work, or operate an external registry.

## Document profiles

| Profile | Purpose | Boundary |
| --- | --- | --- |
| `minimal` | Core entry points and the shortest useful execution view | Default for small projects and bounded changes |
| `standard` | Durable architecture, roadmap, evaluation, and decisions | Add only authorities backed by long-lived facts |
| `runtime_integration` | Operations, contracts, security, storage, integration, and identity layers | Track only layers the project actually has |

Profiles are optional starting configurations. Templates are structural examples adapted to the resolved file language; they are never copied as a mandatory tree.

## Key boundaries

| Concern | Swift Cycle owns | Outside this Skill |
| --- | --- | --- |
| Project loop | Scenario, profile, finite work package, implementation, verification, learning | Portfolio routing, capacity, model assignment, external queues |
| Documentation | Responsibility, freshness, knowledge promotion, packet freeze and retirement | Organizational registry or acceptance ledger |
| Delivery layers | Independent source, artifact, runtime, and consumer evidence | Publishing, deployment, or consumer switching without separate authority |
| Output | Project work package, Review Packet, Closeout Packet | Acceptance, activation, release, or cross-project authorization decisions |

- Words in the project, repository, and root-directory names are separated with `_`; letter case follows the chosen project name. The standards-defined Skill identifier remains `swift-cycle` because underscores are not valid in Agent Skill names.
- `SKILL.md` contains the portable workflow and uses standard portable frontmatter fields, including the MIT license identifier.
- `agents/openai.yaml` contains Codex-specific interface metadata and disables implicit invocation for Codex.
- Other hosts use the same standard Skill package and their own installation conventions.
- Language behavior belongs in the canonical workflow. Conversation and file language resolve independently; localized references clarify terminology without copying the whole workflow, and existing bilingual entry points remain explicit repository choices.
- Scenario routing precedes profile selection. Bootstrap/adopt, small changes, features, bug fixes, research, runtime integration, closeout, and document retirement each define their minimum documentation action, verification strength, and stop condition.
- Document profiles are progressive. `minimal` remains the default, while `standard` and `runtime_integration` activate only for durable facts and delivery layers that exist.
- Optional templates encode one-H1 structure, stable H2 sections, native Mermaid, concise tables, unresolved items, update triggers, and revision records. They do not impose a prose language or mandatory directory tree.
- Knowledge promotion keeps short-lived capture local and moves durable commitments, decisions, constraints, and reusable evidence into responsibility-appropriate shared assets. After promotion, the shared asset is authoritative and the local record retains only a concise pointer.
- State separation identifies labels that combine independent lifecycle questions and splits only the concerns a project actually tracks. It defines no mandatory fields or status schema, and any overall status remains a derived summary.
- Governance baselines activate only for non-trivial work that crosses authority
  boundaries, changes source/runtime relationships, or needs reliable
  before/after comparison. A baseline separates observed and target state, uses
  no mandatory file or schema, and becomes shared evidence only when later work
  depends on it.
- Commit-boundary planning activates for multiple commits, mixed-purpose hunks,
  ordered dependencies, or independently reviewable history. Prefer one atomic
  commit when a split cannot preserve a coherent intermediate state.
- Source, artifact, runtime, and consumer state are optional independent layers.
  Evidence and authorization do not transfer between them, and projects track
  only the layers they actually have.
- Transition checks use canonical contracts and independently evidenced identities. Git source mode is not an installed permission, and tests must not share one incorrect derived authority with the manifest they claim to verify.
- Local `TODO.md` is the current execution view, not the durable source for
  cross-machine plans. Durable plans belong in a committable feasibility
  report, roadmap, or shared issue tracker.
- A normal TODO checklist remains the default. The current milestone and PR
  queue structure activates only for explicitly multi-PR or milestone-based
  work; each PR is an independently reviewable, verifiable, reversible
  increment executed in dependency order.
- Swift Cycle defines this portable PR-sized increment contract directly. It
  does not depend on Superpowers or reproduce plugin-specific mechanisms.
- Work may continue through listed, reversible steps under one unchanged authority without repeating internal approval prompts. Scope expansion, contradictory evidence, external side effects, or unsafe rollback stop the loop.
- Documentation freshness is event-driven. Milestone, decision, contract, runtime, or consumer changes trigger a focused reconciliation of status, pending work, unknowns, identities, indexes, and packets.
- Review Packets are dated or milestone-bound frozen snapshots. Closeout Packets summarize project evidence for an external loop; neither creates organizational acceptance, activation, release, or a second state machine.
- Confirmed reusable failures follow failure mode, cause, corrective assertion, and reusable gate. Unconfirmed one-off failures remain local.
- Repository maintenance details do not belong in the Skill package.
- Host-installed Skill copies and installer-added source metadata are deployment
  artifacts, not repository source. Moving or renaming this checkout does not
  authorize reinstalling, updating, or relinking an installed copy.
- No scripts, runtime dependencies, MCP servers, or external services are required.

## Language strategy

- Conversation and final-report language use the user's explicit request, then the current invocation language.
- Existing-file language uses the user's explicit request, the file's established primary language, the project language, then the invocation language.
- New-file language uses the user's explicit request, the project language, then the invocation language.
- A conversation-language change does not authorize bulk translation. Bilingual counterparts exist only when the project already maintains them or the user requests them.
- Preserve filenames, commands, APIs, code identifiers, standard status values, and repository terminology. Avoid accidental mixed-language prose.
- The current canonical Skill body is maintained in English for portability, but the workflow does not define English as the only valid project-document language. Load the Simplified Chinese reference when Chinese wording or document conventions are needed.

## Compatibility strategy

- Follow the open Agent Skills directory and `SKILL.md` format.
- Validate the package with both the OpenAI Skill validator and `gh skill publish --dry-run`.
- Keep strict explicit-only behavior in Codex metadata.
- Document host-specific manual-invocation controls instead of adding non-standard fields to the canonical frontmatter.

## Unresolved items

- No script is currently required. Mechanical checks remain a candidate only if stable structure or freshness failures cannot be caught reliably with existing validators and focused review.
- Installed Skill copies remain separately versioned deployment state and are not updated by source edits.

## Revision record

| Date | Change |
| --- | --- |
| 2026-08-30 | Added project-internal scenario routing, progressive document profiles, language resolution, freshness and packet lifecycle, proportional verification, and reusable learning boundaries. |
