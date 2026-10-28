<div align="center">

# Swift Cycle（快速螺旋）

**一次采用，持续维护单个项目的轻量工程循环。**

把项目意图、已确认需求、实施、验证和经验连接起来，让每次修改都有清楚的结果与下一步。

[![Release](https://img.shields.io/github/v/release/Solismuchengxue/skill_swift_cycle?style=flat-square)](https://github.com/Solismuchengxue/skill_swift_cycle/releases)
[![License](https://img.shields.io/github/license/Solismuchengxue/skill_swift_cycle?style=flat-square)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent_Skills-portable-2563eb?style=flat-square)](https://agentskills.io/specification)

[English](README.md) · [✨ 功能介绍](#features) · [🚀 快速开始](#quick-start) · [🎬 使用示例](#first-use) · [❓ 常见问题](#help)

</div>

> **版本说明：**本文介绍当前源码。下方固定安装命令使用已发布的 v1.4.0，不包含之后的初始化、模板、参考及 tmp/ 修订。源码、Release 和已安装副本分别管理，详见[版本与验证记录](docs/compatibility.md#fixed-version-delivery)。

---

<a id="features"></a>
<a id="为什么需要-swift-cycle"></a>
<a id="loop-engineering"></a>
<a id="ai-skill-能力"></a>
<a id="项目体现的工程能力"></a>
<a id="工作方式"></a>
<a id="共享事实与本地执行"></a>
<a id="治理边界"></a>
<a id="与任务规模相称的交付方式"></a>

## ✨ 用途与适用范围

Swift Cycle 是一个遵循 Agent Skills 规范的文档型 Skill。它先读取真实项目，再按任务规模选择最小改动、验证和文档同步，不为简单任务生成整套流程。

| 核心能力 | 能帮助你完成什么 |
| :--- | :--- |
| **项目采用与持续推进** | 明确采用一次后，在项目 AGENTS.md 绑定，后续直接提出项目任务 |
| **意图与需求分开** | BLUEPRINT 保留目标与构想，PRD 保留已确认行为与验收，不把所有设想变成承诺 |
| **进度与经验可读** | TODO 展示进度、里程碑位置、问题和下一阶段；DEVLOG 留有效结论与理由 |
| **按需文档模板** | 提供十份核心结构及可选 MANUAL/ADR；README 使用图标导航，DESIGN 使用概要结构与 UML |
| **逐包收敛** | 每个工作包完成实现、相称验证和受影响说明同步；发现新需求时调整后续安排 |
| **复用与轻量治理** | 先找已有能力，按真实职责组织代码；需要时才检查跨层身份、提交边界和文档新鲜度 |
| **临时材料集中存放** | 可写任务使用根级 tmp/ 并按 Git 策略忽略，减少可控的额外 C 盘临时写入 |
| **可移植与语言适配** | 共用一个规范包，正文按文件/项目语言处理，命令、路径和标准标识保持原文 |

**适合：**个人项目、小团队仓库、持续维护和边界明确的工程任务。

**范围之外：**组织级路由、容量管理、跨项目运行授权，以及未经批准的发布、安装、部署或删除。

### 🔁 短循环

```mermaid
flowchart LR
    A[读取真实状态] --> B[选择最小有效改动]
    B --> C[实施并同步说明]
    C --> D[立即验证]
    D --> E[继续或修正]
    E --> A
```

这就是循环工程（Loop Engineering）：让意图、执行、证据和经验在同一个短循环中保持一致。简单工作用普通 TODO，复杂阶段才用一份稳定编号的正式计划。

## 🧰 准备条件

| 项目 | 要求 |
| :--- | :--- |
| Agent 环境 | 支持 Agent Skills 的宿主；各宿主的调用语法和验证范围见[兼容说明](docs/compatibility.md) |
| 安装工具 | 使用安装命令时需要提供 gh skill 的 GitHub CLI；先运行 `gh skill install --help` 核对本机支持 |
| 项目材料 | 当前项目目录、已有执行规则、需求、设计和 Git 状态；缺失或未知内容如实说明 |
| 写入权限 | 维护时仅写获准项目；只读任务不创建目录、改忽略规则或写入记录 |
| 图示工具 | 新建或整篇重整 DESIGN 的架构图需要 Figma 可编辑源稿与 PNG/SVG；普通文字维护不因此要求 Figma |

Skill 本身没有运行脚本或依赖包。仅做本地阅读和维护不要求新增云端账户；外部工具与权限按实际任务决定。

<a id="quick-start"></a>
<a id="快速开始"></a>
<a id="codex"></a>
<a id="claude-code"></a>
<a id="github-copilot"></a>

## 🚀 安装或接入

### 💻 Codex 固定版本安装

**执行位置：**任意可运行 gh 的目录。**执行环境：**Windows PowerShell 7。

```powershell
gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --dir "$env:USERPROFILE\.agents\skills" --pin v1.4.0
```

**成功判断：**完整 Skill 位于用户级 .agents/skills/swift-cycle，并可在 `gh skill list` 中核对来源。ChatGPT 桌面版输入 `@`选择 **Swift Cycle / 快速螺旋**；Codex CLI/IDE 使用 `$swift-cycle`。

已有安装先保留原目录作为回退，再决定是否覆盖；只保留一个独立真实入口，避免旧 .codex/skills 副本或指向源码的 Junction 造成重复发现。更换版本和本仓库源码编辑不会自动更新安装。

### 📦 其他接入方式

| 场景 | 方式 |
| :--- | :--- |
| Claude Code | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent claude-code --scope user --pin v1.4.0`；调用 /swift-cycle |
| GitHub Copilot CLI | `gh skill install Solismuchengxue/skill_swift_cycle swift-cycle --agent github-copilot --scope user --pin v1.4.0`；调用 /swift-cycle，不外推其他界面 |
| Codex 仅项目安装 | 将上述 Codex 命令的 --dir 及其值替换为 --agent codex --scope project |
| 手动安装当前源码 | 复制完整 skills/swift-cycle/ 到宿主支持的 Skill 目录，保留参考、模板和元数据；先处理已有安装的备份与版本选择 |
| 维护本仓库源码 | 按[AGENTS.md](AGENTS.md#swift-cycle)读取仓库内规范入口；无需为了编辑文档先覆盖用户已安装 Skill |

手动安装路径、已安装来源与回退边界详见[兼容说明](docs/compatibility.md#manual-installation)。

<a id="first-use"></a>
<a id="交付循环示例"></a>

## 🎬 第一次使用

### 📥 1. 准备输入

打开一个已有项目，明确本次范围。第一次可从只读核对开始，不必先初始化文档树。

### ▶️ 2. 选择 Skill 并提出任务

在 ChatGPT 桌面版通过 `@`选择 Skill，再发送：

```text
只读检查当前项目的 README、DESIGN 和已有需求说明。
报告当前进度、发现的问题及下一步，不修改文件，不提交推送。
```

Codex CLI/IDE 可在同一请求前加 `$swift-cycle`。一次性检查不建立持久采用；需要持续维护时，再明确要求“采用 Swift Cycle，并在本项目 AGENTS.md 中绑定”。

### ✅ 3. 检查结果

应得到与实际文件对应的状态、问题、未验证范围和下一步，而不是声称创建了未授权的文档。此处是请求示例，不是新的宿主执行测试结果。

采用后直接发送普通项目任务；获准创建或正式初始化时，才要求有效交付根级 TODO.md 与 DEVLOG.md。已有有效记录保留，普通维护只同步受影响内容。

<a id="help"></a>
<a id="仓库结构"></a>

## 🛠️ 日常使用与求助

### 📋 常用操作与文档入口

| 想做什么 | 操作或入口 |
| :--- | :--- |
| 推进现有任务 | 说明目标、范围和保留项；先核对当前 TODO，再完成最小工作包及验证 |
| 接收新需求 | 先确认行为、验收和影响；完成阶段后的新增需求安排后续，不改写原完成范围 |
| 查看整体设计、目录树与 UML | [项目概要设计](DESIGN.md) |
| 选择文档、命名或记录策略 | [项目结构与文档规约](skills/swift-cycle/references/document-profiles.md) |
| 查同步时机与收口条件 | [需求与持续收敛](skills/swift-cycle/references/lifecycle-and-closeout.md) |
| 查看安装、版本和实际验证范围 | [兼容性与证据](docs/compatibility.md) |
| 维护此 Skill | [执行规则](AGENTS.md)、[源规约](docs/engineering_standard.md)、[规范入口](skills/swift-cycle/SKILL.md) |

### ❓ 常见问题

<details>
<summary>为什么装了 v1.4.0，却没有当前源码的新模板？</summary>

固定标签不会随 main 更新。按[交付记录](docs/compatibility.md#fixed-version-delivery)区分版本，需要新源码时明确选择来源并保留回退，不把编辑源码当作安装完成。

</details>

<details>
<summary>会为所有项目创建 ROADMAP、MANUAL 和整套模板吗？</summary>

不会。复用完整等价来源，只补真实职责。没有里程碑就如实说明；MANUAL、详细 SAD 和编号计划均按实际需要使用。

</details>

<details>
<summary>tmp/ 可以直接清空吗？</summary>

集中存放不授予删除权限。已有材料、受跟踪文件、用户数据和恢复点先核用途与授权；只读任务不创建或清理 tmp/。

</details>

仍有问题，请通过 [GitHub Issues](https://github.com/Solismuchengxue/skill_swift_cycle/issues)反馈宿主、Skill 来源/版本、复现步骤和脱敏错误，不附凭据或私人材料。

<a id="兼容性与边界"></a>
<a id="许可证"></a>

## 📄 限制与许可

- **验证范围：**包校验、源码断言、隔离样例、宿主发现及真实调用是不同证据层，具体日期和范围见[兼容记录](docs/compatibility.md)。本仓库自用绘图不证明其他项目、全新 Agent 或其他宿主都已采用。
- **外部工具：**架构图使用 Figma；完整 Superpowers 执行、其他宿主及长期行为不能由本地静态检查推导。
- **权限边界：**Skill 不授予发布、安装、部署、凭据、费用、删除或消费者切换权限；本地记录是否私有取决于实际 Git 策略。
- **许可证：**[MIT License](LICENSE)。安装器来源元数据属于安装副本，不写回规范源码。

## ⭐ Star History

[![Star History](https://api.star-history.com/svg?repos=Solismuchengxue/skill_swift_cycle&type=Date)](https://github.com/Solismuchengxue/skill_swift_cycle/stargazers)
