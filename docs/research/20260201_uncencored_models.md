# https://x.com/i/grok?conversation=2017815276491051326

2026年2月現在、ComfyUIでハイクオリティNSFWをローカル生成する場合、それぞれのカテゴリで最もおすすめのモデルを1つだけ厳選して紹介します（Civitai/コミュニティの人気・品質・NSFW適性に基づく）。

- **二次元（アニメスタイル）画像**：**Pony Diffusion V6 XL**（またはその最新fine-tune版）。  
  NSFWの二次元で圧倒的に強く、解剖描写・ポーズ・詳細が優秀。プロンプトに"score_9, score_8_up"などのPony専用タグを入れると最高品質に。Civitaiで最もダウンロードされ続けている定番。

- **三次元（リアルスタイル）画像**：**Z-Image**（Uncensored版）。  
  低VRAMでも超リアル肌質・照明・NSFW解剖が抜群で、2026年に入って急上昇中の最強候補。ComfyUIで直接ロードして使え、censored回避も優秀。

- **二次元（アニメスタイル）動画**：**AnimateDiff + Pony Diffusion V6 XLベース**。  
  AnimateDiff拡張を入れてPonyを基盤に。NSFWアニメーションの滑らかさと一貫性が最高レベル。Motion LoRAを追加するとさらにクオリティアップ。

- **三次元（リアルスタイル）動画**：**WAN 2.2 Enhanced NSFW**（img2vid専用版）。  
  ComfyUIでImage-to-Videoワークフローに最適。NSFWコンテンツの動き理解・滑らかさ・解像度が抜群で、Civitaiでトップ評価。テキストtoビデオも対応可。

これらをComfyUI Managerで必要なノード/拡張（AnimateDiff、SVDなど）をインストール後、Civitaiからモデルをダウンロードして使ってください。  
プロンプト例（共通）：positiveに"detailed anatomy, explicit, high quality, masterpiece"、negativeに"blurry, deformed, lowres"。  
ステップ30-50、CFG 7-9あたりから調整を。動画はVRAM16GB以上推奨です。