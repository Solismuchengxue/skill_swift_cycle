# Swift Cycle（快速螺旋）

[English](README.md)

Swift Cycle 是一个需要手动调用的 Agent Skill，用轻量文档框架和短验证循环维护个人项目与小型软件项目。

它遵循一个实用节奏：

> 快速扫描 → 最小变更 → 立即验证 → 继续或回退。

## 维护内容

- 纯用户视角的 `README.md`。
- 作为设计入口的简洁 `DESIGN.md`。
- `AGENTS.md` 等仓库级协作规则。
- 仅本地保存并由 Git 忽略的 `TODO.md` 与 `DEVLOG.md`。
- `docs/` 下需要长期共享的详细文档。
- 候选试验、评估证据和重要 ADR。
- 项目尾声的文档复核与方法论提炼。

简单、局部的修改保持轻量，不要求每次编辑都创建 RFC、ADR 或额外设计文档。

## 安装

GitHub CLI 2.90 或更高版本可以把同一份 Skill 安装给多个 Agent。

### Codex

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent codex --scope user
```

调用方式：

```text
$swift-cycle
```

### Claude Code

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent claude-code --scope user
```

调用方式：

```text
/swift-cycle
```

### GitHub Copilot

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent github-copilot --scope user
```

调用方式：

```text
/swift-cycle
```

如果只希望当前项目使用，把 `--scope user` 改为 `--scope project`。不同平台的行为和手动安装路径见[兼容性说明](docs/compatibility.md)。

## 使用示例

```text
$swift-cycle 为当前仓库建立轻量级维护框架。
```

```text
$swift-cycle 检查当前文档职责是否漂移，只修正确实有价值的问题。
```

```text
$swift-cycle 收敛项目文档，并从真实工作中提炼可复用方法论。
```

请根据所用 Agent 调整调用语法。

## 语言支持

Skill 会使用用户当前语言回答和创建项目文档，同时保留仓库已经采用的术语。英文是规范指令语言；简体中文术语和文档约定位于 [`references/zh-CN.md`](skills/swift-cycle/references/zh-CN.md)。

## 仓库结构

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
└─ AGENTS.md
```

本 Skill 遵循开放的 [Agent Skills 规范](https://agentskills.io/specification)。

仓库名中的多个单词使用 `_` 连接。Skill 包名和调用名继续使用 `swift-cycle`，因为 Agent Skills 规范只允许 Skill 名包含小写字母、数字和连字符。
