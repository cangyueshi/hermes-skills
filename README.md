# Hermes Skills — Ported from mattpocock/skills

[EN] This repository is a **Hermes Agent adaptation** of selected skills from [mattpocock/skills](https://github.com/mattpocock/skills) (132k+ stars) — a collection of AI agent skills designed for real engineering work, not vibe coding.

[CN] 本仓库是 [mattpocock/skills](https://github.com/mattpocock/skills)（132k+ stars）精选技能的 **Hermes Agent 移植版**——一套为真实工程工作设计的 AI Agent 技能集，不是 vibe coding。

---

## Skills / 技能清单

### productivity/

| Skill | Original Author / 原作者 | Description / 说明 | Standalone Repo / 独立仓库 |
|-------|-------------------------|-------------------|--------------------------|
| [caveman-hermes-skill](./productivity/caveman-hermes-skill/SKILL.md) | [mattpocock](https://github.com/mattpocock) | [EN] Ultra-compressed communication mode. Drops filler, articles, pleasantries — saves ~75% tokens while keeping full technical accuracy. [CN] 极简沟通模式。去掉废话/冠词/客套话，省约75% tokens，保留完整技术准确性。 | [github.com/cangyueshi/caveman-hermes-skill](https://github.com/cangyueshi/caveman-hermes-skill) |
| [teach-hermes-skill](./productivity/teach-hermes-skill/SKILL.md) | [mattpocock](https://github.com/mattpocock) | [EN] Multi-session teaching system. Creates a stateful workspace with HTML lessons, learning records, reference docs, and tracks the user's zone of proximal development. [CN] 多 Session 教学系统。创建有状态的教学空间，生成 HTML 课程 + 学习记录 + 参考文档，追踪用户的最近发展区。 | [github.com/cangyueshi/teach-hermes-skill](https://github.com/cangyueshi/teach-hermes-skill) |

---

## Attribution / 版权说明

[EN] Each skill in this repository is adapted from [mattpocock/skills](https://github.com/mattpocock/skills) and modified specifically for **Hermes Agent**. The original concepts, structure, and philosophy belong to Matt Pocock. The adaptations include:
- Bilingual (EN/CN) instruction format
- Hermes Agent compatible YAML frontmatter
- Tool integration adjustments for Hermes Agent's ecosystem

[CN] 本仓库中的每个技能均改编自 [mattpocock/skills](https://github.com/mattpocock/skills)，并专门为 **Hermes Agent** 进行了定制修改。原始概念、结构和理念归 Matt Pocock 所有。改编内容包括：
- 中英双语指令格式
- Hermes Agent 兼容的 YAML frontmatter
- 针对 Hermes Agent 生态系统的工具集成调整

---

## Installation / 安装

```bash
# Clone the repo
git clone https://github.com/cangyueshi/hermes-skills.git

# Copy skills to Hermes skills directory
cp -r hermes-skills/productivity/caveman-hermes-skill ~/.hermes/skills/productivity/
cp -r hermes-skills/productivity/teach-hermes-skill ~/.hermes/skills/productivity/

# Or for shared agent skills directory
cp -r hermes-skills/productivity/caveman-hermes-skill ~/.agents/skills/productivity/
cp -r hermes-skills/productivity/teach-hermes-skill ~/.agents/skills/productivity/
```

---

## Usage / 使用

[EN] Hermes Agent automatically scans `~/.hermes/skills/` and loads matching skills based on conversation context. The skills are triggered by keywords in your request.

[CN] Hermes Agent 会自动扫描 `~/.hermes/skills/`，根据对话上下文自动匹配加载技能。技能通过你请求中的关键词触发。

**caveman-hermes-skill triggers / 触发词:**
- "caveman mode", "talk like caveman", "use caveman", "less tokens", "be brief"

**teach-hermes-skill triggers / 触发词:**
- "teach me", "help me learn", "I want to understand", "教教我", "帮我学习"

---

## License / 许可

MIT License — consistent with the original [mattpocock/skills](https://github.com/mattpocock/skills).
MIT 许可证 — 与原作者 [mattpocock/skills](https://github.com/mattpocock/skills) 一致。
