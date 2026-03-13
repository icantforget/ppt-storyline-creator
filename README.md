# PPT Storyline Creator

<p align="center">
  <img src="assets/hero.png" alt="PPT Storyline Creator" width="600">
</p>

<p align="center">
  High-quality PPT creator powered by storyline thinking — AI-guided step-by-step workflow
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
  <b>🇺🇸 English</b> | <b><a href="README.zh-CN.md">🇨🇳 中文</a></b>
</p>

---

## What is this

Most AI-generated PPTs look the same: shallow content, messy structure, generic layouts. This skill takes a different approach:

> **Clarify needs → Build storyline → Draft rich content → Hand off to rendering tools**

Through a step-by-step dialogue workflow, it turns your idea into structured, content-rich Markdown files, then hands them off to Kimi / Gamma for final PPT rendering.

🌐 **Auto language detection** — detects your language from the first message and responds entirely in Chinese or English throughout the session.

---

## Workflow

```
Clarify requirements   Understand audience, goal, scope, slide count
        ↓
Story structure        Build chapter outline, confirm narrative logic
        ↓
Draft content          Generate detailed Markdown drafts (with Mermaid diagrams)
        ↓
Slide planning         Smart split into slides, confirm then generate
        ↓
Manual review          Review each slide, adjust as needed
        ↓
Style + prompt         Choose visual style, generate AI layout prompt
        ↓
Quality review         Multi-dimension scoring + improvement suggestions
        ↓
Generate PPT           Choose a tool, upload files, done
```

Each step waits for your confirmation. You can redo any step at any time.

---

## Quick Start

### Claude

1. Open [`agents/ppt-creator.md`](agents/ppt-creator.md) and copy the full content
2. Go to [claude.ai](https://claude.ai) → **Projects** → your project → **Project Instructions**
3. Paste the content and save
4. Start chatting — describe your PPT topic

### ChatGPT

1. Copy [`agents/ppt-creator.md`](agents/ppt-creator.md) content
2. Go to [chatgpt.com](https://chatgpt.com) → **Explore GPTs** → **Create** → **Configure** → **Instructions**
3. Paste and save
4. Start chatting

### Kiro

1. Copy [`kiro/steering/ppt-creator.md`](kiro/steering/ppt-creator.md) to your project's `.kiro/steering/` directory:
   ```bash
   mkdir -p .kiro/steering
   curl -o .kiro/steering/ppt-creator.md \
     https://raw.githubusercontent.com/<your-username>/ppt-storyline-creator/main/kiro/steering/ppt-creator.md
   ```
2. In Kiro chat, type `#ppt-creator` to reference the skill
3. Start chatting

### Cursor

1. Copy [`agents/ppt-creator.md`](agents/ppt-creator.md) content
2. Paste into `.cursor/rules` or your project's system prompt settings
3. Start chatting

### Open WebUI / Other tools

1. Copy [`agents/ppt-creator.md`](agents/ppt-creator.md) content
2. Paste into the System Prompt field
3. Start chatting

---

## Output file structure

```
your-project/
├── ppt_draft/
│   ├── draft_01_<chapter>.md     # Full content drafts (100–300 lines each)
│   ├── draft_02_<chapter>.md
│   └── ...
└── ppt_slides/
    ├── slide_00_agenda.md        # Agenda slide
    ├── slide_01_<chapter>.md     # Condensed slide-ready Markdown
    ├── ...
    └── prompt_for_ppt.md         # Ready-to-use prompt for Kimi / other tools
```

---

## Style options

| | Style | Best for | Color |
|:---:|---|---|:---:|
| A | Business Blue | Corporate decks, tech presentations | #003087 |
| B | Vibrant Orange | High-impact pitches, product launches | #FF6600 |
| C | Analytical Grey-Blue | Data-heavy reports, research | #0066CC |
| D | Natural Green | Sustainability, strategy, ESG | #00704A |
| E | Dark Premium | Finance, investment, keynotes | #1A1A2E |
| F | Clean Minimal | Academic, internal sharing, education | #F5F5F5 |
| G | Custom | Describe your own style | — |

---

## Quality review dimensions

After generation, the skill scores your deck and provides improvement suggestions:

| Dimension | Points | Description |
|---|:---:|---|
| Structure & Logic | 25 | Clear narrative flow across chapters |
| Content Quality | 20 | Substantive content on every slide |
| MECE Coverage | 15 | No overlap, no gaps |
| Pyramid Principle | 15 | Conclusion-first, supported by evidence |
| Business Value | 15 | Actionable insights and real value |
| Actionability | 10 | Specific, concrete recommendations |

---

## Compatible PPT rendering tools

| Tool | Notes | URL |
|---|---|---|
| **Kimi** (recommended) | Markdown upload, smart layout, generous free tier | kimi.moonshot.cn |
| **Gamma** | Strong design, great for external / English decks | gamma.app |
| **Beautiful.ai** | Auto-layout, suits business presentations | beautiful.ai |
| **Doubao** | Easy to use, good for Chinese content | doubao.com |

---

## File reference

| File | Description |
|---|---|
| `agents/ppt-creator.md` | Universal skill (auto-detects EN/ZH) |
| `agents/ppt-creator-zh.md` | Chinese-only version |
| `agents/ppt-creator-en.md` | English-only version |
| `kiro/steering/ppt-creator.md` | Kiro steering file |

---

## License

MIT
