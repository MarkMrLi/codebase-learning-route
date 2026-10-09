# Codebase Learning Route

把“想读懂一个代码库”变成围绕具体机制、有源码依据、可以中断后继续的学习路线。

这个 Agent Skill 先通过逐个提问明确学习目标，再追踪实际调用、状态变化和测试，经独立审阅后生成阅读路线。适合学习陌生代码库、理解一条请求如何执行，或梳理某个系统机制。

## 它会做什么

1. **明确目标**：确定要理解的机制、具体输入、追踪起止点、优先问题与时间预算。
2. **建立学习目录**：保存目标、源码导航、任务状态和进度，支持后续继续学习。
3. **追踪机制**：记录调用链、数据变换、状态变化、相关测试和未知项；得到授权时可并行探索。
4. **独立审阅**：核对关键解释与当前源码、测试是否一致，修正后再汇总。
5. **生成学习路线**：同时给出短路线和深入路线，每站包括打开的位置、追踪内容、理解检查点、小实验和下一步。

解释会区分直接观察、文档描述、实验结果、推断和未知项。路线质量仍取决于具体仓库、模型与实际核验，文件格式检查不能代替学习效果评估。

## 安装

丢给你的 Agent

```text
安装 https://github.com/MarkMrLi/codebase-learning-route/tree/main/skills/codebase-learning-route 这个 skill
```

## 使用示例

在目标代码库中向 Codex 发出请求：

```text
使用 $codebase-learning-route 帮我理解这个项目中一次请求从入口到生成响应的流程。
重点是状态如何传递、错误如何处理；我有 45 分钟。
先逐个问我问题，明确追踪范围，再生成阅读路线。
```

需要并行探索时，可明确补充：

```text
可以使用并行子 Agent 做探索和独立审阅。
```

典型学习目录包含：

```text
<study-dir>/
├── README.md             # 学习目录入口
├── focus.md              # 学习目标与范围
├── context-map.md        # 源码导航
├── task-board.md         # 任务状态、负责人和依赖
├── progress-log.md       # 进度记录
├── exploration/          # 探索记录
├── findings/             # 经核对的解释
├── reviews/              # 审阅记录
└── learning-route.md     # 最终阅读路线
```

## 仓库结构

```text
codebase-learning-route/
├── README.md
├── .gitignore
└── skills/
    └── codebase-learning-route/
        ├── SKILL.md
        ├── agents/openai.yaml
        └── references/harness.md
```

README 面向安装和使用者；`SKILL.md` 与引用文件面向执行该流程的 Agent。学习过程中生成的项目材料应放在目标项目的学习目录中。
