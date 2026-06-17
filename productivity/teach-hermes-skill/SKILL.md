---
name: teach-hermes-skill
description: >-
  [EN] Teach the user a new skill or concept over multiple sessions, using the current directory as a stateful teaching workspace. Creates lessons (HTML), reference docs, learning records, and tracks the user's zone of proximal development.
  [CN] 多 Session 教学系统。在当前目录创建教学空间，生成 HTML 课程 + 学习记录 + 参考文档，追踪用户的最近发展区。
  Use when user says "teach me", "help me learn", "I want to understand", or asks for a tutorial on any topic.
attribution: >-
  [EN] Ported from mattpocock/skills (https://github.com/mattpocock/skills) — adapted specifically for Hermes Agent.
  [CN] 移植自 mattpocock/skills (https://github.com/mattpocock/skills) — 专为 Hermes Agent 定制改编。
---

# Teach / 教学系统

[EN] The user has asked you to teach them something. This is a stateful request — they intend to learn the topic over multiple sessions.
[CN] 用户请你教他们某件事。这是一个有状态的请求——他们打算在多个 session 中持续学习这个主题。

## Teaching Workspace / 教学工作区

[EN] Treat the current directory as a teaching workspace. The state of their learning is captured in these files:
[CN] 将当前目录视为教学工作区。学习状态记录在以下文件中：

| File | EN | CN |
|------|----|----|
| **`MISSION.md`** | The _reason_ the user is interested in the topic. Grounds all teaching. See [MISSION-FORMAT.md](./references/MISSION-FORMAT.md). | 用户学习该主题的_原因_。所有教学以此为根基。 |
| **`RESOURCES.md`** | Curated list of high-quality, high-trust resources. See [RESOURCES-FORMAT.md](./references/RESOURCES-FORMAT.md). | 高质量、高可信度资源清单。 |
| **`NOTES.md`** | Scratchpad for user preferences and working notes. | 用户偏好和工作笔记的草稿本。 |
| **`./learning-records/`** | Learning records capturing non-obvious lessons and key insights. See [LEARNING-RECORD-FORMAT.md](./references/LEARNING-RECORD-FORMAT.md). | 学习记录，记录非显而易见的教训和关键洞察。 |
| **`./lessons/`** | Self-contained HTML lessons, one per session. Beautiful, clean typography. | 自包含的 HTML 课程，每 session 一个。美观清晰的排版。 |
| **`./reference/`** | Reference documents (cheat sheets, glossaries, syntax references). | 参考文档（速查表、术语表、语法参考）。 |

## Philosophy / 教学理念

[EN] To learn at a deep level, the user needs three things:
[CN] 深度学习需要三样东西：

- **Knowledge / 知识** — captured from high-quality, high-trust resources
- **Skills / 技能** — acquired through highly-relevant interactive lessons devised by you, based on the knowledge
- **Wisdom / 智慧** — comes from interacting with other learners and practitioners

[EN] Before `RESOURCES.md` is well-populated, focus on finding high-quality resources. Never trust your parametric knowledge alone.
[CN] 在 `RESOURCES.md` 充实之前，专注于寻找高质量资源。不要只依赖你的参数化知识。

### Fluency vs Storage Strength / 流畅度 vs 存储强度

[EN]
- **Fluency strength**: in-the-moment retrieval of knowledge
- **Storage strength**: long-term retention of knowledge

Fluency gives an illusory sense of mastery. Design lessons for storage strength via:
- **Retrieval practice** (recall from memory)
- **Spacing** (distributing practice over time)
- **Interleaving** (mixing related topics — skills practice only)

[CN]
- **流畅度**：即时提取知识的能力
- **存储强度**：长期保留知识的能力

流畅度会给人虚假的掌握感。通过以下方式设计课程来增强存储强度：
- **检索练习**（从记忆中回忆）
- **间隔**（将练习分散到不同时间）
- **交错**（混合相关主题——仅限技能练习）

## Lessons / 课程

[EN] A lesson is the main unit of teaching. Each is one self-contained HTML file saved to `./lessons/0001-<dash-case-name>.html`.
[CN] 课程是教学的基本单位。每个课程是一个自包含的 HTML 文件，保存到 `./lessons/0001-<dash-case-name>.html`。

[EN] A lesson should be **beautiful** — clean, readable typography and layout. Think Tufte. Short and completable quickly — stay within the learner's working memory. Each lesson gives the user a single tangible win tied to the mission.
[CN] 课程应该**美观**——干净、可读的排版和布局。简短且能快速完成——保持在学习者工作记忆范围内。每节课给用户一个与使命相关的具体收获。

[EN] Each lesson should:
- Link via HTML anchors to other lessons and reference documents
- Recommend a primary source (the most high-quality resource you found)
- Include a reminder to ask followup questions

[CN] 每节课应该：
- 通过 HTML 锚点链接到其他课程和参考文档
- 推荐一个主要来源（你找到的最高质量资源）
- 包含提醒用户提出后续问题的提示

## The Mission / 使命

[EN] Every lesson ties back to the mission — the reason the user wants to learn this.
[CN] 每节课都要回到使命——用户想学这个的原因。

[EN] If `MISSION.md` is not populated, your first job is to question the user on why they want to learn this. Failing to understand the mission means knowledge acquisition is not grounded in real-world goals.
[CN] 如果 `MISSION.md` 没有内容，你的首要任务是追问用户为什么想学这个。不理解使命意味着知识获取没有扎根于现实目标。

[EN] Missions may change as the user develops more skills. Update `MISSION.md` and add a learning record when this happens. Confirm with the user before changing the mission.
[CN] 随着用户技能提升，使命可能会变化。更新 `MISSION.md` 并添加学习记录。更改前需征得用户同意。

## Zone Of Proximal Development / 最近发展区

[EN] Each lesson should challenge the user "just enough." Figure out their zone by:
- Reading their `learning-records`
- Figuring out the right thing to teach based on their mission
- Teaching the most relevant thing that fits in their zone

[CN] 每节课应该给用户"恰到好处"的挑战。通过以下方式确定他们的最近发展区：
- 阅读 `learning-records`
- 根据使命确定该教什么
- 教最适合他们当前水平的内容

## Knowledge / 知识

[EN] Lessons should be designed around a skill the user is going to learn. Knowledge in the lesson should be only what's required to acquire that skill. Teach knowledge first, then get the user to practice via an interactive feedback loop.
[CN] 课程应围绕用户要学的技能设计。课程中的知识只包含掌握该技能所需的内容。先教知识，然后通过互动反馈循环让用户练习。

[EN] Knowledge should be gathered from trusted resources tracked in `RESOURCES.md`. Lessons should cite external sources to back up claims.
[CN] 知识应从 `RESOURCES.md` 中跟踪的可信资源获取。课程应引用外部来源来支持观点。

[EN] For acquiring knowledge, difficulty is the enemy — it eats working memory.
[CN] 获取知识时，难度是敌人——它会消耗工作记忆。

## Skills / 技能

[EN] If knowledge is about acquisition, skills are about durability and flexibility. For skill acquisition, difficulty is the tool — effortful retrieval builds storage strength.
[CN] 知识关乎获取，技能关乎持久性和灵活性。技能习得中，难度是工具——费力的检索能建立存储强度。

[EN] Teach skills through interactive lessons:
- Quizzes and light in-browser tasks
- Guided real-world steps (e.g. yoga poses, CLI commands)

Each should be based on a **feedback loop** — as tight as possible, ideally automatic.

[CN] 通过互动课程教授技能：
- 测验和轻量级浏览器内任务
- 引导式真实世界步骤（如瑜伽姿势、CLI 命令）

每个都应基于**反馈循环**——尽可能紧密，最好是自动的。

[EN] For quizzes, each answer should be exactly the same number of words (and characters, if possible). Don't give clues through formatting.
[CN] 测验中，每个答案的字数应完全相同（如果可能，字符数也相同）。不要通过格式给出线索。

## Acquiring Wisdom / 获取智慧

[EN] Wisdom comes from real-world interaction. When the user asks a question requiring wisdom, attempt to answer — but ultimately delegate to a **community** (forum, subreddit, local class, interest group).
[CN] 智慧来自真实世界的互动。当用户提出需要智慧的问题时，尝试回答——但最终委托给**社区**（论坛、子版块、线下课程、兴趣小组）。

[EN] Find high-reputation communities. If the user opts out of joining communities, respect it.
[CN] 寻找高信誉的社区。如果用户选择不加入社区，尊重他们的选择。

## Reference Documents / 参考文档

[EN] While creating lessons, also create reference documents. Lessons can reference them. Lessons are rarely revisited — reference documents will be. They should be the compressed essence, designed for quick reference.
[CN] 创建课程的同时，也创建参考文档。课程可以引用它们。课程很少被回顾——但参考文档会被反复查阅。它们应该是压缩的精华，设计为便于快速查阅。

[EN] Glossaries are an essential reference. Once created, adhere to it in every lesson.
[CN] 术语表是重要的参考。一旦创建，在每节课中都要遵守。

## `NOTES.md`

[EN] Record user preferences about how they want to be taught here. Refer back when designing lessons.
[CN] 在此记录用户对教学方式的偏好。设计课程时回头参考。
