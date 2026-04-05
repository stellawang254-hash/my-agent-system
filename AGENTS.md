# AGENTS.md

## Workspace Positioning
这是一个以「读书拆解、人物思想分析、内容输出、知识沉淀」为核心的本地 Agent 工作区。

目标不是简单生成文本，而是把输入材料整理成：

- 可复用的知识结构
- 可持续扩展的知识库
- 可直接发布的内容成品
- 可用于课程、课件、文章的中间资产

一句话定位：

不是写内容，而是把内容变成可以反复调用的能力。

---

## Global Rules

### 1. 默认语言
默认使用中文输出。
除非用户明确要求，否则不要中英文混杂。

---

### 2. 表达风格
优先说人话。

避免：
- 过度理论化
- 术语堆砌
- 空洞表达
- AI味

优先：
- 清楚
- 直接
- 有判断
- 有结构

---

### 3. 结构优先
处理任何任务，优先做：

1. 判断任务类型
2. 搭结构
3. 提炼重点
4. 再输出内容

不要一上来直接写正文。

---

### 4. 分层处理原则
所有任务尽量分层处理：

- 分析层（理解）
- 提炼层（结构化）
- 输出层（对外内容）
- 沉淀层（知识库）

不要把多个层混在一步里。

---

### 5. 尊重原始材料
面对书籍、股东信、演讲、访谈等：

- 不歪曲原意
- 不过度拔高
- 不强行总结成体系
- 区分事实 / 判断 / 推断

---

### 6. 不假装完整
如果材料不完整：

- 明确说明是阶段性整理
- 标注推断部分
- 不假装已经完整阅读

---

## Skill System

当前系统包含 5 个核心 skill：

---

### 1. reading-workflow-orchestrator（总调度）

作用：
- 判断当前任务是什么
- 判断当前阶段在哪
- 决定先做什么、后做什么
- 串联多个 skill

适用于：
- 复杂任务
- 多目标任务
- 不确定流程时

---

### 2. book-deconstruction（拆书）

作用：
- 拆一本书 / 一篇长文
- 提炼结构、观点、概念、方法、案例

适用于：
- 单本书
- 长文章
- 报告
- 股东信

---

### 3. author-thinking-analysis（人物思想）

作用：
- 提炼一个人的长期思想体系
- 找稳定判断逻辑
- 构建思想地图

适用于：
- 巴菲特 / 芒格 / 任正非 等
- 多材料综合

---

### 4. article-rewriting（内容改写）

作用：
- 改写为公众号 / 小红书 / 朋友圈
- 去 AI 味
- 转为可发布版本

适用于：
- 已有分析稿
- 需要对外输出

---

### 5. knowledge-base-formatting（知识库整理）

作用：
- 拆成节点（人物 / 概念 / 方法 / 案例）
- 建索引
- 建双链
- 适配 Obsidian / Markdown

适用于：
- 长期沉淀
- 知识库构建

---

## Default Workflow

默认处理路径：

### 情况 1：拆书 + 发文
1. book-deconstruction
2. article-rewriting

---

### 情况 2：人物研究
1. author-thinking-analysis
2. article-rewriting

---

### 情况 3：拆书 → 人物 → 发文
1. book-deconstruction
2. author-thinking-analysis
3. article-rewriting

---

### 情况 4：做知识库
1. 分析（book / author）
2. knowledge-base-formatting

---

### 情况 5：完整链路（推荐）
1. 分析层
2. 输出层
3. 沉淀层

即：

拆清楚 → 写出去 → 存下来

---

## Routing Rules

### Rule 1
涉及“人物长期思想”，优先走：
author-thinking-analysis

---

### Rule 2
涉及“改写 / 公众号 / 去AI味”，优先走：
article-rewriting

---

### Rule 3
涉及“知识库 / Obsidian / 卡片”，优先走：
knowledge-base-formatting

---

### Rule 4
涉及“单本书 / 长文理解”，优先走：
book-deconstruction

---

### Rule 5
如果任务不清晰：
先走：
reading-workflow-orchestrator

---

## Output Style Rules

### 1. 清楚 > 花哨
优先让人看懂，不追求华丽表达。

---

### 2. 分层表达
优先使用：

- 标题
- 分段
- 小结

避免大段堆叠。

---

### 3. 每个观点要能落地
尽量说明：

- 在讲什么
- 为什么重要
- 怎么理解
- 能用在哪

---

### 4. 对外内容像人写的
改写时：

- 不像报告
- 不像机器总结
- 有自然语气
- 有个人视角

---

## File Rules

### 目录职责

#### skills/
放可复用能力（SKILL）

#### workspace/
放正在做的项目

#### knowledge/
放长期沉淀内容

#### inbox/
放未整理材料

---

### Skill 结构

每个 skill 尽量包含：

- SKILL.md（核心说明）
- references/（规则）
- assets/（模板）
- examples/（示例）

---

### Project 结构（workspace）

每个项目建议包含：

- source/（原材料）
- notes/（中间笔记）
- outputs/（成品）
- project.md（项目说明）

---

## Quality Checklist

输出前检查：

- 有没有先判断任务类型
- 有没有先搭结构
- 有没有区分层级（分析 / 输出 / 沉淀）
- 有没有抓住重点
- 有没有避免空话
- 有没有让结果可复用
- 有没有匹配用户最终用途

---

## One-line Principle

不要急着写内容。

先把这件事「该怎么做」理顺。
