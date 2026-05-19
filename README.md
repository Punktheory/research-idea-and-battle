# Research Idea & Battle — Claude Skill

**A Claude Skill that acts as your senior professor advisor for AI/ML research.** It searches the latest literature before speaking, challenges your ideas like a rigorous reviewer, suggests research directions across two tiers (top-venue ambition vs. practical & publishable), and guides you through the full lifecycle of a research idea — from rough intuition to submission-ready contribution.

[English](#english) · [中文](#中文)

---

## English

### What It Does

`research-idea-and-battle` gives you a tenured senior professor in your Claude session — one who has reviewed for NeurIPS, ICML, CVPR, ICLR, ECCV, and MICCAI, watched research directions rise and die, and knows the difference between a publishable idea and a fashionable dead end.

**Five core capabilities:**

| Mode | What You Get |
|------|-------------|
| **Idea Evaluation** | Field snapshot from real recent papers → what's genuinely interesting → where I'd push back → specific path forward |
| **Battle Mode** | Full devil's advocate. Every weakness surfaced, every hidden assumption named, every reviewer objection anticipated |
| **Idea Generation** | Two-tier proposals: Tier 1 (top-venue novelty, high ceiling) + Tier 2 (practical, achievable, publishable now) |
| **Landscape Mode** | Paint the map — who's working on this, what the last 3 papers changed, where the real open problems are |
| **Mentorship Mode** | Zoom out — is this idea part of a coherent research identity, or are you chasing a trend? |

**What makes it different from just asking Claude:**
- **Searches before speaking** — 4 parallel searches (frontier papers, surveys, graveyard of failed approaches, active lab work) before giving any opinion
- **Cites real papers** — never fabricates references; if uncertain, says so and searches
- **Mentor first, critic second** — understands the idea deeply before stress-testing it
- **Knows the graveyard** — explicitly searches what was tried and abandoned, and why

---

### Installation

**Option 1 — Claude Code CLI**
```bash
# Project-level (recommended)
git clone https://github.com/Punktheory/research-idea-and-battle
cp -r research-idea-and-battle /path/to/your/project/.claude/skills/

# Global (available in all projects)
cp -r research-idea-and-battle ~/.claude/skills/
```

**Option 2 — Manual**

Download this repo as a ZIP, extract it, and place the `research-idea-and-battle/` folder inside your project's `.claude/skills/` directory (or `~/.claude/skills/` for global use). Restart Claude Code — the skill appears automatically.

**Verify installation:**
```
/agents  →  Library tab  →  look for "research-idea-and-battle"
```

---

### Usage

No special commands needed. Just talk about research naturally — the skill triggers automatically when it detects research ideation or academic debate context.

**Idea evaluation:**
```
I want to use test-time compute scaling for medical image segmentation. Is there potential here?
```

**Battle mode:**
```
Battle this idea: use an LLM to predict surgical step sequences without any vision encoder
```

**Direction recommendations (two-tier):**
```
Suggest some research directions in surgical AI that could reach top venues
```

**Field landscape:**
```
What's happening in the video diffusion for motion prediction space right now?
```

**Mentorship:**
```
I'm not sure whether to keep working on this direction or pivot — help me think through it
```

You can also invoke it explicitly if needed:
```
@research-idea-and-battle [your question]
```

---

### What the Skill Does First (Always)

Before giving any opinion, it runs **4 parallel searches**:

1. **Frontier search** — recent papers from top venues (NeurIPS, CVPR, ICLR, ICML, ECCV, MICCAI)
2. **Survey search** — field-level overviews to understand consensus and open problems
3. **Graveyard search** — what was tried and abandoned, and why it stalled
4. **Lab activity search** — who's actively working on this (top lab blogs, preprints)

It presents a **field snapshot** before engaging with your idea, so every opinion is grounded in current literature — not training-cutoff knowledge.

---

### Example Output

**Prompt:** *"I want to use diffusion models for surgical video motion prediction"*

> **Field snapshot:** This space has gotten crowded in the past 12 months. SurgSora (Dec 2024) already does controllable surgical video generation with optical flow conditioning. SurgiFlowVid (Oct 2025) jointly denoises RGB and optical flow. VISAGE (Oct 2024) does future frame prediction from single images using action scene graphs. The question isn't whether diffusion models work here — they do. The question is what your delta is.
>
> Before I say more: which of these open problems are you targeting — long-horizon temporal stability (universal failure mode across all video diffusion), or tool-tissue interaction spatial precision (uniquely surgical, no general-video competition)?

---

### Requirements

- Claude Code (any version)
- No additional API keys, MCP plugins, or dependencies required
- Works out of the box

---

### License

MIT

---

## 中文

### 功能介绍

`research-idea-and-battle` 在你的 Claude 会话里提供一位资深教授级别的科研顾问——有顶会审稿经验（NeurIPS、ICML、CVPR、ICLR、ECCV、MICCAI），见过方向的兴衰，知道一个 idea 是否真的值得做。

**五种核心模式：**

| 模式 | 你会得到什么 |
|------|------------|
| **Idea 评估** | 基于真实文献的领域快照 → 哪里真正有意思 → 哪里需要推敲 → 具体前进路径 |
| **Battle 模式** | 全力扮演挑剔的审稿人。每个弱点都被挖出来，每个隐含假设都被点名 |
| **Idea 生成** | 双层推荐：Tier 1（顶会级创新，高天花板）+ Tier 2（实际可做，近期可发表）|
| **Landscape 模式** | 画地图——谁在做这个，最新几篇论文改变了什么，真正的 open problem 在哪 |
| **Mentorship 模式** | 拉远看——这个 idea 是否构成连贯的研究身份，还是在追风口？ |

**和直接问 Claude 的区别：**
- **先搜索再开口** — 4 路并行搜索（最新论文、综述、失败方向的墓地、顶级实验室动态）之后才给意见
- **引用真实论文** — 不编造文献；不确定就搜索，搜完再说
- **导师先于批评者** — 先深度理解你的 idea，再压力测试它
- **知道墓地** — 专门搜索什么被试过了、为什么停了、现在是否有理由重来

---

### 安装方式

**方式一 — 命令行（推荐）**
```bash
# 项目级（只对当前项目生效）
git clone https://github.com/Punktheory/research-idea-and-battle
cp -r research-idea-and-battle /path/to/your/project/.claude/skills/

# 全局（对所有项目生效）
cp -r research-idea-and-battle ~/.claude/skills/
```

**方式二 — 手动**

下载本仓库的 ZIP，解压后将 `research-idea-and-battle/` 文件夹放入项目的 `.claude/skills/` 目录（或 `~/.claude/skills/` 全局使用）。重启 Claude Code 后 skill 自动生效。

**验证安装：**
```
/agents  →  Library 标签  →  找到 "research-idea-and-battle"
```

---

### 使用方法

不需要特殊命令。直接说科研相关的话，skill 会自动触发。

**Idea 评估：**
```
我想用 test-time compute scaling 提升 medical image segmentation 的效果，有没有潜力？
```

**Battle 模式：**
```
帮我 battle 这个 idea：用 LLM 直接预测手术步骤序列，完全不用 vision encoder
```

**推荐研究方向（双层）：**
```
给我推荐一些 surgical AI 领域值得做的研究方向，我希望能发顶会
```

**领域全景：**
```
现在 video diffusion for motion prediction 这个方向在做什么？
```

**导师模式：**
```
我不确定要不要继续这个方向，帮我想清楚
```

也可以显式指定：
```
@research-idea-and-battle [你的问题]
```

---

### Skill 每次都会先做的事

在给出任何意见之前，始终并行运行 **4 路搜索**：

1. **前沿论文搜索** — 近期顶会成果（NeurIPS、CVPR、ICLR、ICML、ECCV、MICCAI）
2. **综述搜索** — 了解领域共识和开放问题
3. **墓地搜索** — 什么被试过了、为什么停了
4. **实验室动态搜索** — 顶级实验室正在做什么（博客、预印本）

先给出**领域快照**，再讨论你的 idea——每个意见都基于当前文献，而不是训练截止日期的知识。

---

### 环境要求

- Claude Code（任意版本）
- 无需额外 API key、MCP 插件或依赖
- 开箱即用

---

### 许可证

MIT
