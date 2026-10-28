<!--
替换所有 {{变量}}，删除不适用的可选块及教学注释，再检查实际链接/图片/命令。
REPO_SLUG 使用真实 OWNER/REPO；没有公开 GitHub 仓库时删除徽章与 Star History。
图片、Release、许可或文档不存在时删除相关入口，不生成空壳或虚假状态。
LICENSE_STATUS 填真实许可状态；有实际许可文件时写“见许可证”并链接真实路径，LICENSE_PATH 用于对应徽章入口。
无许可文件时删除许可徽章与文件链接，正文仍保留许可状态；未知时写“许可尚未确定，暂无可引用的许可证文件”，已知外部条款则如实说明来源。
正文沿用目标文件语言；保留技术标识，标题图标仅是 README 展示约定。
影响使用的状态与限制须在首屏说明，必要操作不放进折叠块。
-->

<div align="center">

# {{PROJECT_NAME}}

**{{ONE_LINE_DESCRIPTION}}**

{{INTRO}}

<!-- 可选：存在正式 Release 和实际许可文件时保留对应徽章。 -->
[![Release](https://img.shields.io/github/v/release/{{REPO_SLUG}}?style=flat-square)](https://github.com/{{REPO_SLUG}}/releases)
[![License](https://img.shields.io/github/license/{{REPO_SLUG}}?style=flat-square)]({{LICENSE_PATH}})

[✨ 功能介绍](#features) ·
[🚀 快速开始](#quick-start) ·
[🎬 使用示例](#first-use) ·
[❓ 常见问题](#help)

</div>

<!-- 可选：真实净化截图、演示动图或结果预览；无实际图片时删除整个图片块。 -->
<p align="center">
  <img src="{{PREVIEW_IMAGE}}" alt="{{PREVIEW_ALT}}" width="900">
</p>

---

<a id="features"></a>

## ✨ 用途与适用范围

{{SCOPE}}

| 核心能力 | 能帮助你完成什么 |
| :--- | :--- |
| **{{FEATURE_1}}** | {{BENEFIT_1}} |
| **{{FEATURE_2}}** | {{BENEFIT_2}} |
| **{{FEATURE_3}}** | {{BENEFIT_3}} |

**适合：** {{AUDIENCE}}。
**不适合：** {{NON_GOALS}}。

## 🧰 准备条件

<!-- 只保留实际需要的行；不需要账户则删除对应行，秘密不得写入。 -->
| 项目 | 要求 |
| :--- | :--- |
| 运行环境 | {{ENVIRONMENT}} |
| 输入或材料 | {{INPUTS}} |
| 账户与权限 | {{ACCESS}} |

<a id="quick-start"></a>

## 🚀 安装或接入

### ⚡ 推荐方式

{{INSTALL_ROUTE}}

**执行位置：** {{WORKDIR}}
**执行环境：** {{SHELL}}

```text
{{INSTALL_COMMAND}}
```

**成功判断：** {{INSTALL_SUCCESS}}。

<details>
<summary>📦 其他安装方式（按需保留）</summary>

{{ALTERNATIVES}}

</details>

<a id="first-use"></a>

## 🎬 第一次使用

### 📥 1. 准备输入

{{SAMPLE_INPUT}}

### ▶️ 2. 执行任务

```text
{{RUN_COMMAND}}
```

### ✅ 3. 检查结果

```text
{{EXPECTED_OUTPUT}}
```

**成功时你会看到：** {{SUCCESS}}。

<!--
命令块换成实际 Shell/语言；首装与更新分别说明，命令须在声明环境可用。
图形界面可在这里加真实截图；CLI、库或 Skill 使用实际输入输出或调用例子。
仅为设计示例时明确未验证；未知不写成不适用，不伪造成功结果。
-->

<a id="help"></a>

## 🛠️ 日常使用与求助

### 📋 常用操作

| 想做什么 | 操作或入口 |
| :--- | :--- |
| {{ACTION_1}} | {{ENTRY_1}} |
| {{ACTION_2}} | {{ENTRY_2}} |
| 查看详细说明 | [{{DOC_LABEL}}]({{DOC_URL}}) |

### ❓ 常见问题

<details>
<summary>💡 {{QUESTION_1}}</summary>

**原因：** {{CAUSE_1}}。

**处理：** {{FIX_1}}。

</details>

<details>
<summary>💡 {{QUESTION_2}}</summary>

{{ANSWER_2}}

</details>

仍未解决？请通过 [{{SUPPORT_LABEL}}]({{SUPPORT_URL}})
反馈使用环境、复现步骤和经过脱敏的错误信息。

<!--
以下是按需参考，不是必建栏目；没有实际需要则删除，不新建空文档：
### 📡 接口参考
### 📁 项目结构
### 🧩 技术栈
简要介绍并链接既有详细说明，不把 README 写成完整开发手册。

确实涉及配置、更新或撤销安装时，在“限制与许可”前按顺序增补：
## ⚙️ 配置与数据
## 🔄 更新与迁移
## ⏸️ 暂停、恢复与卸载
必需操作和关键风险不能藏在折叠块中。
-->

## 📄 限制与许可

- **已知限制：** {{LIMITATIONS}}。
- **未验证范围：** {{UNVERIFIED}}。
- **许可证：** {{LICENSE_STATUS}}。

<!-- 仅公开 GitHub 仓库按需使用，无真实仓库则删除本节；启用后始终为最后一节。 -->

## ⭐ Star History

![Star History](https://api.star-history.com/svg?repos={{REPO_SLUG}}&type=Date)
