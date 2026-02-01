# ComfyUI Local Setup

## Environment

- **Location**: `/Users/itarutomy/Documents/GitHub/oss/comfy/ComfyUI`
- **Python**: 3.12.12 (arm64, managed by uv)
- **PyTorch**: nightly (MPS enabled for Apple Silicon)
- **venv**: `.venv/` (created with `uv venv`)

## Quick Start

```bash
cd /Users/itarutomy/Documents/GitHub/oss/comfy/ComfyUI
source .venv/bin/activate
python main.py
```

Open http://127.0.0.1:8188 in browser.

## Python Execution (without activating venv)

```bash
/Users/itarutomy/Documents/GitHub/oss/comfy/ComfyUI/.venv/bin/python main.py
```

## Installing Packages

pip is available in the venv:

```bash
.venv/bin/python -m pip install <package>
```

## Custom Nodes

Installed in `custom_nodes/`:
- **ComfyUI-to-Python-Extension-Skill** — Converts ComfyUI workflows to Claude Code skills

## Skills

- **ComfyUI-to-Python-Extension-Skill**: `~/.claude/skills/ComfyUI-to-Python-Extension-Skill/`
  - `skill_config.json` has `comfyui_path` set to this directory
  - Use: Export workflow as API JSON from ComfyUI, then ask "convert to skill"

---

## Model Selection Guide

ユーザーの要求に応じて適切なモデルを選択してください：

### インストール済みモデル

| モデル | スタイル | 主な用途 | 特徴 |
|--------|----------|----------|------|
| **Pony Diffusion V6 XL** | 二次元（アニメ） | イラスト・アニメ調画像 | NSFW対応（Uncensored）、解剖描写・ポーズが優秀 |
| **Z-Image-Turbo** | 三次元（リアル） | リアルな写真・3Dレンダー | NSFW対応（Uncensored）、低VRAM対応、高速生成 |

### モデル選択フロー

```
ユーザーの要求
    │
    ├─「アニメ調」「イラスト」「二次元」
    │   └─→ Pony Diffusion V6 XL
    │       - プロンプト追加: "score_9, score_8_up"
    │       - Settings: Steps 30-50, CFG 7-9
    │
    └─「リアル」「三次元」「3D」「写真」
        └─→ Z-Image-Turbo
            - LoRA併用で高速化 (steps 4-8)
            - Settings: Steps 4-30, CFG 7-8
```

### プロンプト例

**Pony Diffusion V6 XL（アニメ調）:**
```
Positive: score_9, score_8_up, anime style, detailed anatomy, high quality, masterpiece
Negative: blurry, deformed, low quality, worst quality
```

**Z-Image-Turbo（リアル）:**
```
Positive: 3d render, photorealistic, detailed skin, realistic lighting, high quality
Negative: blurry, distorted, ugly, bad anatomy, low quality
```

### 動画用モデル（未インストール）

動画生成が必要な場合：

| モデル | スタイル | 主な用途 | 特徴 | ステータス |
|--------|----------|----------|------|----------|
| **AnimateDiff + Pony Diffusion V6 XL** | 二次元（アニメ） | アニメ調動画 | NSFW対応、滑らかなアニメーション、Motion LoRA対応 | 未ダウンロード |
| **WAN 2.2 Enhanced NSFW** | 三次元（リアル） | リアルな動画 | NSFW対応、Image-to-Video、高解像度、VRAM 16GB+推奨 | 未ダウンロード |

**注意**: 動画生成はVRAM 16GB以上推奨。AnimateDiffはComfyUI Managerから拡張をインストール必要。
