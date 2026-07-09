# pm-skills

> 产品经理把重复劳动外包给 AI，把关键判断交给一支私人顾问团。

---

## 这是什么

20 个 Claude Code / Agent Skill，覆盖产品经理从"开个会"到"写复盘"的完整日常，也覆盖从"这个需求该不该做"到"怎么把方案打磨到足够扎实"的关键判断。

每一个 Skill 都在回答同一个问题：**这件事我每次都要重新想一遍，能不能让 AI 替我想？**

答案是可以。

这套仓库现在分成两类能力：

- **执行工具箱**：13 个生产型 Skill，帮你写 PRD、做路线图、设计实验、写埋点、复盘、拆竞品、生成原型。
- **专家顾问团**：7 个 Advisory Skill，把 Cagan、Teresa Torres、俞军，以及 Mom Test、Story Mapping、Escaping the Build Trap 这些专家视角和方法论请进评审会。

---

## 创作来源

产品经理的工作有个特点：**高度重复，但每次都感觉在从头开始**。

写 PRD 的结构每次都差不多，但每次都要重新想边界条件漏了哪些。排优先级的逻辑每次都是那几个框架，但每次都要花半天对齐认知。复盘报告的格式都固定了，但每次都要反复改行动项写得够不够具体。

这些摩擦加起来，就是每天下班晚两个小时的原因。

所以最早的 13 个 Skill 做的事情只有一件：**把摩擦消掉。**

但产品工作里还有另一类更贵的成本：**判断质量。**

功能看起来都合理，但哪个真的该做？用户说想要，但这是真需求还是客套话？团队做了很多功能，为什么 outcome 没变？PRD 写得再完整，如果前面的机会、风险、用户价值和战略连接没想清楚，最后只是更高效地做错事。

所以新增的专家顾问团解决另一件事：**把盲区照出来。**

---

## 20 个 Skill，一句话说清楚

### 执行工具箱：把产品日常做快

| Skill | 干什么 |
|-------|--------|
| `pm-prd-writer` | 把一段模糊的描述变成可以过评审的 PRD |
| `pm-review-board` | 模拟 6 个角色同时喷你的需求，提前发现问题 |
| `pm-prioritization-engine` | RICE/ICE/Kano 三套模型同时打分，需求排序不再拍脑袋 |
| `pm-roadmap-planner` | 输入目标和人力，输出带甘特图的路线图 |
| `pm-analytics` | 数据跌了→找原因→给建议，一套走完 |
| `pm-experiment-designer` | 实验假设、分流方案、样本量计算、止损规则一次搞定 |
| `pm-tracking-spec-writer` | 把用户链路拆成埋点事件，附带 QA 校验 SQL |
| `pm-survey-designer` | 从调研目标到问卷题目，每道题都对应一个假设 |
| `pm-competitor-deconstructor` | 四维拆解竞品，说清楚哪些能抄、哪些不能抄 |
| `pm-postmortem-writer` | 5-Why 归因 + 强制分级行动项，复盘报告写完能直接发 |
| `pm-image2proto` | 截图进去，可运行的 HTML 原型出来 |
| `pm-image2pencil` | 截图进去，Pencil 设计稿出来 |
| `pm-url2proto` | 网址进去，Next.js 本地项目出来 |

### 专家顾问团：把关键判断做深

| Skill | 类型 | 干什么 |
|-------|------|--------|
| `pm-advisory-suite/pm-advisory-board` | 总控入口 | 不知道该问谁时先找它，自动路由专家、组织多视角评审 |
| `pm-advisory-suite/pm-advisor-cagan` | 专家视角 | 用 Marty Cagan 的四大风险、赋能团队、discovery 视角审需求 |
| `pm-advisory-suite/pm-advisor-torres` | 专家视角 | 用 Teresa Torres 的持续发现、机会解决方案树、假设验证看方案 |
| `pm-advisory-suite/pm-advisor-yujun` | 专家视角 | 用俞军的用户价值公式、交易模型、决策效用算取舍 |
| `pm-advisory-suite/pm-method-mom-test` | 方法论 | 把访谈问题改成能挖出真实信号的问法 |
| `pm-advisory-suite/pm-method-story-mapping` | 方法论 | 把需求拆成故事地图，切出能发布的 MVP |
| `pm-advisory-suite/pm-method-build-trap` | 方法论 | 检查团队是不是掉进功能陷阱，并把战略连回 outcome |

---

## 怎么用

把任意一个文件夹放进 Claude Code 的 skills 目录：

```
~/.claude/skills/pm-prd-writer/
```

然后在 Claude Code 里说"写个需求文档"，它就知道该怎么做了。

如果你想用专家顾问团，可以把 `pm-advisory-suite/` 下面的 7 个子目录复制到 skills 目录，或者先只装 `pm-advisory-board`：

```
~/.claude/skills/pm-advisory-board/
```

常见触发方式：

- "让产品顾问团评审这个方案"
- "用 Cagan 的视角看看这个需求风险"
- "用 Torres 的机会树帮我拆一下"
- "用俞军的用户价值公式算算这个功能值不值得做"
- "用 Mom Test 改一下这份访谈提纲"
- "用 Story Mapping 切一个 MVP"
- "用 Build Trap 看看我们是不是在堆功能"

一条完整链路可以是：

`Mom Test 取真信号 → Torres 挂进机会树 → 俞军算用户价值和替换成本 → Story Mapping 切 MVP → Build Trap 连回 outcome → Cagan 复核四大风险和团队能力`

这时候，原来的执行型 Skill 接上后半程：

`pm-prd-writer 写 PRD → pm-review-board 预审 → pm-tracking-spec-writer 写埋点 → pm-experiment-designer 设计实验 → pm-postmortem-writer 做复盘`

---

## 一些真实反馈

**pm-review-board 是最能救命的一个。**
需求评审会上被喷，通常不是因为需求真的有大问题，而是因为某个角色的顾虑没被提前考虑到。这个 Skill 让你在评审会之前就把所有角色的问题过一遍，到了会上只需要确认，不需要现场救场。

**pm-experiment-designer 解决了一个长期问题。**
A/B 实验方案写出来容易，写对很难。样本量算没算够、止损规则定没定、判定标准是不是在实验开始前就定好了——这些细节之前全靠经验，现在有了检查清单。

**pm-prd-writer 的价值在补漏，不在写。**
PRD 的正文自己写其实不慢，慢的是反复被问"这个异常流程处理了吗""埋点需求呢""非功能需求没有"。这个 Skill 会在生成 PRD 之后自动补一遍，漏不了。

**pm-advisory-board 的价值在于让分歧提前出现。**
很多方案不是缺一个结论，而是缺一张分歧地图。Cagan 会问风险和团队，Torres 会问证据和机会，俞军会问用户价值和交易成本，三本方法论会把访谈、切片、战略落地补上。它不替你拍板，但会让你知道自己到底在赌什么。

**pm-method-mom-test 很适合放在所有用户访谈之前。**
很多访谈失败，不是因为用户不配合，而是因为问题天然诱导对方说好听话。这个 Skill 会把"你会不会用"改成"你上次怎么解决"，把想象拉回事实。

---

## 仍然需要你自己做的事

- 判断这个需求值不值得做
- 在评审会上回答"为什么是现在"
- 说服老板砍掉一个他最喜欢的功能
- 根据一手用户和业务上下文做最终决策
- 下班

AI 替代不了这些。但它可以让你在处理这些事情之前，不用在文档上浪费精力。

---

## 相关项目

- [career.skill](https://github.com/zephyrwang6/career.skill) — 不是产品经理？输入你的职业，AI 帮你拆一套属于你的 Skill 库

---

made with Claude Code，以及大量不想再手写 PRD 的下午
