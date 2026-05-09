# sp-dashboard-portal

Studyplus プロダクト部の Dashboard / Report 公開用リポジトリ。Cloudflare Pages + Cloudflare Access (`@studyplus.jp` ドメイン制限) で社内に配信する。

## 配下構造

- `index.html` … ポータルトップ（目次）
- `samples/` … 動作確認用
- `dashboard/` (予定) … 週次サマリ HTML
- `reports/` (予定) … 経営会議報告等の HTML

## 公開範囲

- Cloudflare Pages にデプロイ（`*.pages.dev` サブドメイン）
- Cloudflare Access による `@studyplus.jp` メールドメイン認証必須
- 認証されていないアクセスは弾かれる

## 注意事項

- **HR情報・個人評価・等級・配置転換などの人事的情報を載せない**
- 機密性の高い情報を載せる場合は、別途運用方針を整備してから

## 関連

- 親運用リポ: `executive`（議事録・OKR等の機密情報を保持）
- bot 連携 (予定): `executive` 内 `Scripts/dashboard_update_bot.py` 等から HTML 出力をこのリポに git push する想定（実装は後続）

## 更新フロー

1. ローカル or bot で HTML 生成
2. このリポに commit & push
3. Cloudflare Pages が自動デプロイ（main ブランチ）
4. `@studyplus.jp` ログインして閲覧
