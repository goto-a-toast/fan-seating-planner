# 扇型座席レイアウト作成

ステージ中心を扇の要として座席を円弧状に配置し、現場で椅子を並べるためのマーキング表まで出力するツールです。

## 公開ページ

https://goto-a-toast.github.io/fan-seating-planner/

## 使い方

ブラウザで上記の URL を開くだけで使えます。インストールやサーバーは不要です。

- 左のパネルに公演名・ステージ寸法・列数・座席寸法などを入力すると、右側の座席図がその場で描き直されます。
- 座席図は SVG ファイルとして書き出せます。
- マーキング表は現場での椅子出し用の数値表です。

## 公開の仕組み（初回のみ手動設定が必要）

`main` ブランチへの push で、`.github/workflows/deploy-pages.yml` が GitHub Pages へ自動公開します。

ただし **リポジトリで一度だけ Pages を有効化する操作が必要** です。ワークフローに渡されるトークンには Pages を新規作成する権限が無いため、自動化できません。

1. リポジトリの **Settings** → 左メニューの **Pages** を開く
2. **Build and deployment** の **Source** を **GitHub Actions** に変更する

この設定後は、`main` への push だけで自動的に公開が更新されます。

## 構成

- `index.html` — アプリ本体。HTML・CSS・JavaScript がこの1ファイルにすべて入っており、外部ライブラリは使っていません。
- `.github/workflows/deploy-pages.yml` — `main` ブランチへの push で GitHub Pages に自動公開するワークフロー。

## ローカルで動かす

`index.html` をブラウザで直接開けば動きます。
