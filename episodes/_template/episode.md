---
id: NNNN
title: ""
status: draft           # draft | sketching | inking | ready | published
season: S1              # S1 | S2 | S3 | S4 | S5+
arc: standalone         # standalone | main | bugmaru | seasonal | side
tags: []                # 例: [デバッグ, ひらめき]
characters: [shunta]    # 登場キャラ ID（lore/characters/ のファイル名と一致）
panels: ~               # 完成時のコマ数（ネタによって可変）
created: YYYY-MM-DD
published_at: ~
post_urls:
  x: ~
  instagram: ~
continues_from: ~       # 前話の id（連作の場合のみ）
---

# {{title}}

## 一行ログライン

（このエピソードを 1 行で。X 投稿のキャプション素案にもなる）

## ネタの核

- **何を見せたいか**:（読み終わった瞬間に残すもの）
- **オチのタイプ**: 意外な結末 / 発見 / 空回り / 無言 / メタ / その他
- **想定読了時間**: 5 秒 / 10 秒 / 30 秒 ぐらい

## 構成設計

> 1 話 = **画像 1 枚**。コマ数はネタ最適に決める（1 コマ〜可変）。
> 読み手が画面をスクロール／視線で追う動線を意識する。

- **コマ数**: N コマ（or 1 枚絵）
- **配置**: 縦長 / 横長 / グリッド / 不定形
- **緩急の山**:（どこで一番テンションが上がるか）
- **オチの位置**:（最後 / 中盤 / 全体で構成）

## コマ割り

> ネタごとに必要な数だけ書く。コマ数固定なし。
> 1 枚絵で完結するなら「コマ 1 のみ」でも OK。

### コマ 1
- 画: （何が描かれているか）
- 話者: 
- セリフ: 
- 効果音 / モノローグ: 

### コマ 2
- 画: 
- 話者: 
- セリフ: 

<!-- 必要なだけ追加 -->

---

## 完成画像

- `cover.png` ← X / Instagram 投稿用の **1 枚画像**

## ネーム / 下書き（任意）

`work/` 配下に sketch-1.png 〜 を置く。完成版だけリポに残したい場合は
`work/` を `.gitignore` してもよい。

## メモ・ボツ案

- 

---

## 画像生成プロンプト（任意 / ChatGPT 等）

画像生成 AI に渡すときの注意:

- 出力は **1 枚画像**。コマ割りも 1 枚の中で完結させる
- コマ数は本ファイルの「構成設計」に書いた数に合わせる
- 吹き出し / セリフのルール: [`../../design-system/speech-bubbles.md`](../../design-system/speech-bubbles.md)
  - `話者:` `吹き出し:` `キャラ名タグ:` の形式で各コマを書く
  - `シュンタ「セリフ」` のような書き方は **避ける**（吹き出しに「」ごと描かれる）
- リズム / 緩急の作り方: [`../../design-system/rhythm.md`](../../design-system/rhythm.md)
- カラーパレット: [`../../design-system/color-palette.md`](../../design-system/color-palette.md)
- **合成プロンプト (毎話使う)**:
  [`../../meta/image-prompts/episode/composition.md`](../../meta/image-prompts/episode/composition.md)
  を開いてシナリオ部分を埋め、ChatGPT に貼り付ける
- **リファレンス / フレームの一覧**:
  [`../../meta/image-prompts/README.md`](../../meta/image-prompts/README.md)
