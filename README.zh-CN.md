# Commercial UI/UX Codex Skill（中文说明）

`commercial-ui-ux` 是一个用于 Codex 的商业 UI/UX/GUI skill，面向产品界面设计、评审、修复和实现任务。

它帮助 Codex 优先处理业务任务、用户路径、工作流状态、交互风险、既有设计系统、无障碍和验证，而不是只生成配色方案、视觉皮肤或组件库模板。

## 联系作者

- 作者：`zjsthm`
- 邮箱：`zjsthm@gmail.com`
- 微信：`63656299`

## 安装

将本仓库克隆到 Codex skills 目录，并命名为 `commercial-ui-ux`。

Windows PowerShell：

```powershell
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill "$env:USERPROFILE\.codex\skills\commercial-ui-ux"
```

macOS/Linux：

```bash
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill ~/.codex/skills/commercial-ui-ux
```

安装后，可以让 Codex 使用 `commercial-ui-ux` 来处理商业 UI/UX/GUI 的设计、评审、修复或实现工作。

## 适用场景

适合用于：

- SaaS 后台、仪表盘、管理台、工作流工具、移动端业务界面、表单、表格和高密度产品界面。
- UI/UX 评审，重点关注任务成功率、状态覆盖、信息层级、可访问性和交互风险。
- 既有产品界面修复，在保留设计系统、路由、组件语义、信息密度和视觉 token 的前提下补齐失败链路。
- 无品牌规范场景，根据产品上下文推断视觉策略。
- 行业化 UI/GUI 规划，根据垂直领域补齐状态、风险、控件和信息密度。

不适合作为纯 Logo 设计、独立插画、海报艺术、装饰风格、法律/医疗/金融/合规判断或欺骗性界面工作的主要工具。

## 包含文件

核心 skill 文件：

- `SKILL.md`
- `SKILL.zh-CN.md`
- `README.zh-CN.md`

用户文档：

- `docs/05-usage-guide.md`
- `docs/01-commercial-ui-ux-rules.md`
- `docs/02-skill-boundaries.md`
- `docs/03-design-constitution.md`
- `docs/06-quality-gates.md`
- `docs/07-visual-strategy-inference.md`
- `docs/09-industry-taxonomy.md`
- `docs/10-industry-template-library.md`

版本元数据：

- `VERSION`
- `CHANGELOG.md`

公开安装包只保留普通使用所需的核心文件，不包含维护脚本、评测轮次、生成截图、本地发布产物或历史交接记录。

## 典型请求

```markdown
使用 commercial-ui-ux 设计一个 B2B SaaS 客户健康度仪表盘。

任务类型：新建产品界面
目标用户：客户成功经理和销售负责人
平台：响应式 Web，桌面优先
核心任务：发现高风险客户、理解风险原因、分配跟进任务
已有设计系统：浅色主题、8px 圆角、紧凑表格密度
视觉来源：按产品上下文推断
必须包含：客户列表、健康分、筛选器、空/加载/错误状态、受保护的批量操作
避免：营销式 hero、装饰性渐变、无关重设计
```

## Codex 应如何工作

1. 从 `SKILL.md` 或 `SKILL.zh-CN.md` 进入。
2. 只读取当前任务需要的参考文档。
3. 按 UX -> UI -> GUI 的顺序工作。
4. 除非用户明确要求重设计，否则保留既有产品系统。
5. 在适用场景覆盖 loading、empty、error、disabled、permission、success 和破坏性操作状态。
6. 使用项目可用检查验证结果，并说明未验证缺口。

## 证据状态

当前候选版本基于三轮公开发布准备评估：

| 假设 | 结果 |
| --- | ---: |
| P6-H1 任务建模 | `+22` |
| P6-H2 既有系统修复 | `+34` |
| P6-H3 风险状态泛化 | `+30` |

平均增量约 `+28.7`，高于本包使用的 `+25` 发布准备门槛。

## 版本

当前版本：`0.1.0-rc.1`

这是一个候选版本。它可以提升 Codex 在商业 UI/UX/GUI 工作中的行为质量，但不替代人工产品、设计、无障碍、安全、领域或合规审查。
