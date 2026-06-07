<p align="center">
  <img src="assets/images/personal-homepage-builder-banner-wide.png" alt="Personal Homepage Builder banner" width="720">
</p>

<h1 align="center">Personal Homepage Builder</h1>

<p align="center">
  一个 agent skill，用于把一个人的身份、材料、审美偏好和发布限制转化为有辨识度、适合 GitHub Pages 发布的个人主页。
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

## 为什么需要这个 Skill

大多数人开始做个人主页时，并不会一开始就拥有清晰的网站结构、个人品味和内容策略。他们通常只有一些零散材料：一份简历、一个 GitHub 主页、几个社交链接、一些照片、还没有完全成形的偏好，以及一种模糊的“我希望别人怎样看见我”的感觉。

`personal-homepage-builder` 为 AI coding agent 提供了一套可复用的工作流，专门处理这种混乱的起点。它帮助 agent 提出更好的问题，提取有用材料，把个人信号转化为设计方向，并构建一个具体、有个人辨识度，而不是模板感很重的主页。

当你想创建或重设计以下内容时，可以使用它：

- `username.github.io` 个人主页
- 作品集、简历站、创作者页面或学术主页
- 包含社交链接和精选作品的个人品牌网站
- 无需后端、可以轻量发布的静态主页
- 使用照片、视频、音乐或生成式视觉资产的媒体增强型个人主页

## 这个 Skill 能帮助 Agent 做什么

这个 skill 会引导 agent 完成一套完整的个人主页工作流：

1. **定位**：检查现有项目，或选择适合 GitHub Pages 的起点。
2. **提取**：阅读简历、简介、笔记、链接、照片、截图和其他源材料。
3. **访谈**：围绕身份、受众、第一印象、审美偏好和隐私边界提出具体问题。
4. **反思**：总结已知信息、推断信息，以及仍需确认的内容。
5. **分类**：选择个人主页原型和页面结构。
6. **定义风格**：把个性、文化偏好、参考对象和反感点转化为具体视觉方向。
7. **形成 Brief**：产出可驱动实现的 `personal_homepage_brief`。
8. **实现**：使用当前项目技术栈构建或更新网站。
9. **审查与发布**：测试结果，并为 GitHub Pages 发布做好准备。

核心规则很简单：不要一开始就问“你想要什么风格？”大多数用户很难直接回答这个问题。这个 skill 会推动 agent 先发现身份，再根据证据推导设计选择。

这个 skill 是发现和编排层。它先帮助用户明确身份和设计需求，再在可用时把审美、主题、前端、图片和审查工作交给正确的辅助 skills。

## 安装

可以在任何兼容 skill 的 agent 环境中从本仓库安装该 skill。对于 Codex 或其他支持 `skills` CLI 的环境，可以使用：

```powershell
npx skills add https://github.com/hhhhao123/personal-homepage-builder --skill personal-homepage-builder
```

安装后请重启你的 agent，这样新 skill 才能被发现。

## 在其他 Agent 中使用

这个仓库不绑定某一个 agent 运行时。如果你的 agent 系统不支持 `skills` CLI，可以把整个仓库交给 agent，或者把 `SKILL.md` 和 `references/` 文件夹复制到该系统的 skill、instruction 或 knowledge 格式中。

至少需要提供：

- `SKILL.md`：主工作流说明
- `references/`：访谈问题、内容提取、风格方向、实现指导和质量检查
- 可选的辅助 skill，或当前系统中等价的设计/前端能力

## 需要准备什么

这个 skill 几乎可以从零开始，但材料越充分，主页越容易做出个人感。建议准备：

- 简历、简短描述或自我介绍
- GitHub、LinkedIn、X/Twitter、Instagram、YouTube、Bilibili、小红书或其他社交链接
- 项目、论文、文章、服务、产品或作品集链接
- 照片、头像、截图、视频、音乐参考或已有品牌资产
- 你喜欢或不喜欢的个人网站示例
- 一个粗略答案：谁会访问这个页面？你希望他们记住你什么？

## 示例 Prompt

```text
Use $personal-homepage-builder to help me build a personal github.io homepage.
```

```text
Use $personal-homepage-builder. I have a resume, GitHub profile, photos, and a few social links. Help me turn them into a homepage.
```

```text
Use $personal-homepage-builder to redesign my existing personal site so it feels more like me and less like a template.
```

```text
Use $personal-homepage-builder to create a portfolio homepage for my research, projects, writing, and contact links.
```

## 你会得到什么

根据你的需求和可用材料，agent 可以产出：

- 简洁的个人主页
- 内容结构和公开展示用的个人简介
- 个人主页原型和栏目建议
- 视觉方向、颜色、字体、图片、媒体和动效指导
- 兼容 GitHub Pages 的静态站点，或对现有站点的更新
- 当用户要求 GitHub 发布时，提供可发布的提交和推送流程

## Brief 示例

这个 skill 会要求 agent 在实现前先创建一个紧凑的 brief，让设计和代码基于已确认的意图，而不是凭空猜测：

```yaml
personal_homepage_brief:
  identity:
    primary_role: "AI researcher and builder"
    personal_elements: ["open-source projects", "writing", "selected photos"]
  audience:
    primary: "collaborators, recruiters, and peers"
  goal:
    first_impression: "thoughtful, technical, approachable"
    remembered_for: "turning research ideas into usable tools"
  content:
    required_sections: ["intro", "projects", "writing", "social links"]
  style:
    direction_name: "quiet technical editorial"
    must_avoid: ["generic portfolio grid", "overly flashy effects"]
  constraints:
    hosting: "GitHub Pages"
    emoji_policy: "no emoji unless explicitly requested"
  implementation:
    companion_skills: ["design-taste-frontend", "frontend-design", "theme-factory", "web-design-guidelines"]
```

## 推荐辅助 Skills

这个 skill 可以独立使用，但如果当前 agent 系统中有以下辅助 skills，主页质量通常会更好：

| Skill | 为什么安装它 | 安装 / 来源 |
| --- | --- | --- |
| `design-taste-frontend` | 在 UI 工作开始前读取 brief，推断合适的设计方向、视觉密度、动效强度和反模板约束。 | [`npx skills add https://github.com/Leonxlnx/taste-skill --skill design-taste-frontend`](https://www.skills.sh/leonxlnx/taste-skill/design-taste-frontend) |
| `frontend-design` | 生成更有辨识度、更接近生产级的主页 UI，避免通用模板感。 | [`npx skills add https://github.com/anthropics/skills --skill frontend-design`](https://www.skills.sh/anthropics/skills/frontend-design) |
| `theme-factory` | 帮助创建或应用一致的颜色和字体系统。 | [`npx skills add https://github.com/anthropics/skills --skill theme-factory`](https://www.skills.sh/anthropics/skills/theme-factory) |
| `web-design-guidelines` | 提供最终的 UI、UX 和可访问性审查。 | [`npx skills add https://github.com/vercel-labs/agent-skills --skill web-design-guidelines`](https://www.skills.sh/vercel-labs/agent-skills/web-design-guidelines) |
| `web-artifacts-builder` | 仅当主页以复杂 React/Tailwind/shadcn artifact 实现时有用。 | [`npx skills add https://github.com/anthropics/skills --skill web-artifacts-builder`](https://www.skills.sh/anthropics/skills/web-artifacts-builder) |
| `find-skills` | 当当前能力不足时，帮助用户发现和安装更多 skills。 | [`npx skills add https://github.com/vercel-labs/add-skill --skill find-skills`](https://www.skills.sh/vercel-labs/add-skill/find-skills) |
| `skill-installer` | Codex 系统 skill，用于从精选列表或 GitHub 路径安装 skills；通常已在 Codex 中可用。 | [Source: `openai/skills`](https://github.com/openai/skills/tree/main/skills/.system/skill-installer) |

本 skill 不会自动安装这些辅助 skills。如果你希望 agent 在创建主页时使用它们，需要单独安装。

当这个 skill 在个人主页设计对话中被启用后，除非用户明确退出，否则 agent 应该在本轮对话后续都继续遵守这个工作流。在审美理解和 UI 定制阶段，agent 应该在可用时调用相关的设计/前端辅助 skills。brief、文案、UI 标签和生成内容默认禁用 emoji，除非用户明确要求使用。

## 仓库结构

```text
personal-homepage-builder/
|-- LICENSE                          # MIT license
|-- SKILL.md                         # 主 skill 说明
|-- README.md                        # 英文仓库介绍
|-- README.zh-CN.md                  # 简体中文仓库介绍
|-- agents/
|   `-- openai.yaml                  # 可选的 OpenAI/Codex UI 元信息
|-- assets/
|   `-- images/
|       `-- personal-homepage-builder-banner-wide.png
`-- references/
    |-- archetypes.md                # 个人主页原型和结构
    |-- content-intake.md            # 源材料提取 schema
    |-- delivery-modes.md            # 快速/深入/媒体/发布路线
    |-- github-pages-bootstrap.md    # GitHub Pages 设置指南
    |-- implementation.md            # 面向技术栈的实现指导
    |-- interview.md                 # 发现式访谈问题库
    |-- media-assets.md              # 图片、视频、音频和嵌入处理
    |-- profile-schema.md            # 可维护的个人资料数据约定
    |-- profile-signals.md           # 可选身份和审美信号
    |-- quality-checklist.md         # 最终质量检查清单
    |-- social-links.md              # 联系方式和平台展示规则
    `-- style-directions.md          # 风格方向转换模式
```

## 设计理念

个人主页不应该都长得像同一个作品集模板。一个好的个人主页应该让访问者快速理解三件事：

- 这个人是谁
- 这个人希望因什么被记住
- 他的工作、故事或审美为什么值得记住

这个 skill 正是围绕这一点设计的。它把简历、MBTI 标签、兴趣爱好、喜欢的媒体、截图、照片、作品链接和社交平台都视为信号。有些是强证据，有些只是线索。agent 会被要求先和用户确认这些信号的真实含义，再把它们转化为公开展示的设计和内容。

预期顺序是：先明确“这个人是谁”，形成更好的设计 brief，然后再调用专门的 taste 和前端 skills，做出更个性化的个人主页。
