# Content Strategy — From Talk to Slides

## The Core Constraint: Slides Per Minute

Use this formula to set expectations before the outline:

| Duration | Total slides (guidance) | Pace |
|---|---|---|
| 15 min | 10–14 | Fast, one idea per slide, minimal reading |
| 30 min | 18–24 | Moderate, some slides carry more weight |
| 40–45 min | 24–32 | Room for image showcases and build-up |
| 60 min | 32–45 | Can afford detailed walkthroughs |

**Rule of thumb:** 1–1.5 minutes per content slide. Section dividers and the cover/closing count as ~30 seconds each. A 40-minute talk with 4 sections and a cover + close lands around 28–32 slides total.

If the user has more content than the duration allows, help them cut. It's better to do fewer ideas well than rush through all of them.

---

## Slide Architecture from an Outline

Given a talk structure (e.g., 4 parts with rough time allocations), build the outline like this:

```
Cover (1 slide)
Agenda / 今天聊什么 (1 slide)

Part 1 — [Title] (~N slides)
  Section divider (1)
  [Content slides]

Part 2 — [Title] (~N slides)
  Section divider (1)
  [Content slides]

...

Closing / Q&A / 谢谢 (1–2 slides)
```

The agenda slide serves double duty: it previews the structure AND acts as a cognitive anchor the audience returns to mentally throughout the talk.

---

## Translating Speaking Notes into Slides

The user will often give you a paragraph of speaking ideas — a mix of what they want to *say* and what they want to *show*. Your job is to separate these:

- **What goes on the slide:** the claim, the structure, the data point, the visual
- **What stays in the speaker's head (or notes):** the story, the context, the "why this matters"

### The One-Idea Rule
Each content slide should deliver exactly one idea. If a slide needs two headers, it should probably be two slides. The title of the slide should be the *conclusion*, not the *topic*:

```
Weak title (topic): "AI 的能力变化"
Strong title (conclusion): "AI 能干的活，每 7 个月翻一倍"
```

A strong title means someone can skim the deck and still understand the argument.

### Turning a Story into a Slide

When the user gives you a case study or anecdote (e.g., "I want to talk about how we used a Skill to do survey deployment"), convert it like this:

1. **Title = the payoff** of the story ("输入研究目的 → 自动生成题目 → 一键投放腾讯问卷")
2. **Body = the structure** that makes the payoff believable (input → process → output, or before/after)
3. **Visual = the evidence** (screenshot of the output, or a placeholder if the screenshot isn't ready)

The story itself — the context, the surprise, the human moment — is for the speaker to deliver verbally. The slide just provides the skeleton.

### Turning Data into a Slide

When the user gives you a specific number or research finding (e.g., "METR研究发现，AI 能处理的任务时长每 7 个月翻倍"):

1. **Make the number the hero** — large font, prominent position
2. **Source is mandatory** — small, below the number ("— METR 研究数据")
3. **One interpretation line** — what this means for the audience ("以前需要等 AI 够强才考虑的工作，现在可以规划了")

Avoid surrounding the key number with too much text. White space amplifies impact.

### Turning a Comparison into a Slide

When the user wants to contrast two things (e.g., Chatbot vs Agent):

- Use the **two-column layout** from `core-patterns.md`
- Left = the "before" / familiar thing (lighter card)
- Right = the "after" / new thing (dark card with accent border — signals this is where attention should go)
- A single VS divider in the center guides the eye
- Keep bullet points parallel in structure across both columns

### Turning a Process into a Slide

When the user has a sequence of steps (e.g., "研究策划 → 访谈设计 → 数据采集 → 分析 → 报告"):

- Use a **horizontal timeline** or **numbered card row**
- 3–5 steps is the visual sweet spot — more than 5 and it gets hard to scan
- Highlight the step the talk is currently focused on (accent background color)
- Each step card: step number + step name + 1-line description

---

## Slide Density by Content Type

Some slides earn more time than others. Here's a rough calibration:

| Content type | Time on screen | Why |
|---|---|---|
| Section divider | 15–30 sec | Just signals a transition |
| "Setup" context slide | 30–60 sec | Audience reads fast, speaker bridges |
| Data / argument slide | 60–90 sec | Audience needs to absorb + speaker explains |
| Image showcase / screenshot | 60–120 sec | Walkthrough takes time |
| Comparison (2-column) | 90–120 sec | Two things to process |
| Multi-step process | 60–90 sec | Build-up if animating, quick if static |

Use this to sanity-check the outline: sum up the estimated times, see if it fits the duration.

---

## Handling "I Have More Content Than Time"

This is the most common problem. Help the user prioritize:

1. **Must-have slides:** the core argument, the key evidence, the call to action
2. **Nice-to-have slides:** supporting examples, extra case studies, appendix material
3. **Cut completely:** context the audience likely already knows, slides that exist only to be thorough

Suggest moving cut content to an appendix section at the end of the deck — it's available for Q&A but doesn't eat into the talk.

---

## Handling Placeholder Screenshots

When the user mentions a screenshot they want to include but haven't provided yet:

1. Build a **placeholder box** (light gray fill, dashed border, italic label in the center)
2. Note the image key in a comment: `// TODO: replace placeholder with actual screenshot`
3. Make the bounding box the right proportion for the expected content (browser screenshot → 16:9, mobile → portrait, etc.)

This lets the user review the deck structure before hunting down all the screenshots.

```js
// Placeholder pattern
slide.addShape(pres.ShapeType.rect, {
  x: 0.4, y: 1.1, w: 9.2, h: 4.1,
  fill: { color: "EAE6E0" }, line: { color: "D4CBC0", width: 1, dashType: "dash" },
});
slide.addText("[ 截图占位：描述内容 ]", {
  x: 0.4, y: 2.8, w: 9.2, h: 0.6,
  fontSize: 17, color: "A89880", fontFace: F,
  align: "center", italic: true, margin: 0,
});
```

---

## Audience Calibration

The target audience changes almost everything about content density and framing:

| Audience | Implication |
|---|---|
| **同行 / 专业同类** | Skip basics, go deep on mechanism and nuance |
| **同公司跨部门** | Explain domain terms, lead with "why this matters for your work" |
| **管理层 / 决策者** | Lead with implications and decisions, keep technical detail minimal |
| **外部公开 / 行业活动** | Assume no prior context, invest in setup slides |
| **混合** | Design for the least-informed, create "depth layers" (main slide + optional deep-dive) |

For the 《从Chatbot到Agent》 talk (用研从业者, 40 min):
- Audience: practitioners who use AI tools daily but may not know the agent/chatbot distinction technically
- Approach: start from their felt experience (AI 变强的感受), build up vocabulary, land on practical takeaways
- Avoid: pure tech jargon without grounding, theoretical framing without examples

---

## Deck-Level Narrative Arc

选择弧线是做 PPT 最先要确定的事之一——它决定了分区结构、情绪节奏、以及哪种类型的听众会被打动。以下是六种经典弧线，每种都有它最擅长的场景。

---

### ① 英雄之旅 (Hero's Journey)
**情绪曲线：** 出发 → 遭遇挑战 → 低谷/顿悟 → 蜕变归来

**适合：** 公司/产品创业故事、个人成长经历、团队复盘（有过真实困难的）

**结构模板：**
```
1. 起点：我们/我在哪里（平静的世界）
2. 触发：发生了什么，打破了平衡
3. 挣扎：尝试过什么、为什么失败、最难的时刻
4. 顿悟：关键的转折点或洞察
5. 蜕变：做了什么不同的事
6. 收获：结果 + 对观众的启示
```

**讲者注意：** 情绪驱动的弧线，低谷段必须够真实才有说服力。如果"挣扎"部分被轻描淡写，观众不会被打动。顿悟要具体，不能只说"我们想明白了"。

---

### ② 问题—解方 (Problem → Solution)
**情绪曲线：** 制造紧张 → 释放紧张

**适合：** 路演、商业提案、产品发布、内部项目立项汇报

**结构模板：**
```
1. 痛点放大：让观众感受到问题有多真实、多普遍、多昂贵
2. 现有方案的不足：为什么已有的解法不够好
3. 解方登场：你的答案是什么
4. 证据：为什么这个解方有效（数据、案例、演示）
5. 行动号召：观众下一步该做什么
```

**关键：** "痛点放大"要够痛，否则解方显得多余。用真实数据或具体场景描述痛苦，不要用抽象的"效率低下"。

---

### ③ 钻石结构 / 金字塔原理 (Pyramid Principle)
**情绪曲线：** 平稳推进，逻辑驱动，无起伏

**适合：** 高管汇报、咨询提案、决策型会议、需要快速传达结论的场景

**结构模板：**
```
1. 结论先行：一句话说清楚你要什么/建议什么
2. 支柱论点1：支持结论的第一个理由 + 证据
3. 支柱论点2：支持结论的第二个理由 + 证据
4. 支柱论点3：支持结论的第三个理由 + 证据
5. 重申结论 + 下一步行动
```

**关键：** 结构越严谨，故事性越弱。适合"决策方听众"（已经信任你，只需要数据佐证），不适合"需要被说服的听众"（他们需要情感共鸣才会改变立场）。

---

### ④ 世界改变了 (The World Has Changed)
**情绪曲线：** 震撼/焦虑 → 理解 → 行动方向

**适合：** AI/技术趋势分享、行业转型判断、"为什么现在做这件事"的说明

**结构模板：**
```
1. 断层：展示一个"过去"和"现在"的鲜明对比，让观众感受到世界已经不同了
2. 为什么变了：驱动变化的底层力量（技术、政策、用户行为）
3. 输家和赢家：不适应的人/公司/方式会怎样
4. 你的方案是新世界的入场券：用你的方法/产品才能抓住新机会
5. 行动：现在该做什么
```

**关键：** "断层"要有具体数据或故事，不能只说"AI 发展很快"。《从Chatbot到Agent》用的就是这个弧线——用"能力每7个月翻倍"做断层，用 MCP/A2A/Skills 说明基础设施已成形，用 OpenClaw 出现说明入场券已经有了。

---

### ⑤ Sparkline（南希·杜阿尔特框架）
**情绪曲线：** 现实与理想反复拉锯 → 理想最终胜出

**适合：** TED 级演讲、激励型分享、变革动员、需要让观众"感受到落差痛苦"然后主动改变的场景

**结构模板：**
```
现实（What Is）  ←→  理想（What Could Be）
现实（困难）     ←→  理想（突破）
现实（现状局限） ←→  理想（用新工具之后）
...重复对比拉锯...
最终：以理想胜出、呼吁行动收尾（"New Bliss"）
```

**关键：** 不是简单的"前后对比"——而是**反复拉锯**，让落差感在演讲全程持续积累。每次回到"现实"都更让人难受，每次展示"理想"都更让人向往。结尾必须留给"理想"，不能以现实收场。

**幻灯片设计提示：** 用两种视觉语调交替出现：现实段用偏灰/冷的色调，理想段用暖色/强调色。结尾 slide 用全幅强调色收尾。

---

### ⑥ 三幕剧 (Three-Act Structure)
**情绪曲线：** 铺垫 → 冲突 → 释然

**适合：** 最通用的叙事容器。用研报告、培训课程、案例分享、项目复盘都能套用。

**结构模板：**
```
第一幕（铺垫/Setup）：
  - 介绍背景、人物、情境
  - 给信息，建立理解

第二幕（冲突/Confrontation）：
  - 核心矛盾或挑战
  - 尝试与失败，或困境深化
  - 给张力，激发关注

第三幕（解决/Resolution）：
  - 方案出现，冲突化解
  - 结果与启示
  - 给释然，引向行动
```

**关键：** 第二幕冲突要够真实，才能让第三幕的解决有意义。如果直接从铺垫跳到解决，观众不会觉得解决方案来之不易，也不会真正被打动。

---

## 弧线选择指南

| 场景 | 推荐弧线 |
|---|---|
| 创业/产品路演 | ② 问题—解方 |
| AI/行业趋势分享 | ④ 世界改变了 |
| 个人成长/公司故事 | ① 英雄之旅 |
| 高管汇报/咨询提案 | ③ 钻石结构 |
| TED 式激励演讲 | ⑤ Sparkline |
| 用研报告/培训/案例分享 | ⑥ 三幕剧 |
| 想要最大灵活性 | ⑥ 三幕剧（最通用容器）|

**一个实用判断方法：** 问自己"我想让观众听完之后*做*什么还是*感受*什么"。如果是做决策 → 钻石结构；如果是感受震撼然后行动 → Sparkline 或世界改变了；如果是理解一个复杂情况 → 三幕剧；如果是信任你这个人 → 英雄之旅。

**无论选哪种弧线：** 确保弧线在分区标题里可见，不能只在讲者脑子里。观众应该能从幻灯片标题重建整个论点。
