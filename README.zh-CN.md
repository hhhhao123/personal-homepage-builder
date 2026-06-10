<p align="center">
  <img src="assets/images/personal-homepage-builder-banner-wide.png" alt="Personal Homepage Builder banner" width="720">
</p>

<h1 align="center">Personal Homepage Builder</h1>

<p align="center">
  一个面向 AI Agent（智能体）的个人主页构建 Skill（能力包）：把普通人模糊、零散的自我表达，转化成可确认的主页或小型个人站点方案，再进入设计和开发。
</p>

<p align="center">
  <a href="https://github.com/hhhhao123/personal-homepage-builder"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-personal--homepage--builder-24292f?logo=github"></a>
  <img alt="Agent Skill" src="https://img.shields.io/badge/Agent-Skill-0A7EBA">
  <img alt="GitHub Pages" src="https://img.shields.io/badge/GitHub%20Pages-ready-2E6B3F">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-E95D3C">
</p>

<p align="center">
  <a href="README.md">English</a> | 简体中文
</p>

---

## 这个项目解决什么问题

很多人想做个人主页，但一开始并不知道该怎么表达自己：

- 不知道主页应该放什么内容
- 不知道给招聘者、合作者、朋友、读者看到的重点是否一样
- 不知道自己适合什么视觉风格
- 手里只有零散材料，比如 GitHub、简历、项目链接、照片、社交账号
- 想做得有个人特色，但又不想变成模板化作品集

`personal-homepage-builder` 的价值不在于直接生成一个网页模板，而在于先把这些模糊想法拆清楚。它会引导 Agent 先和用户对话，梳理身份、受众、展示内容、隐私边界和审美偏好，然后整理成一份能看懂、能确认、也能继续开发的主页方案。

简单说，它先帮你把“我想要一个个人主页”变成“这个主页应该怎么表达我、给谁看、放什么内容、做成什么感觉”。

## 适合什么场景

你可以在这些情况下使用它：

- 从零开始做 `username.github.io` 个人主页
- 做作品集、简历站、创作者主页、学术主页或个人品牌页
- 规划单页主页，或者带有项目、文章、关于我等页面的小型个人站点
- 把简历、GitHub、项目、论文、文章、照片、社交链接整理成主页内容
- 已经有一个主页，但觉得太模板、太普通，想重新梳理和优化
- 想添加动态效果、媒体内容或更强的视觉风格，但不知道什么适合自己
- 想发布到 GitHub Pages，并希望保持静态、轻量、容易维护

## 当前重点

这个能力包目前重点强调：

- **从零引导**：用户没有想法时，Agent 应该一轮一轮问，而不是要求用户一次性提供完整材料。
- **低压力对话**：优先用选择题、对比场景和简单草图帮助用户反应，而不是让用户填写工程表单。
- **先给方向再判断**：当用户说不清楚时，可以先给几种可能方向、文字版页面草图或内容缺口清单，让用户判断哪里不对。
- **材料准备提示**：Agent 需要告诉用户后续可能要准备哪些内容，比如链接、项目、照片、社交账号、参考网站。
- **先确认再动手**：没有确认受众、目的、核心内容、风格倾向、隐私边界和联系方式前，不应该直接写页面。
- **调整也要先确认**：即使只是优化已有页面、添加动效、改栏目或调整样式，也应该先讨论方案，用户确认后再改代码。
- **方案要跟着变化**：小改动可以只记录改动方案；如果受众、定位、页面结构或整体风格变了，之前确认过的主页方案也要同步更新。
- **不让新手选配置**：新手不需要自己判断该用什么模式，Agent 会根据对话内容自动决定该问多细、做多复杂。
- **页面结构清楚**：真实项目可以是一页，也可以拆成首页、项目、文章、关于我等多个页面；文件默认放在清晰的 `assets/` 结构里，不写成一个巨大 HTML 文件。
- **该用设计能力时就用设计能力**：在设计、主题、前端、图片和最终检查阶段，尽量调用对应的辅助 Skill。
- **默认不使用表情符号**：除非用户明确要求，否则方案、文案、页面标签和生成内容都不使用 emoji。

## 安装

如果你的 Agent 环境支持 `skills` CLI，可以这样安装：

```powershell
npx skills add https://github.com/hhhhao123/personal-homepage-builder --skill personal-homepage-builder
```

安装后请重启 Agent，让新的能力被识别。

## 新手怎么开始

你不需要提前准备完整材料，也不需要懂网页设计术语。最简单的第一句话可以这样写：

```text
Use $personal-homepage-builder。我要做一个个人主页，但现在没什么想法，也不知道需要准备什么资料。请你一步一步问我，先不要写代码。
```

如果你已经有一点材料，可以这样写：

```text
Use $personal-homepage-builder。我有 GitHub、几个项目链接和一段自我介绍，但不知道怎么整理成个人主页。请先帮我梳理需求。
```

如果你已经有主页，但想优化：

```text
Use $personal-homepage-builder。我已经有一个个人主页，但感觉比较普通。请先看当前页面，再告诉我哪些地方可以优化，不要直接改代码。
```

如果你已经知道想改哪里，也可以这样写：

```text
Use $personal-homepage-builder。我的项目展示区想做得更有设计感，也想加一点轻微动效。请先给我改动方案，等我确认后再改代码。
```

## Agent 应该怎么引导你

这个能力包要求 Agent 不要一上来就问“你想要什么风格”。更合理的流程应该是分轮推进：

1. 先用容易回答的问题帮你起步，比如“更像线上名片、作品集，还是个人介绍页？”
2. 再问你想展示哪些内容，比如项目、文章、作品、照片、社交账号。
3. 再判断这些内容适合放在一个长页面里，还是拆成首页、项目、文章、关于我等页面。
4. 再确认哪些内容不能公开，比如手机号、住址、未完成项目、过时经历。
5. 然后再聊审美偏好，比如你喜欢什么网站、颜色、氛围、音乐、电影、物件，或者你讨厌什么风格。
6. 如果你说不清楚，它应该给你几个方向卡片或文字版页面草图，让你判断“太正式、太普通、太花哨、太像简历”。
7. 最后把这些回答翻译成主页结构、视觉方向、动效方式和实现计划。

它应该边问边总结，并告诉你下一轮可能需要准备什么，而不是三四轮就草草结束。

## 你可能需要逐步准备什么

不是一开始就要全部准备好。可以按对话推进慢慢补：

| 类型 | 可以准备的内容 | 作用 |
| --- | --- | --- |
| 基础身份 | 公开姓名、一句话介绍、当前身份 | 决定主页代表谁 |
| 受众 | 招聘者、合作者、客户、读者、朋友、同行 | 决定内容顺序和语气 |
| 记忆点 | 希望别人 10 秒后记住什么 | 避免变成普通简历页 |
| 内容材料 | 项目、论文、文章、服务、作品、社交链接 | 决定页面栏目 |
| 页面结构 | 全部放一页，还是拆成项目、文章、关于我等页面 | 决定站点规模和导航 |
| 证明材料 | GitHub、Demo、截图、论文、评价、数据 | 增强可信度 |
| 隐私边界 | 不公开的信息、过时信息、敏感材料 | 避免误发布 |
| 审美线索 | 喜欢的网站、App、颜色、音乐、电影、地点、物件 | 帮助推导风格 |
| 媒体素材 | 头像、照片、封面、视频、截图 | 决定是否做媒体增强 |
| 动效偏好 | 不要、轻微、中等、强表达，或者不确定 | 控制动态效果 |
| 发布限制 | GitHub 用户名、仓库、语言、上线时间 | 决定实现和发布方式 |

## 默认工作方式

如果你没有明确要求，新手不需要选择任何模式或档位。Agent 应该在后台自己判断工作方式，前台只需要告诉你：

> 我会先花一点时间了解你是谁、主页给谁看、要展示什么和不想展示什么，然后做一个足够个性化但不过度复杂的方案。

当你的目标更明确时，Agent 应该自动调整：

- 想快速上线：少问一些，先做能发布的版本。
- 有照片、视频、音乐或视觉素材：安排更适合展示媒体内容的页面。
- 做学术主页：突出论文、项目、履历、研究方向和联系方式。
- 想做精致定制版本：增加审美方向、视觉细节和动效打磨。
- 要发布、推送、部署：增加仓库、分支、构建和上线前检查。

## 最终会得到什么

根据你的材料和目标，Agent 可以产出：

- 方向卡片、文字线框图、内容缺口清单，帮助你判断自己真正想要什么
- 一份经过你确认的个人主页需求文档
- 你的公开身份、受众、记忆点和隐私边界总结
- 推荐的页面结构：单页主页，或者带项目、文章、关于我等页面的小型站点
- 适合你的视觉方向、颜色、字体、图片策略和动效建议
- 设计、前端、图片和最终检查步骤的安排
- 一个适合 GitHub Pages 的静态主页或小型个人站点
- 对已有主页的局部优化建议
- 已有页面调整前的改动方案和确认步骤
- 当方向变化时，更新当前主页方案或生成新的方案版本
- 发布到 GitHub Pages 前的检查和提交流程

## 需求文档示例

Agent 在写代码前，应该先产出类似这样的需求文档，并等待你确认：

```markdown
## 个人主页方案

- 主页主要给谁看：合作者、招聘者、技术同行
- 希望别人记住什么：我能把 AI 想法做成可用的小工具
- 首页必须展示：一句话介绍、两个代表项目、GitHub、LinkedIn、一篇文章、联系方式
- 暂时没有的材料：正式头像、最终项目链接，可以先用占位内容
- 不公开的内容：手机号、住址、未完成课程项目、夸大的项目效果
- 页面感觉：安静、技术感、可信，但不要太像公司官网
- 动态效果：只做轻微滚动出现和按钮反馈，不做夸张动画
- 页面结构：首页做清晰概览，项目内容较多时可以单独做 `projects.html`
- 文件组织：使用 `index.html`、可选的支持页面和 `assets/` 文件夹，方便后续维护

请确认：这个方案是否准确？有没有哪部分需要补充、删掉或改得更像你？
```

## 推荐辅助 Skills

这个能力包可以独立使用，但搭配下面这些辅助 Skill，主页质量通常会更好：

| Skill | 作用 | 安装 / 来源 |
| --- | --- | --- |
| `design-taste-frontend` | 根据主页方案推导更合适的审美方向、视觉密度、动效强度和反模板约束。 | [`npx skills add https://github.com/Leonxlnx/taste-skill --skill design-taste-frontend`](https://www.skills.sh/leonxlnx/taste-skill/design-taste-frontend) |
| `frontend-design` | 生成更有设计感、更接近真实产品质量的页面 UI。 | [`npx skills add https://github.com/anthropics/skills --skill frontend-design`](https://www.skills.sh/anthropics/skills/frontend-design) |
| `theme-factory` | 帮助生成或整理颜色、字体、间距等主题系统。 | [`npx skills add https://github.com/anthropics/skills --skill theme-factory`](https://www.skills.sh/anthropics/skills/theme-factory) |
| `web-design-guidelines` | 最后检查 UI、UX、响应式和可访问性问题。 | [`npx skills add https://github.com/vercel-labs/agent-skills --skill web-design-guidelines`](https://www.skills.sh/vercel-labs/agent-skills/web-design-guidelines) |
| `web-artifacts-builder` | 只在需要复杂 React/Tailwind/shadcn 页面时使用。 | [`npx skills add https://github.com/anthropics/skills --skill web-artifacts-builder`](https://www.skills.sh/anthropics/skills/web-artifacts-builder) |
| `find-skills` | 当现有能力不够时，帮助发现更多可安装 Skill。 | [`npx skills add https://github.com/vercel-labs/add-skill --skill find-skills`](https://www.skills.sh/vercel-labs/add-skill/find-skills) |
| `skill-installer` | Codex 系统 Skill，用于从精选列表或 GitHub 路径安装 Skill。 | [Source: `openai/skills`](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) |

本仓库不会自动安装这些辅助 Skill。需要时请单独安装。

## 在其他 Agent 中使用

这个仓库不绑定某一个运行时。如果你的 Agent 不支持 `skills` CLI，可以把整个仓库交给 Agent，或者把 `SKILL.md` 和 `references/` 文件夹复制到对应系统的 Skill、instruction 或 knowledge 格式中。

至少需要提供：

- `SKILL.md`：主工作流
- `references/`：访谈问题、材料提取、风格翻译、实现指导和质量检查
- 可选辅助 Skill，或当前系统里等价的设计、前端、图片和审查能力

## 仓库结构

```text
personal-homepage-builder/
|-- LICENSE
|-- SKILL.md
|-- README.md
|-- README.zh-CN.md
|-- agents/
|   `-- openai.yaml
|-- assets/
|   `-- images/
|       `-- personal-homepage-builder-banner-wide.png
`-- references/
    |-- anti-patterns.md
    |-- archetypes.md
    |-- brief-lifecycle.md
    |-- beginner-conversation-patterns.md
    |-- beginner-validation-scenario.md
    |-- content-intake.md
    |-- delivery-modes.md
    |-- forward-tests.md
    |-- github-pages-bootstrap.md
    |-- homepage-brief.md
    |-- implementation.md
    |-- interview.md
    |-- iteration-requests.md
    |-- media-assets.md
    |-- motion-design.md
    |-- output-contracts.md
    |-- personal-signal-intake.md
    |-- profile-schema.md
    |-- profile-signals.md
    |-- quality-checklist.md
    |-- requirements-template.md
    |-- session-protocol.md
    |-- site-structure.md
    |-- skill-routing.md
    |-- social-links.md
    `-- style-directions.md
```

## 设计理念

个人主页不应该只是把简历搬到网页上。它应该回答三个问题：

- 这个人是谁
- 他希望别人因为什么记住他
- 他的工作、经历、兴趣或审美有什么值得被看见

这个 Skill 的目标，就是让 Agent 先把这些问题问清楚，再去做设计和代码。这样做出来的主页才更像一个真实的人，而不是一个通用模板。
