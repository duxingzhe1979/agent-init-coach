# 初始化教练

给刚上手 Agent 工具的人的一份开箱配置：一次装好行为约束和三个基础技能，再给三条练习把人带进门。

## 这份包解决什么

大多数人第一次用 Agent，前三天都在踩同样的坑——AI 改了一堆没让改的文件、遇到看不懂的材料只会给摘要、每次做重复的事都从头讲一遍需求。

这个包把四件事一次做完：

| 项目 | 作用 | 装在哪 |
| --- | --- | --- |
| 卡帕西四原则 | 约束 AI 怎么做事：先想清楚、最小改动、只碰该碰的、给验证标准 | 用户级长期记忆，跨会话生效 |
| `skill-creator` | 把自己的重复流程写成技能 | 宿主内置则直接用 |
| `darwin-skill`（达尔文·花叔） | 给技能打分、提改进、只保留分数上涨的修改 | 用户级技能目录 |
| `help-me-understand`（帮我看懂） | 论文/报告/复杂方案看不懂时，按卡点给文字、图示或交互页 | 用户级技能目录 |

四原则是地基，另外三个是工具。只装工具不装约束，会更高效地把事情做歪。

## 怎么用

**方式一：让 Agent 自己装（推荐）**

把整个 `初始化教练` 文件夹（或压缩包）放到任意位置，然后对你的 Agent 说：

```
我拿到了「初始化教练」技能包，在 <这里换成你的实际路径>。
请先把它装到你的技能目录，然后按它的 SKILL.md 执行初始化，
最后给我一张验收表：每项是否可用、装在哪、怎么验证。
```

**方式二：手动装**

把 `初始化教练` 整个文件夹复制到你的用户级技能目录：

- WorkBuddy：`~/.workbuddy/skills/`
- Claude Code：`~/.claude/skills/`

然后说「用初始化教练给我做初始化」。

## 装完怎么验收

初始化会产出一张表，四项都要有路径和证据：

```
项目                    状态    路径                                    证据
卡帕西四原则             ✅      ~/.workbuddy/user-xxx/MEMORY.md         搜到四个原则名
skill-creator            ✅      内置                                    能读到 SKILL.md
darwin-skill             ✅      ~/.workbuddy/skills/darwin-skill         name: darwin-skill
help-me-understand       ✅      ~/.workbuddy/skills/help-me-understand   name: help-me-understand
```

真正的验收不在表格上，而在下一次对话：AI 不需要你再提醒，就按四原则做事了——先给计划、只改该改的、交付前自查。

## 装完先做这三件事

1. `用达尔文给初始化教练打个分` —— 看看 AI 怎么评估自己的工具链，顺便知道这个包还能怎么改
2. 丢一份你真的没看懂的材料，说 `帮我看懂` —— 体会「按卡点选形式」和「给一段摘要」的区别
3. `用 skill-creator 把我每周整理周报的流程做成技能` —— 第一次把自己的经验变成可复用资产

第三条最重要。学会造第一个技能之后，你会开始用另一种眼光看自己每天做的事。

## 目录结构

```
初始化教练/
├── SKILL.md                      # 执行流程与验收标准
├── README.md                     # 本文件
├── references/
│   ├── four-principles.md        # 四原则原文、记忆块、平台适配
│   └── platform-paths.md         # 各宿主路径对照与兜底
└── assets/                       # 离线可装的技能副本
    ├── darwin-skill/             # 达尔文 2.x（MIT，alchaincyf/花叔）
    └── help-me-understand/       # 帮我看懂
```

## 来源与授权

- **卡帕西四原则**：Andrej Karpathy 的工程实践，本文做了 Agent 场景迁移
- **darwin-skill**：花叔（alchaincyf）开源，MIT License，仓库 `github.com/alchaincyf/darwin-skill`，副本已保留 LICENSE
- **skill-creator**：Anthropic 官方 skills 仓库，多数宿主内置
- **help-me-understand**：随包分发，参考 STE（简化技术英语）表达原则，不构成 STE 合规认证
