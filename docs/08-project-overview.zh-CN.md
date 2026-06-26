---
title: Commercial UI/UX Codex Skill 项目说明
aliases:
  - 商业 UI/UX Codex Skill
  - commercial-ui-ux
tags:
  - codex/skill
  - ui-ux
  - product-design
  - promotion
version: 0.1.0-rc.1
status: public-release-candidate
repo: "https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill"
download: "https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill"
author: zjsthm
email: "zjsthm@gmail.com"
wechat: "63656299"
created: 2026-06-25
---

# Commercial UI/UX Codex Skill 项目说明

> [!summary] 一句话介绍
> `commercial-ui-ux` 是一套面向 Codex 的商业 UI/UX/GUI 设计 skill，帮助 AI 在设计、评审、修复和实现产品界面时，先理解业务任务、用户路径、交互风险和既有设计系统，再输出可验证、可落地的界面方案。

## 项目名称

| 项目项 | 信息 |
| --- | --- |
| 公开名称 | Commercial UI/UX Codex Skill |
| Skill 名称 | `commercial-ui-ux` |
| 仓库名称 | `commercial-ui-ux-codex-skill` |
| 当前版本 | `0.1.0-rc.1` |
| 当前状态 | 公开候选版本，可安装使用 |

## 下载地址

> [!tip] 推荐下载方式
> 项目主页与下载地址：<https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill>
>
> 这是唯一推荐下载入口。进入 GitHub 页面后，可以点击 `Code` 下载 ZIP，也可以使用下面的命令安装到 Codex skills 目录。

Windows PowerShell 安装：

```powershell
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill "$env:USERPROFILE\.codex\skills\commercial-ui-ux"
```

macOS/Linux 安装：

```bash
git clone https://github.com/zjsthmjialin/commercial-ui-ux-codex-skill ~/.codex/skills/commercial-ui-ux
```

## 项目作用

这不是一个单纯“给界面配色”的提示词包，也不是只负责把页面做得更好看的视觉皮肤库。它的核心作用是让 Codex 在商业界面任务中形成更稳定的产品设计判断：

- **设计新产品界面**：用于 SaaS 后台、仪表盘、管理台、表单、表格、移动端业务流等真实产品页面。
- **评审 UI/UX 问题**：优先指出任务链路、状态覆盖、信息层级、交互风险和可访问性问题。
- **修复既有界面**：在保留现有设计系统、路由、组件语义、密度和视觉 token 的前提下补齐失败链路。
- **推断视觉策略**：当没有品牌规范、参考图或设计系统时，根据产品语境生成克制、可信、服务任务的视觉方向。
- **覆盖行业场景**：内置 18 个顶层行业和 54 个典型 UI/GUI 场景模板，帮助 Codex 更快理解垂直业务上下文。

## 主要特点

| 特点 | 说明 |
| --- | --- |
| 项目类别自动适配 | 可根据项目类别、行业语境和业务对象，推断适合的 UI 风格、信息密度、控件类型和页面结构。例如金融风控、教育运营、SaaS 后台、审批流等场景会采用不同的界面组织方式。 |
| 无品牌规范时自动推断视觉策略 | 当用户没有提供品牌色、参考图或设计系统时，Codex 可以依据产品语境生成克制、可信、符合行业气质的视觉方向，而不是随机套用流行风格。 |
| UX -> UI -> GUI 顺序工作 | 先建模用户任务、角色、主路径和异常路径，再处理信息层级、响应式布局、控件状态和视觉细节。 |
| 既有产品修复不乱重做 | 面对已有项目时，默认保留信息架构、组件语义、视觉 token、路由和状态模型，只修复失败链路、缺失状态、字段校验、可访问性或移动端问题。 |
| 高风险状态覆盖 | 对 loading、empty、error、disabled、permission、success、destructive action 等状态给出明确处理，尤其强调受保护操作的硬门槛。 |
| 行业模板库支持 | 内置 18 个顶层行业和 54 个典型 UI/GUI 场景模板，让 Codex 更容易理解不同垂直业务的界面惯例。 |
| 交付前质量门槛 | 要求说明验证方式、未验证缺口和仍需人工判断的风险，避免只交付“看起来完成”的界面。 |

## 工作原理

`commercial-ui-ux` 通过 Codex Skill 的方式，把商业 UI/UX/GUI 的判断规则、边界、质量门槛和行业模板组织成一套可调用的本地知识结构。Codex 在触发该 skill 后，不是一次性加载所有维护材料，而是按任务类型读取必要文档。

```mermaid
flowchart LR
    A["用户提出 UI/UX/GUI 任务"] --> B["触发 commercial-ui-ux"]
    B --> C["判断任务模式与输入约束"]
    C --> D["按需读取规则、边界、宪法、质量门槛"]
    D --> E["UX: 任务链路与状态模型"]
    E --> F["UI: 信息层级与响应式布局"]
    F --> G["GUI: 控件状态、反馈与风险操作"]
    G --> H["验证、说明假设与交付结果"]
```

核心方法可以概括为四层：

1. **任务优先**：先确认用户是谁、要完成什么任务、失败会造成什么影响。
2. **系统优先**：修复既有产品时优先保留现有设计系统，而不是无理由重绘。
3. **状态优先**：loading、empty、error、disabled、permission、success、destructive action 等状态必须被看见。
4. **验证优先**：交付时说明已运行的检查、未验证项和仍需人工判断的风险。

## 应用方式

安装后，可以直接在 Codex 中提出类似请求：

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

也可以用更自然的方式：

- “帮我检查这个后台页面的 UI/UX 问题。”
- “修复这个订单管理页面的移动端、空状态和字段校验，但不要重做设计语言。”
- “为一个金融风控看板设计信息架构和 React 页面。”
- “没有品牌规范，请根据项目内容推断视觉策略。”

## 适合谁使用

| 使用者 | 典型价值 |
| --- | --- |
| 产品经理 | 把模糊需求转成更完整的界面任务、路径和状态要求 |
| UI/UX 设计师 | 快速获得结构化评审、状态清单和风险提醒 |
| 前端工程师 | 在实现页面时减少无关重构，补齐交互状态和响应式问题 |
| 创业团队 | 在没有完整设计团队时，用更稳的方式推进后台、仪表盘和业务系统界面 |
| AI 工具使用者 | 让 Codex 不只“做漂亮”，而是更像产品界面协作者 |

## 证据状态

当前候选版本基于三轮公开发布准备评估：

| 假设 | 结果 |
| --- | ---: |
| P6-H1 任务建模 | `+22` |
| P6-H2 既有系统修复 | `+34` |
| P6-H3 风险状态泛化 | `+30` |

平均增量约 `+28.7`，高于本项目采用的 `+25` 发布准备门槛。该结果说明 skill 在任务建模、既有系统修复、风险状态泛化等场景中，能让 Codex 的输出更接近商业产品界面的真实交付要求。

> [!warning] 使用边界
> 当前版本是 `0.1.0-rc.1` 候选版本。它可以提升 Codex 在商业 UI/UX/GUI 工作中的行为质量，但不替代人工产品、设计、无障碍、安全、法律、医疗、金融、领域或合规审查。

## 公开包包含内容

- `SKILL.md`
- `SKILL.zh-CN.md`
- `README.md`
- `README.zh-CN.md`
- `CHANGELOG.md`
- `VERSION`
- `docs/01-commercial-ui-ux-rules.md`
- `docs/02-skill-boundaries.md`
- `docs/03-design-constitution.md`
- `docs/05-usage-guide.md`
- `docs/06-quality-gates.md`
- `docs/07-visual-strategy-inference.md`
- `docs/09-industry-taxonomy.md`
- `docs/10-industry-template-library.md`

公开安装包只包含普通使用所需的核心文件，不包含完整源码工作区、维护脚本、原始评测包、生成截图、历史交接记录、插件元数据或 GitHub Release。

## 作者联系方式

> [!info] 联系作者
> 作者：`zjsthm`
>
> 邮箱：`zjsthm@gmail.com`
>
> 微信：`63656299`

## 推荐宣传语

> 让 Codex 不只是“生成漂亮页面”，而是能围绕业务任务、用户路径、交互风险和既有设计系统，产出更可用、更可信、更可验证的商业 UI/UX/GUI 方案。
