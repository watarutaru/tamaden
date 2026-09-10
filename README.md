# たま電 プログラムページ

身内向け音楽イベント「たま電」当日用の、スマホで見るプログラム表（縦スクロール1枚）。

## 構成

- **`index.html`** … これ1ファイルで完結。サーバーに置けばそのまま表示できます。
- 外部依存は Google Fonts（`fonts.googleapis.com`）のCDN読み込みのみ。画像・ロゴ・アイコンはすべてHTML内に埋め込み済み（追加ファイル不要）。

## ホスティング

- 自前サーバー：`index.html` を公開ディレクトリに置くだけ。
- GitHub Pages を使う場合：リポジトリの Settings → Pages → Source を `main` / `/ (root)` にすると、
  `https://watarutaru.github.io/tamaden/` で公開されます。

## 編集ガイド

- **文言・出演者**：`index.html` の `<section>` や `.row` を直接書き換え。
  出演行の形式：`<div class="row"><div class="left"><span class="num">1</span><span class="name">団体名</span></div><span class="cat">UNIT</span></div>`
- **背景色など**：`<style>` 冒頭の `:root{ --bg: ... }` の変数を変更。
- **Discordリンク**：`<script>` 内の `GUILD` / `CHANNEL` のID、および `#discord` の `href`。
- **地図リンク**：AFTER PARTY の `.mapbtn` の `href`（Google Maps URLs 形式 `?api=1&query=店名`）。

## メモ

- スマホファースト。広い画面では中央に最大580px幅で表示。
- ヘッダーの GAIN / PRESSURE のツマミは、ドラッグ/スワイプで回せる飾り（動作には影響なし）。
- Discordボタンはスマホでアプリを優先起動し、未インストール等ではブラウザ版へ切り替わります。
- 見出し等に `text-box-trim`（上下トリミング）を使用。新しめのブラウザで最適表示になります。

---
元PR（開発経緯）: watarutaru/goods#6 から `git subtree split` で履歴ごと移送。
