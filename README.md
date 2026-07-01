# Project Operating

面向软件项目的全流程 Codex Skill，用文件化状态管理把项目从模糊想法推进到上线，并支持多轮会话、多 Agent 接力。

## 适用场景

- 从一个模糊产品想法开始，逐步明确需求、视觉化、开发、部署。
- 接手一个已有项目，判断真实进度并继续推进。
- 在项目上下文中修复 bug、调整方向、记录决策。
- 让非技术用户也能通过用户验收方式判断功能是否完成。

## 核心流程

```text
orient -> requirements -> visualize -> engineer -> deploy -> handoff
```

横向动作：

```text
debug / change / status
```

## 项目文档

Skill 会按需在项目根目录维护这些文档：

- `ProjectState.md` - 当前阶段、目标、任务、验证状态和下一步。
- `Requirements.md` - 通过引导式对话澄清后的产品需求。
- `Design.md` - 视觉方向、界面原型规则、交互、动效和设计规范。
- `Tasks.md` - 可执行任务、用户验收方式、技术验证和实施日志。
- `Decisions.md` - 关键产品、技术、范围和方向决策。
- `Deployment.md` - 部署平台、环境变量、验证、监控、回滚和安全信息。
- `Summary.md` - 里程碑、项目收尾或交接总结。

## 安装

```bash
npx skills add https://github.com/MarshallZhang723/project-operating
```

也可以手动复制本仓库到 Codex skill 目录：

```bash
mkdir -p ~/.codex/skills/project-operating
cp -R . ~/.codex/skills/project-operating
```

## 使用

显式触发：

```text
使用 $project-operating：我想做一个交易复盘工具，从需求梳理开始，一直到上线。
```

常见触发方式：

```text
我有个产品想法，帮我从 0 做到上线。
```

```text
这个项目之前做了一半，你看看现在到哪了，然后继续。
```

```text
先做视觉原型，让我确认产品方向。
```

```text
按照这个计划开始实现。
```

```text
准备上线，帮我检查部署还缺什么。
```

## 设计原则

- 模糊需求不能直接脑补成最终文档，必须先通过引导式对话澄清。
- 有界面项目进入开发前，应先完成视觉化确认和 `Design.md`。
- 开发任务完成记录同时包含用户验收方式和技术验证结果。
- 重大需求、视觉、架构或部署变更必须追加到 `Decisions.md`。
- 只问进度时默认不改文件，先用文档和代码事实交叉验证真实状态。
