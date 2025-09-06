
# RailsGirls Ideas App

このリポジトリは RailsGirls 用のアイデア投稿アプリです。

## 主な機能

- アイデアの投稿・編集・削除
- 画像アップロード（CarrierWave使用）
- アイデア一覧・詳細表示
- Aboutページ


## 技術スタック

- Ruby on Rails 8.0
- SQLite3（開発・テスト）
- PostgreSQL（本番）
- CarrierWave（画像アップロード）
- Propshaft（アセット管理）
- Turbo/Stimulus（Hotwire）
- Jbuilder（JSON API）
- Puma（Webサーバ）
- Importmap（JavaScript管理）


## セットアップ手順

1. リポジトリをクローン
2. 必要なGemをインストール
	```zsh
	bundle install
	```
3. データベース作成・マイグレーション
	- 開発・テスト環境（SQLite3）
	  ```zsh
	  bin/rails db:create db:migrate
	  ```
	- 本番環境（PostgreSQL）
	  - PostgreSQLのインストール・設定が必要です。
	  - `config/database.yml` を本番用に修正してください。
	  - 環境変数 `DATABASE_URL` などを利用して接続情報を指定します。
	  - マイグレーション：
		 ```zsh
		 bin/rails db:migrate RAILS_ENV=production
		 ```
4. サーバ起動
	```zsh
	bin/rails server
	```
5. ブラウザで `http://localhost:3000` にアクセス

## ディレクトリ構成

- `app/models/idea.rb` アイデアモデル
- `app/controllers/ideas_controller.rb` アイデアのCRUDコントローラ
- `app/views/ideas/` アイデア関連のビュー
- `app/uploaders/picture_uploader.rb` 画像アップローダ
- `db/migrate/` マイグレーションファイル
- `config/routes.rb` ルーティング設定
- `public/uploads/` 画像保存先

## テスト

テストは以下で実行できます。
```zsh
bin/rails test
```

## デプロイ

Docker対応（`Dockerfile`あり）。Kamalでのデプロイも可能です。

## ライセンス

MIT
