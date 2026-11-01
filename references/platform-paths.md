# 宿主识别与路径对照

安装前先把三个位置找出来：**用户级技能目录**、**用户级长期记忆文件**、**内置技能目录**。三者定位错了，装完等于没装。

## 一、先识别宿主

看用户主目录下有哪些工具痕迹：

```bash
# macOS / Linux
ls -a ~ | grep -E '^\.(workbuddy|claude|codex|cursor|gemini)'
# Windows (Git Bash)
ls -a "$USERPROFILE" | grep -E '^\.(workbuddy|claude|codex|cursor|gemini)'
```

命中的目录决定用哪一行路径。多个命中时按用户当前会话实际使用的工具选，不要一次往所有工具里写。

## 二、路径对照表

| 宿主 | 用户级技能目录 | 用户级长期记忆 | 内置技能 |
| --- | --- | --- | --- |
| **WorkBuddy** | `~/.workbuddy/skills/` | `~/.workbuddy/user-*-personal/MEMORY.md`（工作区级另有 `<workspace>/.workbuddy/memory/MEMORY.md`） | 应用目录下 `resources/plugins/workbuddy-builtin/skills/`，含 `skill-creator` |
| **Claude Code** | `~/.claude/skills/`（项目级 `<project>/.claude/skills/`） | `~/.claude/CLAUDE.md`（项目级 `./CLAUDE.md`） | 无内置，`skill-creator` 需另装 |
| **Codex / 其他** | 以宿主文档为准 | 以宿主文档为准 | 先查再答，不猜 |

Windows 下 `~` 展开为 `%USERPROFILE%`，路径分隔符用 `/` 在 Git Bash 中可直接使用。

## 三、记忆文件的两种粒度

- **用户级**（跨项目生效）：四原则应该写这里，因为它是「AI 怎么做事」的通用约束
- **工作区级**：只在当前项目生效，适合项目约定，不适合通用行为约束

两者都存在时，写用户级；只有工作区级时，写工作区级并把这点告诉用户——换项目就失效了。

## 四、定位不到的兜底

宿主不认识、目录结构变了、或没有写权限时：

1. 写到本技能目录旁的 `PRINCIPLES.md`
2. 明确告知绝对路径
3. 告诉用户「这份约束不会自动生效，需要在你的工具里引用它」

不要因为找不到标准路径就跳过这一步——四原则是这个初始化包里唯一会改变日常行为的部分，另外三件只是工具。
