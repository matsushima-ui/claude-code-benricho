# Claude Code 便利帳

Claude Code(Anthropicのコーディング用CLIツール)を使う上で役立つ「便利な設定」「ツール・機能の組み合わせ」「効果的な指示(プロンプト)の出し方」を集めたTips集です。

- 閲覧サイト: GitHub Pagesで公開(リポジトリの Settings → Pages → Source: `Deploy from a branch` / `main` / `/(root)` を有効にすると `https://matsushima-ui.github.io/claude-code-benricho/` で見られます)
- ライブ版(自動で毎週更新される元データ): [claude.ai上のArtifact](https://claude.ai/code/artifact/3609a89d-43be-4a17-b740-a53c09852672)

## 構成

- `index.html` — 静的サイト本体。`data/tips.json` を読み込んで表示するだけのシンプルな1ファイル構成
- `data/tips.json` — Tips本体のデータ。1件が1オブジェクトの配列

## データ形式

```json
{
  "id": "2026-09-09-desktop-notifications",
  "title": "短いタイトル",
  "summary": "2〜3文の要約",
  "category": "setting | combo | prompting | other",
  "level": "beginner | intermediate | advanced",
  "source_name": "出典名",
  "source_url": "出典URL",
  "date_added": "2026-09-09",
  "week_of": "2026-09-07",
  "tags": ["キーワード"]
}
```

## 更新方法(自動)

このリポジトリは、以下の2つの定期ルーティンによって完全自動で更新されています。

1. **週次Tips調査ルーティン** — 毎週、Claude Codeに関する新しい情報を調査し、claude.ai上のArtifact(ライブ版)のデータベースに追記します。
2. **週次同期ルーティン** — その数時間後、Artifactのデータベースから最新データを取得して `data/tips.json` を再生成し、GitHub App経由で自動的にcommit・pushします。

通常は手動での作業は不要です。手動で介入したい場合は、以下のいずれかで行ってください。

- **Claudeに頼む** — 「GitHubのclaude-code-benrichoを最新のTipsに同期して」と頼むと、同期ルーティンを手動実行できます(ただし単発のClaude Codeセッションにはこのリポジトリへのpush権限が付与されていない場合があります。その場合はGitHub Appのアクセス権を持つ定期ルーティンか、ご自身のローカル環境からpushしてください)。
- **手動で編集** — `data/tips.json` に新しいTipsオブジェクトを追記してpushするだけで、サイトに反映されます(ビルド不要)。

## ローカルでの確認

```bash
cd claude-code-benricho
python3 -m http.server 8000
# http://localhost:8000 を開く
```
