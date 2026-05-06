# エピソード

各話の脚本・ネーム・公開状況を管理する場所。

## フォーマット

**1 話 = 画像 1 枚**。コマ数はネタごとに最適化する（固定コマ数なし）。
1 枚で必ず 1 回オチをつけ、SNS 投稿時もこの 1 枚を添付する。

リズム設計 / 緩急の作り方は [`../design-system/rhythm.md`](../design-system/rhythm.md) を参照。

## ディレクトリ構成

各エピソードは **1 話 = 1 フォルダ** にする。脚本・完成画像・下書きを co-locate。

```
episodes/
├── README.md
├── _template/                 ← 新規エピソード用テンプレ
│   ├── episode.md             ← 脚本・コマ割り・メモのテンプレ
│   └── compose.md             ← 画像生成プロンプトのテンプレ (コピペ用)
└── NNNN-slug/
    ├── episode.md             ← 脚本・コマ割り・メモ
    ├── compose.md             ← ChatGPT に丸ごとコピペで投げるプロンプト
    ├── cover.png              ← 完成版 1 枚画像（SNS 投稿用）
    └── work/                  ← ネーム / 下書き（任意・公開しなくてよい）
        └── sketch-*.png
```

> **`compose.md` の役割**: フレーム + キャラ refs を ChatGPT に添付した上で、
> このファイルを **丸ごとコピペで貼るだけ** で 1 話ぶんの画像が生成できる。
> 元テンプレ: [`../meta/image-prompts/episode/composition.md`](../meta/image-prompts/episode/composition.md)

### 命名ルール

- フォルダ名: `NNNN-slug`
  - `NNNN`: 4 桁の通し番号（公開順 or 作成順、運用は緩く）
  - `slug`: 内容を表す英小文字スラッグ（例: `bugmaru-debut`）
- 完成画像は **必ず `cover.png`** に統一（フォルダ名から一意に辿れる）

## status の意味

| status      | 意味                                       |
| ----------- | ------------------------------------------ |
| `draft`     | プロット段階。コマ割り / セリフ未確定      |
| `sketching` | ネーム作業中                               |
| `inking`    | 下書き → 清書                              |
| `ready`     | 公開準備完了。投稿待ち                     |
| `published` | 公開済                                     |

## season / arc

front matter に必ず入れる。連載構造はこれで束ねる。

| キー      | 値                                                       |
| --------- | -------------------------------------------------------- |
| `season`  | `S1` 〜 `S4` (`S5+` 以降は決まり次第)                     |
| `arc`     | `standalone` / `main` / `bugmaru` / `seasonal` / `side`  |

詳しい構造は [`../lore/storyline/`](../lore/storyline/) を参照。

## 連作の扱い

エピソード間のつながりは可。ただし **1 枚で必ず 1 回オチる** こと。
連作の場合は front matter に `continues_from: NNNN` を入れて辿れるようにする。

## 新規エピソードの作り方

```bash
cp -r episodes/_template episodes/0001-your-slug
# episode.md を編集 → compose.md のシナリオ部分を埋める
# → ネーム → 清書 (or compose.md を ChatGPT に投げて生成) → cover.png を置く
```

詳しいフローは [`../meta/workflow.md`](../meta/workflow.md) を参照。

## 一覧

| 番号 | スラッグ                  | タイトル                              | season | arc        | status |
| ---- | ------------------------- | ------------------------------------- | ------ | ---------- | ------ |
| 0001 | monaka-asa-no-sanpo       | 朝の散歩、いつもの儀式                 | S1     | standalone | ready  |
| 0002 | iris-kidou                | コーヒーが鳴ると、アイリスが起きる    | S1     | standalone | draft  |
| 0003 | design-battle             | それ、ダサくない？                    | S1     | main       | draft  |
| 0004 | bugmaru-houga             | コードの隅で、何かが動いた             | S1     | bugmaru    | draft  |
| 0005 | atode-yaru                | 「あとで」の塔                         | S1     | standalone | draft  |
