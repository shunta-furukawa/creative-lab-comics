# 画像生成プロンプト集 (Image Prompts)

> ChatGPT images (gpt-image) で漫画 1 枚を生成するためのプロンプト。
> **各ファイルは自己完結している** — 開いて全選択 → コピー → ChatGPT に貼るだけ。

## TL;DR (使い方 3 ステップ)

1. 下の表からファイルを 1 つ選ぶ
2. **ファイルを丸ごとコピー** (中身全部)
3. ChatGPT に貼り付けて画像を生成 → 指定の保存先に保存

複数の入力画像をまとめて使うのは **エピソード合成プロンプト** だけ。
それ以外は 1 ファイル = 1 プロンプト = 1 画像出力で完結する。

---

## ① リファレンス画像 (初回 1 回だけ生成)

キャラクターやラボ内装の "正" を決める画像。
**初回に 1 回ずつ全部生成** して `assets/` に保存しておけば、後はずっと使い回せる。

| ファイル                                                      | 内容                              | 出力サイズ | 保存先                                          |
| ------------------------------------------------------------- | --------------------------------- | ---------- | ----------------------------------------------- |
| [`references/01-char-shunta.md`](./references/01-char-shunta.md)     | シュンタのモデルシート             | 1536×1024 | `assets/characters/shunta/ref-sheet.png`        |
| [`references/02-char-iris.md`](./references/02-char-iris.md)         | アイリスのモデルシート             | 1536×1024 | `assets/characters/iris/ref-sheet.png`          |
| [`references/03-char-mika.md`](./references/03-char-mika.md)         | ミカのモデルシート                 | 1536×1024 | `assets/characters/mika/ref-sheet.png`          |
| [`references/04-char-takuma.md`](./references/04-char-takuma.md)     | タクマのモデルシート               | 1536×1024 | `assets/characters/takuma/ref-sheet.png`        |
| [`references/05-char-monaka.md`](./references/05-char-monaka.md)     | モナカのモデルシート               | 1536×1024 | `assets/characters/monaka/ref-sheet.png`        |
| [`references/06-char-bugmaru.md`](./references/06-char-bugmaru.md)   | バグまるのモデルシート             | 1536×1024 | `assets/characters/bugmaru/ref-sheet.png`       |
| [`references/07-lab-interior-wide.md`](./references/07-lab-interior-wide.md) | ラボ内装ワイドショット (5 ゾーン)  | 1536×1024 | `assets/concept/lab-interior-wide.png`          |
| [`references/08-lab-floor-plan.md`](./references/08-lab-floor-plan.md)       | ラボの俯瞰フロアプラン             | 1024×1024 | `assets/concept/lab-floor-plan.png`             |
| [`references/09-style-guide.md`](./references/09-style-guide.md)             | 色 / 線 / 吹き出しのスタイルボード | 1024×1536 | `assets/concept/style-guide.png`                |
| [`references/10-motif-catalog.md`](./references/10-motif-catalog.md)         | モチーフ・小道具のカタログ         | 1024×1536 | `assets/concept/motif-catalog.png`              |

---

## ② フレーム画像 (初回 1 回だけ生成)

エピソードの "コマ割りの土台" になる空白フレーム画像。
**よく使うフォーマットだけ生成** すれば OK (全部作る必要はない)。

| ファイル                                                          | コマ数 / 配置             | 出力サイズ | 保存先                                          |
| ----------------------------------------------------------------- | ------------------------- | ---------- | ----------------------------------------------- |
| [`frames/1koma-portrait.md`](./frames/1koma-portrait.md)         | 1 コマ・縦長              | 1024×1536 | `assets/concept/frames/1koma-portrait.png`      |
| [`frames/2koma-portrait.md`](./frames/2koma-portrait.md)         | 2 コマ縦                  | 1024×1536 | `assets/concept/frames/2koma-portrait.png`      |
| [`frames/3koma-portrait.md`](./frames/3koma-portrait.md)         | 3 コマ縦                  | 1024×1536 | `assets/concept/frames/3koma-portrait.png`      |
| [`frames/4koma-portrait.md`](./frames/4koma-portrait.md)         | **4 コマ縦古典 (推奨)**   | 1024×1536 | `assets/concept/frames/4koma-portrait.png`      |
| [`frames/6koma-grid.md`](./frames/6koma-grid.md)                 | 6 コマ 2×3 グリッド        | 1024×1536 | `assets/concept/frames/6koma-grid.png`          |
| [`frames/9koma-grid.md`](./frames/9koma-grid.md)                 | 9 コマ 3×3 グリッド        | 1024×1536 | `assets/concept/frames/9koma-grid.png`          |
| [`frames/freeform-a.md`](./frames/freeform-a.md)                 | 不定形 A (大ゴマ + 小 3)   | 1024×1536 | `assets/concept/frames/freeform-a.png`          |
| [`frames/freeform-b.md`](./frames/freeform-b.md)                 | 不定形 B (縦 2 + 大ゴマ)   | 1024×1536 | `assets/concept/frames/freeform-b.png`          |
| [`frames/1koma-square.md`](./frames/1koma-square.md)             | 1 コマ正方形 (Instagram)   | 1024×1024 | `assets/concept/frames/1koma-square.png`        |
| [`frames/4koma-landscape.md`](./frames/4koma-landscape.md)       | 4 コマ横長 (プレゼン用)    | 1536×1024 | `assets/concept/frames/4koma-landscape.png`     |

> **最初は `4koma-portrait.md` だけ作っておけば十分**。
> 必要になったら他のフレームを足す。

---

## ③ エピソード合成 (毎話やる)

各エピソードを生成するときに使う。

[`episode/composition.md`](./episode/composition.md)

ファイルを開いて、下半分の **「シナリオ」セクション** を該当エピソードの内容で埋める。
ChatGPT に **このプロンプト + 入力画像 (フレーム + キャラ refs + 必要に応じて内装)** を一緒に渡す。

---

## ネタとフレームの目安

| ネタの性質                       | おすすめフレーム                     |
| -------------------------------- | ------------------------------------ |
| 状況 1 枚で笑わせる              | `1koma-portrait` / `1koma-square`    |
| Before / After / 期待 vs 現実    | `2koma-portrait`                     |
| 短いボケツッコミ                 | `3koma-portrait`                     |
| 起承転結 / 迷ったらこれ          | **`4koma-portrait`**                 |
| 段取り・手順を見せる             | `6koma-grid`                         |
| 密度型・テンポで読ませる         | `9koma-grid`                         |
| 強い 1 コマ + リアクション       | `freeform-a`                         |
| 比較 → 結論大ゴマ                | `freeform-b`                         |
| 横長 (ブログ・プレゼン)          | `4koma-landscape`                    |

詳しくは [`../../design-system/rhythm.md`](../../design-system/rhythm.md) のリズム設計を参照。

---

## ディレクトリ構成

```
meta/image-prompts/
├── README.md                       ← このファイル (索引)
│
├── references/                     ← ① キャラ・内装・スタイルのリファレンス画像生成
│   ├── 01-char-shunta.md
│   ├── 02-char-iris.md
│   ├── 03-char-mika.md
│   ├── 04-char-takuma.md
│   ├── 05-char-monaka.md
│   ├── 06-char-bugmaru.md
│   ├── 07-lab-interior-wide.md
│   ├── 08-lab-floor-plan.md
│   ├── 09-style-guide.md
│   └── 10-motif-catalog.md
│
├── frames/                         ← ② コマ割りフレームの空白テンプレ生成
│   ├── 1koma-portrait.md
│   ├── 2koma-portrait.md
│   ├── 3koma-portrait.md
│   ├── 4koma-portrait.md           ← まずはこれだけ作れば OK
│   ├── 6koma-grid.md
│   ├── 9koma-grid.md
│   ├── freeform-a.md
│   ├── freeform-b.md
│   ├── 1koma-square.md
│   └── 4koma-landscape.md
│
└── episode/                        ← ③ エピソードごとの合成プロンプト
    └── composition.md              ← シナリオ部分を埋めて使う
```

---

## メモ・コツ

- **キャラ 6 人ぶんは 1 体ずつ別々に生成**する。まとめて指示するとディテールが崩れやすい
- **同じ ChatGPT スレッドで生成し続ける** とキャラの一貫性が保ちやすい
- **生成後に必ずチェック**: 既存企業のロゴ / バグまるの口 / モナカの人語 などが混入していないか
- 気に入った構図が出たら **そのまま `assets/` にコミット**。差し替えはまた PR で

## 関連ドキュメント

- カラーパレット: [`../../design-system/color-palette.md`](../../design-system/color-palette.md)
- シェイプ・ライン: [`../../design-system/shapes-and-lines.md`](../../design-system/shapes-and-lines.md)
- モチーフ: [`../../design-system/motifs.md`](../../design-system/motifs.md)
- 吹き出しルール: [`../../design-system/speech-bubbles.md`](../../design-system/speech-bubbles.md)
- リズム設計: [`../../design-system/rhythm.md`](../../design-system/rhythm.md)
- ワークフロー: [`../workflow.md`](../workflow.md)
