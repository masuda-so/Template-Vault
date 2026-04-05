# Template Vault

[English version](README.md)

Obsidian 向けの、運用方針をあらかじめ備えたスターター Vault です。ノートの記録、継続的なレビュー、フォルダ運用と Bases ビューによる整理を始めやすくします。

## このプロジェクトでできること

このリポジトリは、そのまま使える Obsidian Vault テンプレートです。以下を含みます。

- アイデア、プロジェクト、参照情報、クリッピング、定期ノートのためのフォルダ構成
- Sandbox による Obsidian 学習用の導線とサンプル
- [Bases](Bases) 配下の `.base` ファイルによる、データベース風ビュー

個人ナレッジベース、日誌、プロジェクトハブとして使え、独自運用の土台にもできます。

## このプロジェクトが役立つ理由

- 始めやすい: 最初から用途別フォルダが分かれており、迷いにくい
- 習慣化しやすい: Daily / Weekly / Monthly でレビューサイクルを作りやすい
- 構造化しやすい: Books、People、Projects、Trips などの `.base` 定義が用意済み
- 学習しやすい: Sandbox にオンボーディングノートと書式例がある
- ローカルファースト: すべて Markdown で保存され、移植しやすく Git 管理しやすい

## Vault 構成

| パス | 用途 |
| --- | --- |
| [Daily](Daily) | 日次ノートと日々の記録 |
| [Weekly](Weekly) | 週次計画と週次レビュー |
| [Monthly](Monthly) | 月次計画と月次レビュー |
| [Projects](Projects) | 進行中プロジェクト |
| [Ideas](Ideas) | 検討中アイデア |
| [References](References) | 長期参照する知識ノート |
| [Clippings](Clippings) | 抜粋・ソース保存 |
| [Meta](Meta) | Vault 運用ルールや改善メモ |
| [Templates](Templates) | 各フォルダ向けの挿入用テンプレート |
| [Bases](Bases) | Obsidian Bases 定義 (`*.base`) |
| [Sandbox](Sandbox) | 学習ガイドと書式サンプル |
| [Canvases](Canvases) | 視覚的なキャンバス作業 |

## はじめ方

### 1. Vault を取得する

```bash
git clone https://github.com/masuda-so/Template-Vault.git
```

または ZIP をダウンロードして展開してください。

### 2. Obsidian でフォルダを開く

1. [Obsidian](https://obsidian.md/) をインストール
2. Open folder as vault を選択
3. このリポジトリのフォルダを指定

### 3. まずはオンボーディングノートを読む

- [ようこそ.md](ようこそ.md) — Vault ツアーと最初の 3 ステップが書かれています
- [Sandbox/Start here.md](Sandbox/Start%20here.md)
- [Sandbox/Guides/Get started with Obsidian.md](Sandbox/Guides/Get%20started%20with%20Obsidian.md)

### 4. Obsidian の Core Plugins を有効化する

**Settings → Core plugins** を開き、以下を ON にしてください。

| プラグイン | 役割 |
| --- | --- |
| **Templates** | `Templates/` フォルダのテンプレートをノートに挿入できるようになる |
| **Daily notes** | `Daily/` に日付ノートをワンクリックで作成できるようになる |
| **Bases** | `Bases/` の `.base` ファイルでノートをテーブル・カード表示できるようになる |

Templates を有効化したら、Settings → Templates → **Template folder location** に `Templates` と入力して保存してください。

### 5. フォルダ運用を始める

実用的な開始フロー:

1. まず [Ideas](Ideas) にメモを置く
2. 実行する内容は [Projects](Projects) に昇格
3. 根拠資料は [References](References) または [Clippings](Clippings) に保存
4. [Weekly](Weekly) と [Monthly](Monthly) で定期レビュー

### 6. Bases を活用する

[Bases](Bases) 配下に、Books / Music / People / Places / Projects / Recipes / Shows / Trips などの `.base` 定義があります。Obsidian で Bases 機能を有効にすると、表やカードで閲覧できます。

## `.obsidian/` の追跡方針

`.obsidian/` ディレクトリは、このリポジトリでは**追跡しない**方針です（`.gitignore` 参照）。

Obsidian の設定（テーマ、インストール済みプラグイン、ワークスペースレイアウト）はユーザーごと・デバイスごとに異なります。追跡すると、異なるマシンや Obsidian バージョンで使う複数のユーザー間でコンフリクトが起きます。

clone 後は、上記「はじめ方 → ステップ 4」に記載のプラグインを手動で有効化してください。

## `.claude/` ディレクトリについて

`.claude/` ディレクトリには、[Claude Code](https://claude.ai/code) の設定ファイル（スキル定義・プロンプトコンテキスト）が含まれています。このリポジトリの開発時に使用したものであり、Vault 構造改善に貢献する際に Claude Code を活用できるよう、意図的に追跡しています。

Claude Code を使用しない場合は、このディレクトリを無視して問題ありません。

## 利用例

以下は [.claude/skills](.claude/skills) の obsidian-skills 由来パターンをもとにした例です。

### 1. Obsidian Markdown ノート例

ウィキリンク、コールアウト、埋め込みを使ったノート:

```md
---
title: Project Alpha
date: 2024-01-15
tags:
  - project
  - active
status: in-progress
---

# Project Alpha

This project aims to [[improve workflow]] using modern techniques.

> [!important] Key Deadline
> The first milestone is due on ==January 30th==.

## Tasks

- [x] Initial planning
- [ ] Development phase
  - [ ] Backend implementation
  - [ ] Frontend design

## Notes

The algorithm uses $O(n \log n)$ sorting. See [[Algorithm Notes#Sorting]] for details.

![[Architecture Diagram.png|600]]
```

### 2. Bases ファイル例

[Bases](Bases) に置く `.base` ファイル例（例: `tasks.base`）:

```yaml
filters:
  and:
    - file.hasTag("task")
    - 'file.ext == "md"'

formulas:
  days_until_due: 'if(due, (date(due) - today()).days, "")'

views:
  - type: table
    name: "Active Tasks"
    filters:
      and:
        - 'status != "done"'
    order:
      - file.name
      - status
      - due
      - formula.days_until_due
```

### 3. JSON Canvas ファイル例

[Canvases](Canvases) に置く `.canvas` ファイル例（例: `research.canvas`）:

```json
{
  "nodes": [
    {
      "id": "8a9b0c1d2e3f4a5b",
      "type": "text",
      "x": 0,
      "y": 0,
      "width": 300,
      "height": 150,
      "text": "# Main Idea\\n\\nThis is the central concept."
    },
    {
      "id": "1a2b3c4d5e6f7a8b",
      "type": "text",
      "x": 400,
      "y": -100,
      "width": 250,
      "height": 100,
      "text": "## Supporting Point A\\n\\nDetails here."
    }
  ],
  "edges": [
    {
      "id": "3c4d5e6f7a8b9c0d",
      "fromNode": "8a9b0c1d2e3f4a5b",
      "fromSide": "right",
      "toNode": "1a2b3c4d5e6f7a8b",
      "toSide": "left"
    }
  ]
}
```

## ヘルプ・サポート

- まずは [Sandbox](Sandbox) のオンボーディングノートを確認
- 公式ヘルプ: https://help.obsidian.md/
- 書式例: [Sandbox/Formatting/Format your notes.md](Sandbox/Formatting/Format%20your%20notes.md)
- 問題報告: https://github.com/masuda-so/Template-Vault/issues

## メンテナとコントリビューション

このリポジトリは GitHub の `masuda-so` が管理しています。

コントリビューション歓迎です。特に以下の改善は価値があります。

- Vault 構造の分かりやすさ向上
- ノートテンプレート改善
- オンボーディング導線の改善
- Bases 定義の拡充

貢献手順:

1. リポジトリを Fork
2. 変更内容ごとのブランチを作成
3. 最小限で明確な更新を行う
4. 変更意図を添えて Pull Request を作成

大きな構造変更は、先に Issue で方針相談してください。

## サードパーティ表記

このリポジトリには kepano/obsidian-skills 由来の内容が含まれます。
必要な著作権表示および許諾表示は
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) に記載しており、関連する
内容のすべての複製または重要な部分に含める必要があります。
