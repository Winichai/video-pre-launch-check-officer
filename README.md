# Video Pre-Launch Check Officer

这是一个基于 [feicaiclub/video-spec-builder](https://github.com/feicaiclub/video-spec-builder) 的个人改造版 Codex skill 项目。

目标是保留原 skill 的核心能力，同时强化“渲染前检查”：先把视频需求、设计范式、分镜脚本和预览表过一遍，用户批准后再交给 HyperFrames 生成视频。

## 当前状态

- skill 名称已改为 `video-pre-launch-check-officer`，显示名为 Video Pre-Launch Check Officer，避免和已安装的原版 `video-spec-builder` 冲突。
- 原始 README 已保留在 `docs/README.upstream.md` 和 `docs/README.upstream.zh.md`。
- 原始 MIT License 已保留。发布到自己的 GitHub 时请继续保留 `LICENSE`。
- 仓库根目录保留 `SKILL.md`，方便 `npx skills add <your-github>/<repo>` 直接安装。
- 已加入渲染前预览审批：生成 `video-spec.md` 后先生成 `preview-board.md`，用户批准后再启动 HyperFrames。

## 目录结构

```text
.
├── SKILL.md                  # skill 入口和核心行为说明
├── templates/                # video-spec.md 输出模板
├── references/               # 工作流、追问库、节奏规则、组件目录
├── examples/                 # 示例 video-spec
├── spec-mono/                # 视觉主题示例
├── Full Code/                # 原项目附带的完整组件代码
├── docs/                     # 上游 README 和改造文档
├── CHANGELOG.md              # 记录你的改造历史
├── LICENSE                   # MIT 许可证
└── README.md                 # 当前仓库首页
```

## 推荐改造顺序

1. 先改 `SKILL.md` 里的追问风格、工作原则和输出要求。
2. 再改 `references/question-bank.md`、`references/workflow-0-1.md`、`references/workflow-iteration.md`。
3. 如果你要改变最终文档格式，再改 `templates/video-spec-template.md`。
4. 如果你要调整渲染前审批方式，改 `references/preview-approval.md` 和 `templates/preview-board-template.md`。
5. 每次改完，用一个真实的视频需求测试它能不能产出稳定的 `video-spec.md` 和 `preview-board.md`。
6. 把变更写进 `CHANGELOG.md`，方便以后回滚或对比。

## 上传到自己的 GitHub

在这个目录中创建 GitHub 仓库后，可以按下面的方式发布：

```powershell
git init
git add .
git commit -m "Create video pre-launch check officer skill"
git branch -M main
git remote add origin https://github.com/<your-name>/video-pre-launch-check-officer.git
git push -u origin main
```

上传后，安装你的版本：

```powershell
npx skills add <your-name>/video-pre-launch-check-officer
```

安装后重启 Codex，让新 skill 生效。

## 如果想覆盖原版名称

当前 `SKILL.md` 使用 `name: video-pre-launch-check-officer`。如果你希望它替代原版，而不是并排存在，可以把名称改回：

```yaml
name: video-spec-builder
```

这样做前建议先备份或删除本机已安装的原版，避免安装时目录名冲突。

## Attribution

This project is based on `feicaiclub/video-spec-builder`, licensed under the MIT License. The original license text is retained in `LICENSE`.
