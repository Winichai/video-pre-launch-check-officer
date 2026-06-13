# 改造指南

这份文档用于记录这个 skill 最适合从哪里下手改。

## 最值得优化的地方

### 1. 追问风格

文件：`SKILL.md`、`references/dialogue-style.md`

可以调整它和用户说话的语气，比如更像导演、更像制片人、更像增长顾问，或者更适合中文短视频团队。

### 2. 问题库

文件：`references/question-bank.md`

这里决定它会怎么追问目标受众、平台、时长、素材、卖点和节奏。想让它更懂某个行业，优先改这里。

### 3. 工作流

文件：`references/workflow-0-1.md`、`references/workflow-iteration.md`

这里决定它是怎么从空白需求进入完整分镜，或者怎么修改已有 `video-spec.md`。

### 4. 输出格式

文件：`templates/video-spec-template.md`

如果你想让最终文档更适合 HyperFrames、剪辑师、客户评审或团队协作，改这里。

### 5. 渲染前预览审批

文件：`references/preview-approval.md`、`templates/preview-board-template.md`

这里决定它在真正生成视频前怎么给用户看分镜预览表，以及什么样的用户回复才算批准。

### 6. 视觉与组件规则

文件：`references/components-catalog.md`、`references/scene-breakdown.md`、`references/pacing-rules.md`

这里决定它会把镜头拆到多细、推荐什么画面组织方式，以及不同平台下节奏如何变化。

## 发布前检查

- `SKILL.md` 在仓库根目录。
- `SKILL.md` frontmatter 里有 `name` 和 `description`。
- `LICENSE` 保留原 MIT 许可证。
- `README.md` 的安装命令已经替换成你的 GitHub 用户名和仓库名。
- 用至少一个真实需求跑过，确认能生成可用的 `video-spec.md`。
- 确认 `preview-board.md` 会在 `/hyperframes` 前生成，并且用户没批准前不会启动渲染。
- 如果改了输出格式，确认 `templates/video-spec-template.md` 和 `references/spec-rules.md` 没有互相冲突。

## 命名建议

如果你想和原版并排使用，保留：

```yaml
name: video-pre-launch-check-officer
```

如果你想让它作为原版的替代品，改成：

```yaml
name: video-spec-builder
```

并排使用更适合开发期，替代原版更适合稳定后自用。
