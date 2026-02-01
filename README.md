# comfy

ComfyUIを使った画像生成・実験プロジェクト。

## 構造

```
comfy/
├── .claude/           # Claude Code設定
├── CLAUDE.md          # ComfyUIセットアップ手順
├── docs/              # リサーチノート
├── ComfyUI/           # ComfyUI本体（OSS、git submodule）
├── workflows/         # 保存したワークフロー（予定）
└── outputs/           # 生成画像へのシンボリックリンク（予定）
```

## セットアップ

```bash
# ComfyUI submoduleの初期化
git submodule update --init --recursive

# ComfyUIの起動
cd ComfyUI
source .venv/bin/activate
python main.py
```

ブラウザで http://127.0.0.1:8188 を開く。

## インストール済みモデル

| モデル | サイズ | 用途 |
|--------|--------|------|
| Pony Diffusion V6 XL | 6.5GB | アニメ/イラスト |
| Z-Image-Turbo | 11.4GB | 高速・リアル |

## インストール済みカスタムノード

- ComfyUI-Manager
- ComfyUI-to-Python-Extension-Skill

## 参考資料

- [ComfyUI GitHub](https://github.com/comfyanonymous/ComfyUI)
- [Civitai](https://civitai.com/)
