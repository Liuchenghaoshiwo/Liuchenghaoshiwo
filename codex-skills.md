# Codex Skills 收藏清单

更新时间：2026-04-22

这份清单优先收藏官方 OpenAI skills，因为可安装性、文档结构和安全边界更清楚。第三方仓库先作为发现入口，不建议直接安装陌生 skill；安装前应阅读 `SKILL.md`、脚本和依赖。

## 官方 OpenAI skills

来源：[openai/skills](https://github.com/openai/skills) - 官方 Codex Skills Catalog。

| Skill | 链接 | 适合做什么 | 推荐理由 |
| --- | --- | --- | --- |
| `skill-installer` | https://github.com/openai/skills/blob/main/skills/.system/skill-installer/SKILL.md | 安装 curated / experimental / GitHub URL skills | 管理 skills 的基础工具，适合先掌握 |
| `skill-creator` | https://github.com/openai/skills/blob/main/skills/.system/skill-creator/SKILL.md | 创建或更新自己的 skill | 如果你想把常用工作流沉淀成可复用能力，这是起点 |
| `cli-creator` | https://github.com/openai/skills/blob/main/skills/.curated/cli-creator/SKILL.md | 把 API、后台系统、脚本封装成稳定 CLI | 对自动化和内部工具很有价值 |
| `chatgpt-apps` | https://github.com/openai/skills/blob/main/skills/.curated/chatgpt-apps/SKILL.md | 构建 ChatGPT Apps SDK 应用 | 适合做 MCP server + widget UI 的项目 |
| `frontend-skill` | https://github.com/openai/skills/blob/main/skills/.curated/frontend-skill/SKILL.md | 构建更高质量的网页、App UI、原型 | 对前端视觉、信息层级、动效有明确约束 |
| `playwright-interactive` | https://github.com/openai/skills/blob/main/skills/.curated/playwright-interactive/SKILL.md | 用真实浏览器测试网页和 Electron 应用 | 适合交互验证、截图检查、端到端 QA |
| `develop-web-game` | https://github.com/openai/skills/blob/main/skills/.curated/develop-web-game/SKILL.md | 开发和迭代 HTML/JS 网页游戏 | 提供实现、操作、暂停、观察、修正的测试循环 |
| `pdf` | https://github.com/openai/skills/blob/main/skills/.curated/pdf/SKILL.md | 读取、生成、审查 PDF | 强调渲染验证，适合正式文档和排版敏感任务 |
| `doc` | https://github.com/openai/skills/blob/main/skills/.curated/doc/SKILL.md | 读取、创建、编辑 `.docx` | 适合合同、报告、简历、正式 Word 文档 |
| `speech` | https://github.com/openai/skills/blob/main/skills/.curated/speech/SKILL.md | 生成旁白、语音提示、批量 TTS | 适合产品演示、无障碍朗读、IVR 音频 |
| `security-threat-model` | https://github.com/openai/skills/blob/main/skills/.curated/security-threat-model/SKILL.md | 对代码库做威胁建模 | 适合 AppSec、架构评审、上线前风险梳理 |
| `linear` | https://github.com/openai/skills/blob/main/skills/.curated/linear/SKILL.md | 管理 Linear issue、项目和团队工作流 | 如果你使用 Linear，这类工具型 skill 很实用 |

## 第三方发现入口

| 仓库 | 链接 | 用途 |
| --- | --- | --- |
| Awesome Agent Skills | https://github.com/skillmatic-ai/awesome-agent-skills | 学习 Agent Skills 概念和发现更多资源 |
| Kodus Awesome Agent Skills | https://github.com/kodustech/awesome-agent-skills | 按前端、后端、DevOps、测试、安全等分类找技能 |
| VoltAgent Awesome Agent Skills | https://github.com/VoltAgent/awesome-agent-skills | 另一个社区索引，可用来交叉发现 |
| Everything Claude Code | https://github.com/affaan-m/everything-claude-code | 偏 Claude Code 生态，但有些 workflow 思路可参考 |

## 建议安装顺序

1. 先熟悉 `skill-installer` 和 `skill-creator`。
2. 如果经常写前端，优先看 `frontend-skill`、`playwright-interactive`、`develop-web-game`。
3. 如果经常处理文件，优先看 `pdf`、`doc`。
4. 如果要做内部自动化，优先看 `cli-creator`。
5. 如果要做安全或上线审查，优先看 `security-threat-model`。

## 安全检查

安装第三方 skill 前，至少检查：

- `SKILL.md` 是否清楚说明触发条件和工作流。
- 是否包含会执行 shell、下载依赖、读取密钥、访问网络的脚本。
- 是否要求 API key、token、cookie、私有仓库权限。
- 是否有不必要的写文件、删文件、推送代码、发请求行为。
- 是否能先在临时目录或 sandbox 中试运行。

## 安装提示

在 Codex 里可以用 `$skill-installer` 安装官方 curated skills，例如：

```text
$skill-installer install pdf
$skill-installer install frontend-skill
$skill-installer install cli-creator
```

安装后通常需要重启 Codex 才会加载新 skill。
