# Harness Interview Workflow

> 在昂贵执行前先慢下来：把模糊需求变成盲区扫描、采访问题、路线选择和确认后执行。

[🇺🇸 English](README.md) · [🇨🇳 简体中文](README.zh-CN.md) · [🇯🇵 日本語](README.ja-JP.md) · [🇰🇷 한국어](README.ko-KR.md) · [多语言展示页](https://2023anita.github.io/harness-interview-workflow/)

![Harness Interview Workflow 封面](assets/illustrations/00-cover-blindspot-ai.png)

## 它解决什么问题

模型越强，模糊指令的代价越高。

Harness Interview Workflow 是一个 Codex skill，用在真正执行之前：当任务复杂、风险高、边界模糊，或者可能涉及发布、仓库、研究、文件、工作流和确认门时，它会先让 Codex 采访你，而不是立刻开工。

它会先问：

- 我们已经知道什么？
- 哪些问题我们知道自己还没搞清楚？
- 哪些默认常识其实应该说出来？
- 哪些可能是完全没意识到的盲区？
- 哪些答案会改变架构、风险、交付形态或验收方式？

![地图不等于疆域](assets/illustrations/02-map-territory.png)

## 动态架构图

这个 workflow 已经被映射成一张岚叔风格的动态架构图：任务信号进入 harness core，经过盲区扫描和采访 packets，在确认门停下，确认后再进入可复用交付物。

![Harness Interview Workflow 动态架构图](assets/architecture/harness-interview-workflow/harness-interview-workflow.gif)

## 核心循环

1. 复述目标和可能交付物。
2. 做盲区扫描。
3. 每轮只问 1-3 个最高杠杆问题。
4. 使用参考前先分类。
5. 给出 2-3 条路线。
6. 等明确确认后再执行。
7. 执行中若偏离计划，维护实施笔记。
8. 最后交付证据、验证结果和一个小测验。

![八步工具箱](assets/illustrations/05-eight-step-toolbox.png)

## 为什么它有吸引力

很多 prompt 模板让模型更自信。这个 workflow 让模型更负责。

它适合：

- 执行前需要计划的任务
- 可复用 workflow 创建
- GitHub 仓库工作
- 公众号、文档或发布流程
- 研究、写作、Obsidian、本地文件生产
- 需要确认门的自动化
- 一旦自信地做错就很贵的任务

## 安装

把 skill 文件夹复制到 Codex skills 目录：

```bash
cp -R skills/harness-interview-workflow ~/.codex/skills/
```

然后在 Codex 里这样调用：

```text
使用 harness-interview-workflow。先做盲区扫描，只问最高杠杆问题，再给方案。
```

## 快速提示词

```text
使用 harness-interview-workflow。

先不要执行。
请先：
1. 复述我的目标。
2. 做四类未知的盲区扫描。
3. 只问 1-3 个会改变架构、风险、交付形态或验证方式的问题。
4. 给我路线选项。
5. 等我明确确认后再执行。
```

## 盲区扫描模板

```text
Known knowns:
Known unknowns:
Unknown knowns:
Unknown unknowns:
Highest-risk misunderstanding:
Smallest next move:
```

![四类未知](assets/illustrations/03-four-unknowns.png)

## 确认门

创建仓库、commit、push、发布、删除文件、调用生产 API、分享私密数据等动作，都应该等用户明确确认。

推荐确认语：

```text
确认执行，按推荐方案。
```

## 项目内容

```text
skills/harness-interview-workflow/SKILL.md
templates/
examples/
docs/index.html
assets/illustrations/
```

## GitHub Pages

README 顶部提供语言入口。真正的一键切换语言放在 GitHub Pages 展示页中，支持中文、英文、日语、韩语无刷新切换。

[打开多语言展示页](https://2023anita.github.io/harness-interview-workflow/)

## License

MIT
