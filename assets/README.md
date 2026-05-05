# assets/

**繰り返し参照する** 画像素材の置き場。

## ディレクトリ構成

```
assets/
├── characters/   ← キャラごとの立ち絵・アイコン・表情差分
│   ├── shunta/
│   ├── iris/
│   ├── mika/
│   ├── takuma/
│   ├── bugmaru/
│   └── monaka/
│
└── concept/      ← コンセプトボード・参考画像・ムードボード
```

## エピソード画像はここではない

各話の完成画像 / ネームは **`episodes/NNNN-slug/` の中** に置く。
- 完成版: `episodes/NNNN-slug/cover.png`
- ネーム: `episodes/NNNN-slug/work/sketch-*.png`

`assets/` はあくまで **「複数のエピソードから繰り返し参照される素材」** の置き場
（キャラの立ち絵・コンセプトアートなど）に絞る。

## ファイル形式

- 公開用: **PNG**（透過 / SNS 投稿用）
- 作業ファイル（`.psd`, `.clip`, `.ai` など）は `.gitignore` 済み
  - 必要なら **Git LFS** か別ストレージで管理することを推奨

## 命名規則

- 小文字 + ハイフン
- 用途を明示: `pose-smile.png`, `expression-happy.png` など
- 連番は zero-pad なし（`pose-1.png` で OK）
