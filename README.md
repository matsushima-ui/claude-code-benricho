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

## 更新方法

このリポジトリへの自動pushは設定していません(意図的に、認証情報をどこにも保存しない運用にしています)。更新したいときは、以下のどちらかで反映してください。

1. **Claudeに頼む** — 「GitHubのclaude-code-benrichoを最新のTipsに同期して」と頼むと、claude.ai上のArtifact(ライブ版)から最新データを取得して `data/tips.json` を書き換え、コミットまで用意します。push自体はご自身の認証情報で行ってください。
2. **手動で編集** — `data/tips.json` に新しいTipsオブジェクトを追記してpushするだけで、サイトに反映されます(ビルド不要)。

## ローカルでの確認

```bash
cd claude-code-benricho
python3 -m http.server 8000
# http://localhost:8000 を開く
```
