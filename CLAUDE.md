# tamaden リポジトリ運用ルール（Claude Code向け）

このリポジトリは身内向け音楽イベント「たま電」の当日プログラムページ。
`main` ブランチ / ルートの `index.html` を **GitHub Pages で本番公開**している
（公開URL: https://watarutaru.github.io/tamaden/ ）。

## ブランチ運用（C運用：軽量フロー）

アカウント共通の `git-flow-strategy` スキルに準拠しつつ、本リポジトリは小規模のため
`develop` を使わない軽量運用とする。

- `main` = 本番（Pages公開）。**直接コミット・直接pushは禁止**。
- すべての変更は **`feature/<名前>` ブランチ**を切って作業する
  （命名は英小文字・ハイフン区切り。例: `feature/fix-lineup`）。
- 変更完了後、**base を `main` にして Pull Request を作成**する
  （このリポジトリでは `main` への直PRを許可＝C運用）。
- PR作成後は **`pr-review` スキルでレビュー**し、ユーザーにマージ可否を確認してからマージする。
- コミットメッセージは `git-flow-strategy` の形式（`feat:` / `fix:` / `docs:` / `chore:` 等）に従う。

## Claude Codeへの指示

- **gitのコミット/プッシュ/PRの前に、必ず上記と `git-flow-strategy` スキルを確認する。**
- 「小さな修正だから」でも `main` への直pushはしない。必ず feature ブランチ + PR。

## 技術メモ

- `index.html` 1ファイルで完結（外部依存は Google Fonts の CDN 読み込みのみ、画像・ロゴ・アイコンはHTML内に埋め込み）。
- `main` にマージされると GitHub Pages が自動で再デプロイ（1〜2分）。
- Jekyll 無効化のため `.nojekyll` を配置済み。
