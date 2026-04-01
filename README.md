# NINJA SLASH — 忍斬

> ローグライクアクションゲーム。純粋なバニラJS。HTMLファイル1枚。ビルド不要。

**バージョン：** v1.1.1  
**ライブデモ：** [https://men0tai0ko.github.io/ninja-slash/](https://men0tai0ko.github.io/ninja-slash/)

---

## 概要

四方から迫り来る敵をタップ／クリックで斬る。  
コンボをつなぎ、パッシブスキルを選択し、できる限り生き残れ。

**スマホ縦持ちファースト**で設計。PCマウス操作にも完全対応。

---

## クイックスタート

```bash
git clone https://github.com/men0tai0ko/ninja-slash.git
cd ninja-slash
open index.html   # または任意のモダンブラウザにドラッグ＆ドロップ
```

依存ライブラリなし。ビルドプロセスなし。`index.html` がゲームのすべて。

---

## 機能一覧

| カテゴリ | 内容 |
|----------|------|
| **武器** | 刀（近距離・高威力）・手裏剣（遠距離・貫通）・鎌（範囲攻撃） |
| **ローグライクスキル** | スコアマイルストーンで3択パッシブスキル選択 |
| **ステージ演出** | スコア3,000・10,000で背景が自動変化 |
| **コンボBGM** | Web Audio APIによるコンボ数連動のBGM重畳（5／10／20コンボ） |
| **デイリーチャレンジ** | seed値による日替わりルール・localStorage記録 |
| **難易度** | 易（Easy）／普（Normal）／難（Hard） |
| **対応プラットフォーム** | スマホ（タッチ）＋デスクトップ（マウス） |

---

## 技術スタック

| レイヤー | 技術 |
|----------|------|
| 言語 | Vanilla JavaScript（ES6+） |
| グラフィクス | HTML5 Canvas API |
| 音声 | Web Audio API |
| レイアウト | CSS3（Flexbox・CSSカスタムプロパティ・メディアクエリ） |
| ストレージ | localStorage |
| 外部依存 | **なし** |

---

## プロジェクト構成

```
ninja-slash/
└── index.html          # ゲーム本体（HTML + CSS + JS、単一ファイル完結）
docs/
├── README.md           # このファイル — 概要・入口
├── spec.md             # ゲーム仕様・バランス値
├── architecture.md     # システム構造・データフロー
├── tasks.md            # 開発タスク・ロードマップ
└── issues.md           # 既知バグ・制限事項
```

---

## バージョニング

[セマンティックバージョニング](https://semver.org/)に準拠：

| 種別 | タイミング |
|------|-----------|
| PATCH（x.x.**1**） | バグ修正・小規模改善 |
| MINOR（x.**1**.x） | 後方互換の新機能追加 |
| MAJOR（**1**.x.x） | 破壊的変更 |

**変更履歴（チェンジログ）は `index.html` のファイルヘッダーコメントで管理する。**

---

## オンラインランキング（スタブ）

`index.html` 内の `OnlineRanking` は Supabase／Cloudflare Workers KV 向けのスタブとして実装済み。  
`OnlineRanking` IIFE 内の `API_BASE` を実際のURLに差し替えることで有効化できる。  
設定されるまでは通信が無音でスキップされる。ローカルランキングは独立して動作する。

---

## 関連ドキュメント

- [spec.md](spec.md) — ゲーム仕様全文・バランス値
- [architecture.md](architecture.md) — 状態機械・モジュール構成・データフロー
- [tasks.md](tasks.md) — ロードマップ・タスク状況
- [issues.md](issues.md) — 既知バグ・オープンイシュー
