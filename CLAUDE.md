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
