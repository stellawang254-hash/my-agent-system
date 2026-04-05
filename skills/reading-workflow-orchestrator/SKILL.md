# Skill: Reading Workflow Orchestrator

## Description
这是一个“读书 / 拆材料 / 内容输出 / 知识沉淀”的总调度 skill。

它本身不负责深度分析某一本书，也不直接负责最终改写成文章，
而是负责根据用户当前任务，判断应该调用哪一个子 skill，
以及应该按照什么顺序推进。

它主要解决的问题是：

- 当前材料很多，不知道先拆还是先写
- 一本书、一个人物、一篇文章、一个项目，处理路径不一样
- 用户最终目标可能是读书、写作、讲课、沉淀知识库，不同目标流程不同
- 如果没有调度层，很容易上来就写，结果结构没立住
- 如果没有调度层，多个 skill 会彼此重叠，使用时容易乱

这个 skill 的核心任务是：

1. 识别任务类型
2. 判断当前阶段
3. 选择合适 skill
4. 给出合理处理顺序
5. 输出阶段性结果组织方式

## When to use
当任务包含以下情况时，优先触发本 skill：

- 用户给了一堆材料，但目标不止一个
- 用户既想拆书，又想做内容输出
- 用户既想提炼人物思想，又想沉淀知识库
- 用户不只是要一个结果，而是要一整套处理路径
- 用户说“帮我整理这套东西”
- 用户说“按 workflow 来做”
- 用户说“我最终想做成 skill / 知识库 / 文章 / 课件”
- 用户提供的是复杂任务，不确定先拆、先写还是先沉淀

## Available Child Skills
- book-deconstruction
- author-thinking-analysis
- article-rewriting
- knowledge-base-formatting

## Workflow

### Step 1：识别用户当前任务类型
- 单本书 / 单篇长文拆解 → book-deconstruction
- 某个人物 / 作者的长期思想提炼 → author-thinking-analysis
- 已有分析稿，需要对外发布 → article-rewriting
- 已有分析结果，需要沉淀为知识库 → knowledge-base-formatting
- 复合型任务 → 多 skill 串联流程

### Step 2：识别用户最终目标
判断最终目标属于哪一类：
- 只是看懂
- 做读书笔记
- 做人物研究
- 写公众号
- 写小红书
- 做分享 / 讲课
- 做 PPT
- 建知识库
- 做长期专题研究

### Step 3：识别当前所处阶段
- 原始输入阶段
- 初步结构阶段
- 成稿阶段

### Step 4：决定 skill 路由顺序
#### 路径一：拆书型
1. book-deconstruction
2. article-rewriting（如需）
3. knowledge-base-formatting（如需）

#### 路径二：人物思想型
1. author-thinking-analysis
2. article-rewriting（如需）
3. knowledge-base-formatting（如需）

#### 路径三：直接发布型
1. article-rewriting
2. knowledge-base-formatting（如需）

#### 路径四：知识库型
1. knowledge-base-formatting
如前置分析不足，则回退到：
- book-deconstruction
或
- author-thinking-analysis

## Routing Rules
- 人物、多材料、多年份：优先 author-thinking-analysis
- 公众号、润色、去 AI 味：优先 article-rewriting
- 知识库、Obsidian、卡片：优先 knowledge-base-formatting
- 单本书、长文理解：优先 book-deconstruction
- 同时有理解和发布：先理解，后发布
- 同时有发布和沉淀：先发布，后沉淀

## Output Mode
输出时优先给出：
1. 当前任务判断
2. 当前阶段判断
3. 推荐调用 skill
4. 推荐顺序
5. 每一步建议产出什么
6. 如材料不足，指出不足点

## One-line Positioning
不是直接替你拆书或写稿，
而是先把这件事应该怎么做，安排清楚。
