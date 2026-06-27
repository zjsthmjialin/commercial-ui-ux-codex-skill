# 商业 UI/UX/GUI 设计 Skill 文档包

本项目把 `commercial_ui_ux_architecture_guide.md` 中的商业界面设计思想，整理成一套更适合 Codex 调用、维护和迭代的 skill 文档。

这套文档的目标不是把模型变成“会写 Tailwind 的提示词复读机”，而是让 Codex 在设计、评审或实现 UI/UX/GUI 时，始终先理解业务场景、用户任务、交互风险和既有设计系统，再输出可验证的界面方案。

## P5-RC 决策与 P6 路线

当前项目已完成 P4 收束审计和最终文档一致性维护：P0-P4 已完成。P5-RC 三轮证据恢复也已完成，但当时不是正式发布。P6-H1/H2/H3 证据组达标后，项目已补充候选版本 `0.1.0-rc.1`、`CHANGELOG.md`、发布准备记录、发布包清单和本地发布记录；本地核心包已生成在 `output/release/commercial-ui-ux-0.1.0-rc.1.zip`，并包含中文公开说明 `README.zh-CN.md`。公开核心包已推送到 GitHub：`https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill`，并已创建 `0.1.0-rc.1` GitHub prerelease：`https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill/releases/tag/0.1.0-rc.1`。当前未公开完整项目源码、未创建最终非 RC 版本。发布决策见 `docs/14-p5-rc-release-decision.md`，发布准备见 `docs/16-public-release-preparation.md`，发布包边界见 `docs/17-release-package-checklist.md`，本地发布记录见 `docs/18-local-release-record.md`。

后续按 P6 通用正式版补强路线推进，路线图见 `docs/15-public-general-release-roadmap.md`。P6 采用“继续朝通用正式版补强”的方案 A；P6-H1 已完成一轮通用任务建模证据恢复，delta `+22`；P6-H2 已完成一轮既有系统修复证据恢复，delta `+34`；P6-H3 已完成一轮风险状态泛化证据恢复，delta `+30`。P6-H1/H2/H3 作为预声明证据组的平均 delta 约为 `+28.7`，达到公开正式版证据门槛，可以恢复发布准备，但不等于自动打包或上传。四轮历史独立复测、三轮 P5-RC 和 P6-H1/P6-H2/P6-H3 原始产物仍是审计证据；`output/` 与阶段性交接文档是生成物或历史记录，不属于核心 skill 使用路径。

## 文件结构

普通 UI 工作优先读取这些文件：

| 类别 | 文件 |
| --- | --- |
| Skill 入口 | `SKILL.md`、`SKILL.zh-CN.md` |
| 使用与规则 | `docs/05-usage-guide.md`、`docs/01-commercial-ui-ux-rules.md`、`docs/06-quality-gates.md` |
| 边界与宪法 | `docs/02-skill-boundaries.md`、`docs/03-design-constitution.md` |
| 按需视觉和行业上下文 | `docs/07-visual-strategy-inference.md`、`docs/09-industry-taxonomy.md`、`docs/10-industry-template-library.md` |

维护、治理和评测准备时再读取这些文件：

| 类别 | 文件 |
| --- | --- |
| 来源与进度 | `docs/00-source-analysis.md`、`docs/04-progress-plan.md` |
| 独立复测协议 | `docs/08-independent-evaluation-protocol.md` |
| 交接与决策记录 | 当前接续入口：`docs/13-handoff-consolidation-next-thread.md`；P5-RC 发布决策：`docs/14-p5-rc-release-decision.md`；P6 路线：`docs/15-public-general-release-roadmap.md`；发布准备：`docs/16-public-release-preparation.md`；发布包清单：`docs/17-release-package-checklist.md`；本地发布记录：`docs/18-local-release-record.md`；历史记录：`docs/11-handoff-next-thread.md`、`docs/12-handoff-p4-rendered-layout.md` |

数据、展示和历史证据按需查看：

| 类别 | 文件 |
| --- | --- |
| 评测与触发数据 | `evals/evals.json`、`evals/trigger-cases.json` |
| 行业数据 | `evals/industry-taxonomy.json`、`evals/industry-templates.json` |
| 展示与复测证据 | `showcase/`、`validation/independent-evaluation/` |

验证脚本按维护任务分类使用；全量入口是 `scripts/validate-all.ps1`。

| 类别 | 脚本 |
| --- | --- |
| 文档与治理 | `scripts/validate-skill-docs.ps1`、`scripts/validate-doc-structure.ps1`、`scripts/validate-doc-links.ps1`、`scripts/validate-governance.ps1`、`scripts/validate-text-hygiene.ps1` |
| 数据与触发 | `scripts/validate-evals.ps1`、`scripts/validate-trigger-cases.ps1`、`scripts/validate-industry-taxonomy.ps1`、`scripts/validate-industry-templates.ps1` |
| 展示页与 HTML | `scripts/validate-showcase.ps1`、`scripts/validate-showcase-a11y.ps1`、`scripts/validate-html-workflow-quality.ps1`、`scripts/validate-html-rendered-layout.ps1`、`scripts/validate-html-dom-interaction-quality.ps1` |
| 独立复测证据 | `scripts/validate-independent-evaluation.ps1`、`scripts/export-independent-evaluation.ps1`、`scripts/validate-independent-evaluation-export.ps1`、`scripts/validate-independent-evaluation-naturalness.ps1`、`scripts/generate-independent-evaluation-report.ps1`、`scripts/validate-independent-evaluation-report.ps1` |

## 推荐使用方式

普通 UI 工作路径：

1. 用 `SKILL.md` 作为 Codex skill 入口，只按任务需要读取相关 `docs/`。
2. 真实 UI 任务先用 `docs/05-usage-guide.md` 收集背景，再按 `docs/01-commercial-ui-ux-rules.md` 和 `docs/06-quality-gates.md` 执行。
3. 无品牌规范或参考图时读取 `docs/07-visual-strategy-inference.md`；只有行业线索时再读取 `docs/09-industry-taxonomy.md` 和 `docs/10-industry-template-library.md`。
4. `docs/04-progress-plan.md`、`docs/08-independent-evaluation-protocol.md`、`evals/`、`validation/` 和 `output/` 不进入普通 UI 任务的默认读取路径。

维护与验证路径：

1. 修改核心文档结构、路径或治理边界后，运行 `scripts/validate-doc-structure.ps1`、`scripts/validate-doc-links.ps1` 和 `scripts/validate-governance.ps1`。
2. 修改入口、触发边界、行业分类或模板数据后，运行对应的 skill、trigger、taxonomy、template 验证脚本。
3. 修改展示页或本地 HTML 原型后，再运行 showcase、a11y、workflow、rendered-layout 和 DOM interaction 验证脚本。
4. 独立复测材料只在有新假设时更新；P5-RC 的 H1-H3 三轮针对性证据工作，以及 P6-H1 通用任务建模、P6-H2 既有系统修复、P6-H3 风险状态泛化证据恢复已完成。
5. 上传前统一运行 `scripts/validate-all.ps1`。P6 证据组已恢复发布准备资格，候选 changelog、版本号、打包边界和本地核心包已补齐；公开核心包已在用户明确授权后推送到 GitHub。

## 当前状态

这是文档与 skill 入口的 P6 通用正式版补强阶段。它已经包含可执行规则、边界、验收标准、视觉策略自动推断模式、行业分类矩阵、行业模板库、评测草案、独立复测协议和行业 UI/GUI 样例。当前已完成三个 POC、两套展示页、18 个顶层行业和 54 个典型 UI/GUI 场景。P1 已完成四轮独立复测：第一轮 delta `+1`，第二轮 delta `0`，第三轮交叉评分 delta `+2`，第四轮自然复测交叉评分 delta `+1`，均未达到协议建议的 `+25` 显著改善门槛。P1 当时结论是证据不足：在明确 rubric、强约束和高能力 baseline 条件下，baseline 也能产出高覆盖原型。

P4 收束完成审计和最终一致性维护已完成：现有工具分层、普通 UI 路径、维护/评测路径、历史证据保护和全量验证入口已经对齐。P5-RC 已按 H1-H3 完成三轮针对性复测，用于验证 skill 是否能在简报不完整、既有产品修复、受保护操作硬状态三类更有区分度的任务中带来可观察增益。P5-RC 整体未通过发布门槛，因此 P5-RC 阶段不打包、不创建远程仓库、不推送、不上传 GitHub。

P5-RC 当前结果：RC-01（H1）delta `+11`，RC-02（H2）delta `+10`，RC-03（H3）delta `+30`。RC-03 单轮达到 `+25` 门槛，但三轮平均 delta 约 `+17`，仍未达到 P5-RC 发布通过标准。P6-H1 当前结果：baseline `76/100`，with-skill `98/100`，delta `+22`；P6-H2 当前结果：baseline `64/100`，with-skill `98/100`，delta `+34`；P6-H3 当前结果：baseline `68/100`，with-skill `98/100`，delta `+30`。P6 预声明证据组三轮平均 delta 约 `+28.7`，已经恢复进入公开正式版发布准备的资格；当前候选版本为 `0.1.0-rc.1`，本地核心包、本地发布记录和公开 GitHub 核心仓库已完成。
