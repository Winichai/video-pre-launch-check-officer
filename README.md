# Video Pre-Launch Check Officer

Video Pre-Launch Check Officer is a Codex skill for preparing videos before they are sent to HyperFrames.

It helps you turn a rough video idea into a usable production brief: purpose, audience, platform, assets, voiceover, visual direction, pacing, storyboard, and a clear `video-spec.md`. Before rendering, it adds one more checkpoint: a keyframe preview board for approval, so you can catch visual problems before HyperFrames spends time generating the video.

## What It Does

- Turns a vague video idea into a structured video brief.
- Checks the missing pieces before production: script, audio, footage, images, design references, aspect ratio, duration, and output format.
- Helps define the visual system before rendering: design style, typography, color, layout density, motion language, and components.
- Breaks the script into scenes with purpose, on-screen text, expected visuals, movement, transitions, and asset dependencies.
- Creates `video-spec.md` as the production handoff for HyperFrames.
- Creates a pre-render approval board before HyperFrames starts rendering.
- Requires approval before video generation, reducing expensive visual rework.

## Pre-Render Approval

The key feature is the checkpoint before rendering.

After the video spec and design direction are ready, the skill must generate:

- `preview-board.md`: a scene-by-scene approval table.
- Keyframe preview images when visual output is being prepared locally.
- A short explanation for each scene: what the image will look like and how it will move.

HyperFrames should not start generating the video until the user explicitly approves the preview board.

Approval means the user clearly says something like:

- `通过`
- `批准`
- `可以生成`
- `开始渲染`
- `OK 按这个做`

If the user asks for changes, the skill goes back and updates the spec, design notes, and preview board first.

## Workflow

1. The user describes the video they want to make.
2. The skill asks only for missing production-critical details.
3. The skill checks assets: script, voiceover, footage, images, data, 3D, references, and design rules.
4. The skill creates or updates `video-spec.md`.
5. The skill creates `preview-board.md` and keyframe preview guidance before rendering.
6. The user approves or requests changes.
7. Only after approval does the workflow move to HyperFrames rendering.

## Install

Install HyperFrames first, then install this skill:

```bash
npx skills add heygen-com/hyperframes
npx skills add Winichai/video-pre-launch-check-officer
```

If you make videos often, install globally:

```bash
npx skills add heygen-com/hyperframes -g
npx skills add Winichai/video-pre-launch-check-officer -g
```

After installation, restart Codex so the skill can be picked up.

## Files

```text
.
├── SKILL.md
├── templates/
│   ├── video-spec-template.md
│   └── preview-board-template.md
├── references/
│   ├── workflow-0-1.md
│   ├── workflow-iteration.md
│   ├── question-bank.md
│   ├── preview-approval.md
│   └── ...
├── examples/
├── docs/
├── CHANGELOG.md
├── LICENSE
└── README.md
```

## Attribution

This project is based on [`feicaiclub/video-spec-builder`](https://github.com/feicaiclub/video-spec-builder), licensed under the MIT License. The original license text is retained in `LICENSE`.
