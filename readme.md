## settings.json 配置

> https://code.claude.com/docs/zh-CN/settings
> sk-b2d4d413a92345e5851652328320cf0b
> 写在.claude/settings.json 里，claude 会自动读取。

### settings配置

放在项目.claude/settings.json 里，claude 会自动读取。

> https://github.com/ChrisWiles/claude-code-showcase

> https://gist.github.com/ranaroussi/42b7c319e1e36be39b554b66e8fba3cb

https://github.com/multica-ai/andrej-karpathy-skills

全局配置（影响所有项目）
└── ~/.claude/settings.json

项目级配置（只影响当前项目）
└── 项目根目录/.claude/settings.json

项目上下文文件（告诉AI项目背景信息）
└── 项目根目录/CLAUDE.md ← 最重要！

| 层级         | 路径                   | 作用范围       | 适合写什么                                                         |
| ------------ | ---------------------- | -------------- | ------------------------------------------------------------------ |
| **全局级**   | `~/.claude/CLAUDE.md`  | 所有项目都会读 | 个人习惯、身份、翻译偏好（如"永远用中文回答"、"我是 xx、从事 xx"） |
| **项目级**   | 项目根目录/`CLAUDE.md` | 仅本项目       | 项目技术栈、架构、规范、进度（可提交 Git，团队共享）               |
| **文件夹级** | 子目录/`CLAUDE.md`     | 仅该子目录     | 模块专属约定（如 `src/payment/CLAUDE.md` 写支付模块踩过的坑）      |

三层叠加生效，不冲突。优先级：文件夹级 > 项目级 > 全局级。

**两个官方推荐的创建姿势：**

- **`/init` 创建项目级**：在项目根目录下运行 `claude` 后输入 `/init`，cc 会自动扫描项目并生成一份 CLAUDE.md 初稿，你再调整。官方建议：**项目有一定规模再 `/init` 效果更好**（太空它扫不出什么东西）。
- **`/memory` 编辑全局级**：在 cc 会话里输入 `/memory` 选择“全局 CLAUDE.md”，会用默认编辑器打开该文件供你修改。**修改全局后需重启 cc 才生效。**

# CLAUDE.md

https://github.com/multica-ai/andrej-karpathy-skills/blob/main/CLAUDE.md

# Skills

- https://github.com/anthropics/skills

- https://github.com/vercel-labs/skills

### 例子 安装 skill-creator

> 可以 用 vercel 的 npx 安装 要装的时候去官网看 不推荐直接用claude code 安装 要更项目走

```bash
npx skills find skill-creator
npx skills add anthropics/skills@skill-creator
# Local path
npx skills add ./my-local-skills
```

npx skills 最终安装到 .agent/skills
Skill 安装成了 Agent Skills 标准目录， VS Code 能用，Claude Code CLI 找不到
Copy-Item -Recurse .agent\skills\xxx .claude\skills\

```bash
/plugin marketplace add anthropics/skills
/plugin install skill-creator@anthropic-agent-skills
/plugin
```

插件安装后的 Skill 通常由 Claude Code 管理，不要求把源文件放进当前项目。

### 使用

使用 skill-creator 创建一个新的 用于review cobol代码 的Skill

#### 4.2.4 社区 Skill 库

除了官方库，社区贡献了大量 Skill 资源：

**精选 GitHub 仓库：**

| 仓库                                 | Skill 数量 | 特色                               |
| ------------------------------------ | ---------- | ---------------------------------- |
| **ComposioHQ/awesome-claude-skills** | 127+       | 10大分类，含59个SaaS应用集成Skill  |
| **alirezarezvani/claude-skills**     | 235+       | 9大领域，含25个POWERFUL级高级Skill |
| **travisvn/awesome-claude-skills**   | 持续更新   | 精选列表，社区投票排名             |
| **glebis/claude-skills**             | 专项       | 专注特定工作流的高质量Skill        |

**alirezarezvani/claude-skills 领域覆盖（235+ Skill）：**

#### 4.2.5 Skill 聚合平台

如果觉得逐个找仓库太麻烦，还有专门的 Skill 聚合搜索平台：

| 平台               | 地址                    | Skill 数量 | 特色                            |
| ------------------ | ----------------------- | ---------- | ------------------------------- |
| **skills.sh**      | https://skills.sh       | 48,000+    | Vercel 官方推荐的发现平台       |
| **SkillsMP**       | https://skillsmp.com/zh | 900,000+   | 最大的 Skill 市场，支持中文界面 |
| **AgentSkills.io** | https://agentskills.io  | 开放标准   | Agent Skills 开放标准定义       |

在这些平台上，你可以按分类浏览、按关键词搜索，找到需要的 Skill 后一键安装。

# Skill 聚合平台

**前端大佬 上班没事做的时候可以看下打发时间** (行末两个空格换行)  
https://github.com/mattpocock/skills
