# Github分析雷达

一个面向非技术用户的 GitHub 项目分析 Skill（可以理解成：交给 Codex 的一套固定工作方法）。

它不只总结 README，而是通过仓库文档、配置和少量关键源码，回答四个更实用的问题：

- 这个项目解决什么现实问题；
- 它大致怎么工作；
- 你能不能直接使用，应该接入现有流程的哪一步；
- 最小验证怎么做，看到什么结果才算真的用上。

## 主要特点

- 默认先做快速分析，避免一开始就陷入大量源码；
- 重要结论区分“已确认、合理推断、暂未确认”；
- 默认只读，不安装依赖（项目运行需要的工具包）、不运行陌生代码；
- 必须给出使用结论、最快体验、接入位置、最小复用和最小验证；
- 用户明确要求后，才围绕一个具体问题继续深入源码；
- 只有用户要求保存或生成网页时，才创建 HTML 报告。

## 安装方法

在 Mac 的“终端”中运行：

```bash
git clone https://github.com/kellyjiao-Kelly/github-analysis-radar.git ~/.codex/skills/github-analysis-radar
```

安装后，新建一个 Codex 任务，让 Codex 重新读取本地 Skill。

## 使用方法

把 GitHub 仓库链接和你的问题一起发给 Codex，例如：

```text
使用 $github-analysis-radar 分析这个项目：
https://github.com/owner/repository

请告诉我它解决什么问题、我怎么实际用上，并给出最小验证步骤。
```

也可以分析本地项目目录、README 或部分源码：

```text
使用 $github-analysis-radar 分析这个本地项目：
/你的项目绝对路径
```

需要继续深入时，可以指定一个问题：

```text
继续深入：这个项目的核心数据是怎样流转的？请用源码验证。
```

## 输出内容

一次完整的快速分析通常包括：

1. 它解决什么问题；
2. 它怎么解决；
3. 最值得认识的核心部分；
4. 最值得学习的设计；
5. 怎么真正用上；
6. 推荐先读哪些文件；
7. 证据位置和暂未确认的边界。

## 文件说明

```text
github-analysis-radar/
├── SKILL.md                          # 主工作流程
├── agents/openai.yaml                # Codex 中的名称和默认提示词
├── references/evidence-and-safety.md # 证据、安全、版本和许可证规则
├── references/report-structure.md    # 快速与深度分析的报告结构
└── assets/report-template.html       # 用户要求网页报告时使用的模板
```

## 使用边界

这个 Skill 用于帮助你理解和判断项目，不代表项目本身已经安全、可运行或适合商用。安装依赖、执行陌生代码、配置密钥或投入正式业务前，仍应先做可回退的小范围验证。
