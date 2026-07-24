# 简体中文执行约定

当用户使用简体中文或要求输出中文项目文档时，使用本文件统一术语和表达。不要复制或重新解释完整的 `SKILL.md` 流程。

## 核心名称

- Swift Cycle：快速螺旋。
- Lightweight governance：轻量级治理或轻量维护框架。
- Scan quickly → smallest useful change → verify immediately → continue or revert：快速扫描 → 最小变更 → 立即验证 → 继续或回退。
- Candidate：候选方案。
- Controlled trial：受控试点。
- Adopted architecture：正式架构或已采用架构。
- Maintenance evidence：维护证据。
- Project closeout：项目尾声或项目收敛。

## 文档职责

- `README.md`：纯用户视角，只保留项目介绍、安装或启动方式、使用方法和用户确实需要知道的限制。
- `DESIGN.md`：简洁的设计总入口，说明目标、原则、整体结构、关键边界、正式架构和详细文档链接。
- `AGENTS.md`：项目规则、数据安全边界、文档同步规则和验证要求。
- `TODO.md`：当前行动、优先级、阻塞项和下一步；仅本地维护并由 Git 忽略。
- `DEVLOG.md`：踩坑、失败方案、内部判断、维护证据和演进过程；仅本地维护并由 Git 忽略。
- `docs/`：长期共享的需求、架构、运行手册、路线图、评估和 ADR。
- `METHODOLOGY.md`：只在项目尾声根据真实工作提炼，默认仅本地维护。

## 状态词

- planned：规划中。
- draft：草案。
- in progress：进行中。
- accepted：已接受。
- rejected：已拒绝。
- superseded：已被替代。
- archived：已归档。

## 表达边界

- 区分“已确认事实”“假设”和“推断”。
- 未验证时使用“候选”“规划中”或“待确认”，不要写成“已采用”或“已完成”。
- 小型、局部且明确的修改不要引入额外 RFC、ADR、设计书或大型流程。
- 需要删除、安装、连接外部服务或改变重要配置时，先说明影响并取得用户确认。

## 完成报告

使用简洁中文说明：

- 修改了什么；
- 为什么这样分层；
- 实际执行了哪些验证；
- 哪些共享文件仍未提交；
- 哪些内容仅保留在本地；
- 仍有哪些候选、风险或待确认项。
