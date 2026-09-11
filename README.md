# topic-skill

为 Obsidian 知识库生成按讨论触发度排序的 AI 日报的 Codex Skill。

## 它会产出什么

- 北京时间范围内、全量覆盖 AIHOT 精选并合并近 30 天讨论的 AI 日报
- Obsidian 总览中的当日入口链接

所有内容写入知识库的 `AI资讯` 目录。日报不显示来源和链接，而是以“发生了什么事 / 值得关注什么”呈现合并后的事件，并按最可能引发评论或讨论的顺序排列。

## 使用方式

将本仓库放入 Codex Skills 目录，例如：

```text
~/.codex/skills/topic-skill/
```

然后在包含 `.obsidian` 的知识库目录中请求：

```text
使用 topic-skill 生成今天的 AI 日报
```

Skill 会先检查 `last30days` 的安全诊断，再读取 AIHOT 当日资讯并取完所有精选条目。基础研究可用时继续执行；缺少 X、YouTube 等扩展来源时，只报告覆盖缺口，不会误报为未初始化。

## 依赖与边界

- 需要可用的 `last30days` 与 `aihot` Skill。
- AIHOT 用于当前新闻；`last30days` 用于近期真实讨论信号。
- 不读取或写入知识库中 `AI资讯` 目录以外的旧笔记。
- 不生成选题、素材包、口播稿或每周复盘，也不修改定时任务。

完整工作流见 [SKILL.md](SKILL.md)，文件格式见 [输出规范](references/output-spec.md)。

## 许可证

[MIT](LICENSE)
