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
