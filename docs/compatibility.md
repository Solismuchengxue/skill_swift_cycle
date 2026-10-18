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
| Codex | PowerShell: `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --dir "$env:USERPROFILE\.agents\skills" --pin v1.4.0` | ChatGPT desktop: select the Skill with `@`; Codex CLI / IDE extension: `$swift-cycle` | Explicit user destination; package-relative `agents/openai.yaml` (repository path `skills/swift-cycle/agents/openai.yaml`) disables implicit invocation. |
| Claude Code | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent claude-code --scope user` | `/swift-cycle` | Claude Code supports filesystem-based Agent Skills. |
| GitHub Copilot | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent github-copilot --scope user` | Copilot CLI: `/swift-cycle`; no shared slash syntax is claimed for other surfaces | Copilot supports Agent Skills across multiple surfaces, but `/swift-cycle` is documented only for Copilot CLI. |

GitHub CLI supports additional agent hosts. Run `gh skill install --help` to inspect the currently supported `--agent` values rather than relying on a static list.

Invocation syntax is surface-specific. The installation commands install from the same canonical source package for each host; they do not imply byte-identical installed artifacts or one command syntax across every UI.

The `gh skill install` command form, agent values, and `--scope user` flag were documented by the first-party manual and matched local GitHub CLI 2.96.0 help output on 2026-09-07. On 2026-10-17, local help also confirmed that `--dir` overrides `--agent` and `--scope`; the current Codex command explicitly selects the documented user `.agents/skills` root. For project-only Codex installation, replace that `--dir` argument with `--agent codex --scope project`. The later Codex remote-install check is recorded below; Claude Code and Copilot installations remain **NOT_VERIFIED**. Local authentication state is environment-specific and is not compatibility evidence.

## Invocation policy

Swift Cycle uses two explicit layers rather than semantic implicit invocation:

- **Host or system selection remains deliberate and explicit.** An unadopted project must not load Swift Cycle merely because a request resembles its workflow. Codex enforces this boundary with `allow_implicit_invocation: false` in package-relative `agents/openai.yaml` (repository path `skills/swift-cycle/agents/openai.yaml`).
- **Project adoption is one explicit action.** After adoption, the project's `AGENTS.md` may persistently require later project tasks to load the `swift-cycle` Skill. In Codex-facing instructions the identifier is written `$swift-cycle`; this is a repository binding, not a claim that ChatGPT desktop users invoke it with `$`.
- Claude Code supports direct `/swift-cycle` invocation, and Copilot CLI supports `/swift-cycle`. Other Copilot surfaces support Agent Skills, but this document does not claim that they expose the Copilot CLI slash syntax. Project-instruction, persistent-binding, and automatic-invocation behavior remains host-specific.

The host-specific field above is not included in the canonical package because the OpenAI validator intentionally accepts a narrower portable frontmatter set.

## Manual installation

If `gh skill` is unavailable, copy the complete `skills/swift-cycle/` directory into the host's supported project or user Skill directory. Do not copy only `SKILL.md`; keep referenced files and metadata together.

For Codex user scope, use one independent real directory at `$HOME/.agents/skills/swift-cycle`, as documented in [Build skills with Codex](https://learn.chatgpt.com/docs/build-skills). An authorized migration of an existing fixed installation copies that installed directory, including its installer metadata, rather than rebuilding it from current source. Validate the new copy before recoverably removing the exact legacy `.codex/skills/swift-cycle` entry; do not leave a duplicate or source Junction, and preserve unrelated backups.

## First-party references

- [Agent Skills specification](https://agentskills.io/specification)
- [Build skills with Codex](https://learn.chatgpt.com/docs/build-skills)
- [Extend Claude Code with skills](https://code.claude.com/docs/en/slash-commands)
- [Add agent skills for GitHub Copilot](https://docs.github.com/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills)
- [GitHub Copilot CLI command reference](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference)
- [GitHub CLI `gh skill install` manual](https://cli.github.com/manual/gh_skill_install)

## Local source and optional helper checks (2026-10-13)

The approved [r29 source standard](engineering_standard.md) is implemented and passed D60 local-source acceptance. Publication and installation are tracked separately below. Architecture diagrams conditionally require Figma editable sources and PNG/SVG exports; package validation does not verify Figma access, drawing quality or actual project adoption. No new host support is inferred.

Installed Superpowers **6.4.2** was inspected without editing it. An ignored local fixture used Git Bash on Windows to exercise the real task-brief, task-start, sdd-workspace and task-done helpers:

- Four helpers passed Bash syntax checks; this is not Linux target compatibility.
- Task 1 and Task 10 were extracted independently; headings inside a code fence did not change task boundaries.
- A W-only table and a missing task returned exit 3 (negative controls).
- The first brief omitted global constraints; the final brief retained subsequent overall verification/risk/status sections. Execution must read the formal plan and its source requirements, not the brief alone.
- task-start reported the unchanged HEAD as BASE. A failing check (exit 7) did not record completion; a successful extraction check appended the fixture task result in the ignored workspace. This proves helper handoff only, not a business task or milestone result.
- Git Bash was blocked by sandbox MSYS initialization, then ran through the approved host channel. A test-harness POSIX-to-Windows path error was corrected; the third-party plugin was not changed.

The sole formal plan remains the numbered milestone plan. `Task N` technical headings can coexist with Chinese H2 sections, but an ordinary W table is not directly compatible with this parser. See [integration conditions](../skills/swift-cycle/references/superpowers-bridge.md).

**NOT_VERIFIED:** full writing-plans/SDD/native execution workflows, worktree and review lifecycle, commit-based completion, resumability across sessions, Figma drawing/export, real cross-project adoption and target-host use. Those optional helper checks did not publish or install the Skill.

## Fixed-version delivery

On 2026-10-13, the separately authorized r29 delivery published [v1.4.0](https://github.com/Solismuchengxue/skill_swift_cycle/releases/tag/v1.4.0), a stable non-draft Release targeting source commit `ef184206977517171649081b55ae1bdce3e002ba`. Git over SSH verified the remote commit and tag. Existing tags, including `v1.3.2`, were not moved. Subsequent delivery-status documentation does not alter the tagged Skill package, whose Git tree is `e0e5a6affa15da61a7a043a79ca295d42d104496`.

- **Source:** seven focused static check groups, 31 Markdown files / 54 local links, OpenAI quick_validate, `gh skill publish --dry-run` and Git whitespace checks passed. Source-only `engineering_standard.md`, local records and verification helpers are not installed.
- **Codex installation:** the official installer helper downloaded the fixed tag into an isolated verification directory. `gh skill install` then updated only the existing Codex user-scope `swift-cycle` with `--pin v1.4.0 --force`. The installed copy remains an ordinary directory, not a source Junction. Its 26-file set matches the tag: 25 non-manifest files match byte-for-byte; the Skill body and portable frontmatter match, and installer-only repository/path/tag/tree metadata is correct. The installed validator passed, implicit invocation remains disabled, and no installer metadata entered the source checkout. `gh skill list` reports pinned `v1.4.0`.
- **Native discovery:** Codex `0.162.0-alpha.17.2`, through a temporary native stdio process using read-only `skills/list` with `forceReload`, found exactly one enabled `swift-cycle` user Skill at the installed path, with the new r29 descriptor and `Swift Cycle / 快速螺旋` display name. The existing daemon proxy could not connect; no daemon or configuration repair was performed. That discovery check did not verify desktop selection or actual task invocation; the separate follow-up is recorded below. No new chat or model task was created by the discovery probe.
- **Rollback:** before replacement, the old ordinary directory was copied outside discovered Skill roots. Its 20 files, Skill body and pinned `v1.3.2` metadata were verified against the old tag. An isolated restore copy matched all 20 backup file hashes and passed package validation; the active installation was not switched back. The local backup and guarded restore entry remain available. Other users must preserve their own installed copy before replacement; `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent codex --scope user --pin v1.3.2 --force` is the remote fixed-version rollback alternative after checking the destination is an independent real directory.

The 2026-10-13 desktop explicit-entry and actual read-only invocation trial passed independent D60 acceptance. The user directly confirmed selecting Swift Cycle in the existing owner chat and submitted a real Skill reference bound to the installed v1.4.0 manifest. The owner loaded that installed package and completed the bounded responsibility, status and reference review of `README.zh-CN.md`, `DESIGN.md` and `docs/engineering_standard.md`. All seven before/after file hashes matched; 14 local links and relevant anchors passed. Existing changes were preserved, and no template tree or report was generated. The old `conformance` directory comment was noted, not repaired.

Desktop selection evidence is the user's confirmation, not an automated screenshot or full UI automation test. Read-only app/window enumeration had identified the target as ChatGPT, so the Computer Use automation prohibition remained respected. The agent performed no automated window capture, activation, click or input, and made no restart, reinstall or configuration repair. External links were not individually checked; cross-project adoption, full Superpowers/Figma execution, other hosts and long-term behavior remain **NOT_VERIFIED**. The completed invocation trial wrote no files; subsequent, separately scoped record maintenance updates existing status documents and must not be described as having no writes.

D60 independent acceptance of the earlier bounded release, installation and rollback delivery passed on 2026-10-13, with no blocking corrections. That earlier acceptance alone did not establish desktop selection or actual invocation; the later limited trial above has its own evidence and acceptance. Neither result establishes real-project or organization-wide adoption, Figma drawing/export, full Superpowers execution, long-term use or other-host installation. Newly installed skills are available on the next turn; if the selector does not refresh, follow the [official Skill guidance](https://learn.chatgpt.com/docs/build-skills) and restart Codex when convenient.

## Current Codex installation entry (2026-10-17)

The existing fixed v1.4.0 installation was copied unchanged from the legacy user root into `$HOME/.agents/skills/swift-cycle`: all 26 files / 58,587 bytes matched by per-file SHA-256, including installer metadata. The package ID, display name, disabled implicit-invocation policy and absent dependency declaration were preserved. OpenAI quick_validate and YAML checks passed. This was an installation-path migration, not a functional upgrade or a new Release.

Before cleanup, a temporary native Codex `0.163.0-alpha.10.2` stdio process found the new enabled path. After the exact legacy directory was sent to the Windows Recycle Bin, read-only `skills/list` with `forceReload` found exactly one enabled `swift-cycle` at the new path in each of two local project contexts, with no discovery errors. No extra discovery roots or configuration overrides were supplied; both temporary processes closed normally. Other rollback material was retained. The source repository and package were not moved or renamed, and no global configuration was changed. This does not verify a full desktop restart, selector refresh, actual task invocation at the new path, other hosts or long-term behavior.

The dated 2026-10-13 commands above describe that original delivery, not the current installation destination. For a current remote rollback, first preserve the active directory outside discovered roots and verify that the destination is an independent real directory, then use PowerShell:

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --dir "$env:USERPROFILE\.agents\skills" --pin v1.3.2 --force
```

Alternatively restore only a verified backup into `.agents/skills/swift-cycle`; do not recreate the legacy discovery entry. Neither rollback alternative was executed during this path migration.

## Source-only initialization and structure revision (2026-10-18)

The approved increment makes valid root TODO.md and DEVLOG.md an initialization completion condition, separates initialization from mere adoption/maintenance, and adds bounded reuse, responsibility/dependency, capability navigation and behavior-preserving refactor guidance. At the 2026-10-18 source-only closeout, this was an uncommitted source revision on the r29 baseline, not an installed or published update. Historical r29 acceptance and v1.4.0 delivery above remain historical; the separately approved local installation is recorded below.

The pre-edit missing-record negative fixture was rejected as expected; this checks the artifact oracle, not an independently replayed old-agent failure. The existing seven static check groups and OpenAI quick_validate passed; the ten core template H2 sequences are unchanged. The checks covered 31 Markdown files and 60 local Markdown links; local anchors were additionally checked. These are static results, not behavior or host compatibility claims.

The current agent read the revised source instructions, made case-specific decisions, authored missing records directly and read back the resulting artifacts in 13 owned temporary subscenarios:

| Subscenarios | Observed result |
| --- | --- |
| A: new Git record initialization; B: existing/repeated initialization | Valid root records; A had actual exact ignore and untracked checks. A/B each had two repeat readbacks with identical artifact bytes and no duplicate ignore or date copies. |
| C: only TODO missing; only DEVLOG missing | Only the missing file was added; the other file's SHA-256 was unchanged. |
| D: empty file; teaching placeholder | Both were rejected as incomplete; existing bytes were preserved, not overwritten. |
| E: non-Git record initialization | Valid root records; no `.git` or `.gitignore` was created; Git checks were not applicable. |
| F: read-only; ordinary maintenance; adoption only | No record creation or ignore changes. Maintenance changed only its intended README text; adoption changed only its binding. |
| G: confirmed-policy conflict; safe I/O substitute | Both remained incomplete without policy, permission or existing-content changes. The I/O substitute used a directory at the TODO path, not a real ACL modification. |
| H: bounded fictional structural change | Located the existing parser, caller and tests; added a thin second entry by reuse, documented responsibility/dependency/placement and capability links. Three normal/failure/cross-entry regression tests passed; the original parser and caller behavior were retained. |

All 13 subscenarios met their expected outcomes, including four expected incomplete cases; no unresolved validation failure or skipped subscenario remained. The missing-record and missing-entry negative controls detected their intended absence. Artifact scripts only inspected results; no template-copy initializer or new persistent helper was added to the package. These results cover isolated local-record initialization and bounded structural guidance, not complete product initialization. They are not independent fresh-agent pressure repetitions or actual Skill invocation through a host.

Only the owned temporary Git fixture had a successful `git init`; the source repository had no Git writes, staging or commits. The installed 26-file copy was read-only compared before/after and remained unchanged. No host discovery/invocation, install, publish or publish dry-run, global configuration, business service or consumer-project operation was performed. Historical release/installation results above do not validate this unpublished increment.

## Local accepted-source installation and fresh initialization (2026-10-19)

The current increment received independent D60 source-only acceptance (`PASS`, no issues), distinct from historical r29 acceptance. A later explicit user authorization covered updating only the existing local Skill and testing a new isolated project; no Git commit, publication or consumer-project change was included.

The existing real directory at `$HOME/.agents/skills/swift-cycle` had 26 files / 58,587 bytes with v1.4.0 metadata and no additional files or local configuration differences. Its exact original bytes were backed up outside discovered roots. A local-only `gh skill install --from-local` probe supplied the normal local-path metadata; the active directory was then updated in place from that verified payload, without deleting or moving the entry. Nine files changed and seventeen, including `agents/openai.yaml`, retained their original bytes. The package remains explicit-only, with no dependency declaration or global configuration change. The retired `.codex` entry was not recreated; historical backups were not cleaned.

The result contains 26 files / 64,401 bytes. All 25 non-manifest files match the accepted canonical package byte-for-byte. SKILL.md has the same body and portable frontmatter, plus installer-local `metadata.local-path`; GitHub pinned/ref/tree/repository fields were removed rather than misrepresenting this unpublished content as v1.4.0. `gh skill list --dir` reports the local source, `pinned=false`, and an empty version. This is a mutable local-source installation, not a new commit, tag or Release.

Content SHA-256 digests of the saved per-file manifest sequences (relative name, byte count, lowercase file SHA-256, tab-delimited with LF; entry order retained in the verification manifests):

| Object | Digest |
| --- | --- |
| Original installation and exact backup | `c843a11faebfa6edadc77cad6bb43ab3ad658531940a7c55731b5f75a3adb314` |
| Accepted canonical package | `6e5bd6275dce94ed923e2e7b22b080ae94709ef8d5e073bfc698c742f7fda7c2` |
| Updated installation, including local metadata | `f36e79a3b55bd8d3bb0ead99c766c4da5dbec415b9c2123230b40523970378df` |

The agent explicitly loaded the updated installed manifest, relevant references and minimal templates, then authored a fresh, initially empty, non-Git fictional card-ordering documentation project. It created seven actual documents: README, AGENTS, DESIGN, docs/blueprint, docs/requirements, root TODO and DEVLOG. TODO contains the project's real current goal, executable card-check actions, no-blocker statement and next step; DEVLOG records the actual non-Git/manual-first decision and its reason. No old A–H records or template-copy initializer were used. Two repeat readbacks preserved all seven file hashes without resets, appended entries or date copies. Git checks were not applicable and no Git repository was created.

Source and installed OpenAI package validation both passed. Seven existing source-check groups passed (31 Markdown files / 62 local links). Twelve read-only installation/project/boundary tests passed with zero failures or skips, checking the 26-file backup/payload, provenance, preserved configuration, 25 installed Markdown files / 30 local links, seven project Markdown files / 14 local links, headings, meaningful record content, binding and repeat preservation. The temporary PowerShell control script passed the syntax/encoding gate; optional PSScriptAnalyzer was not run in fast mode. An initial temporary installer probe hit sandbox directory access restrictions; the precisely approved host channel completed it without ACL changes.

This demonstrates actual initialization by the existing agent using the updated installed files, plus separate artifact assertions. It does not establish independent fresh-agent behavior, automatic host discovery/selection/invocation, application runtime, actual ACL-failure handling, production or long-term reliability. The exact backup, per-file manifests, guarded restore entry and new project were retained in the owned temporary workspace; actual rollback was not executed. Source instructions/templates, source HEAD and empty staging were preserved. No source Git write, publishing/dry-run, Podcast, browser, service or global-setting operation was performed. Future turns can use the updated files; selector refresh was not tested.
