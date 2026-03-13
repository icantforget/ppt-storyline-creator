# PPT Storyline Creator

<p align="center">
  <img src="assets/hero.png" alt="PPT Storyline Creator" width="600">
</p>

<p align="center">
  基于故事线思维的高质量 PPT 创作助手 — AI 引导的分步工作流
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Claude-black?style=flat-square&logo=anthropic&logoColor=white" alt="Claude">
  <img src="https://img.shields.io/badge/ChatGPT-412991?style=flat-square&logo=openai&logoColor=white" alt="ChatGPT">
  <img src="https://img.shields.io/badge/Kiro-232F3E?style=flat-square&logo=amazon&logoColor=white" alt="Kiro">
  <img src="https://img.shields.io/badge/Cursor-000?style=flat-square&logo=cursor&logoColor=white" alt="Cursor">
  <img src="https://img.shields.io/badge/Open_WebUI-FF6B35?style=flat-square" alt="Open WebUI">
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="MIT License">
</p>

<p align="center">
  <b><a href="README.md">🇺🇸 English</a></b> | <b>🇨🇳 中文</b>
</p>

---

## 这是什么

直接让 AI 生成 PPT，往往内容空洞、结构混乱。这个 skill 的核心思路是：

> **先把需求搞清楚 → 再把故事线做好 → 再把内容写充实 → 最后交给工具排版**

通过分步对话工作流，把你的想法逐步变成结构清晰、内容充实的 Markdown 素材，再交给 Kimi / Gamma 等工具一键生成高质量 PPT。

🌐 **自动语言检测** — 根据你第一条消息的语言，全程用中文或英文交流。

---

## 工作流程

```
需求澄清      搞清楚受众、目标、内容范围、页数要求
    ↓
故事线框架    梳理章节结构，确认叙事逻辑
    ↓
草稿生成      为每个章节生成详细 Markdown 草稿（含 Mermaid 图表）
    ↓
页面规划      智能拆分草稿为 slide 页面，确认后生成
    ↓
手动精修      你自行检查每页内容，按需调整
    ↓
风格+提示语   选择视觉风格，生成 AI 排版提示语
    ↓
质量评审      多维度评分 + 改进建议
    ↓
生成 PPT      选工具，上传文件，一键生成
```

每步完成后等待确认，不会自动跳过。任何一步不满意，可以重新生成。

---

## 快速开始

### Claude

1. 打开 [`agents/ppt-creator.md`](agents/ppt-creator.md)，复制全部内容
2. 打开 [claude.ai](https://claude.ai) → **Projects** → 你的项目 → **Project Instructions**
3. 粘贴内容并保存
4. 开始对话，描述你的 PPT 需求

### ChatGPT

1. 复制 [`agents/ppt-creator.md`](agents/ppt-creator.md) 内容
2. 打开 [chatgpt.com](https://chatgpt.com) → **探索 GPT** → **创建** → **配置** → **说明**
3. 粘贴并保存
4. 开始对话

### Kiro

1. 将 [`kiro/steering/ppt-creator.md`](kiro/steering/ppt-creator.md) 复制到你项目的 `.kiro/steering/` 目录：
   ```bash
   mkdir -p .kiro/steering
   curl -o .kiro/steering/ppt-creator.md \
     https://raw.githubusercontent.com/<your-username>/ppt-storyline-creator/main/kiro/steering/ppt-creator.md
   ```
2. 在 Kiro 对话中输入 `#ppt-creator` 引用 skill
3. 开始对话

### Cursor

1. 复制 [`agents/ppt-creator.md`](agents/ppt-creator.md) 内容
2. 粘贴到 `.cursor/rules` 或项目的 system prompt 设置中
3. 开始对话

### Open WebUI / 其他支持 system prompt 的工具

1. 复制 [`agents/ppt-creator.md`](agents/ppt-creator.md) 内容
2. 粘贴到 System Prompt 输入框
3. 开始对话

---

## 输出文件结构

```
your-project/
├── ppt_draft/
│   ├── draft_01_<章节>.md     # 详细草稿（每份 100–300 行）
│   ├── draft_02_<章节>.md
│   └── ...
└── ppt_slides/
    ├── slide_00_agenda.md     # 目录页
    ├── slide_01_<章节>.md     # 精简后的 slide 内容
    ├── ...
    └── prompt_for_ppt.md      # 可直接发给 Kimi 等工具的提示语
```

---

## 风格选项

| | 风格 | 适合场景 | 主色调 |
|:---:|---|---|:---:|
| A | 商务蓝 | 商业汇报、科技类演示 | #003087 |
| B | 活力橙 | 高冲击力提案、产品发布 | #FF6600 |
| C | 专业灰蓝 | 数据报告、分析类内容 | #0066CC |
| D | 自然绿 | 可持续发展、战略规划 | #00704A |
| E | 深色高端 | 金融、投资、发布会 | #1A1A2E |
| F | 清新极简 | 学术、教育、内部分享 | #F5F5F5 |
| G | 自定义 | 描述你想要的风格 | — |

---

## 质量评审维度

生成完成后，skill 会从以下维度对内容打分并给出改进建议：

| 维度 | 分值 | 说明 |
|---|:---:|---|
| 结构逻辑 | 25 | 章节是否有清晰的叙事逻辑 |
| 内容质量 | 20 | 每页是否有实质性内容 |
| MECE 程度 | 15 | 内容是否不重叠、不遗漏 |
| 金字塔原则 | 15 | 结论是否先行、论据是否支撑 |
| 商业价值 | 15 | 内容是否有实际价值和洞察 |
| 可执行性 | 10 | 建议是否具体可落地 |

---

## 兼容的 PPT 生成工具

| 工具 | 特点 | 地址 |
|---|---|---|
| **Kimi**（推荐） | 支持上传 Markdown，智能布局，免费额度充足 | kimi.moonshot.cn |
| **Gamma** | 设计感强，适合对外展示 / 英文场景 | gamma.app |
| **Beautiful.ai** | 自动排版，适合商务演示 | beautiful.ai |
| **美图 AI PPT** | 模板丰富，操作简单 | ai.meitu.com |
| **豆包** | 国内工具，上传即用 | doubao.com |

---

## 文件说明

| 文件 | 说明 |
|---|---|
| `agents/ppt-creator.md` | 通用版 skill（中英双语自动切换） |
| `agents/ppt-creator-zh.md` | 纯中文版 |
| `agents/ppt-creator-en.md` | 纯英文版 |
| `kiro/steering/ppt-creator.md` | Kiro steering 专用版 |

---

## License

MIT
