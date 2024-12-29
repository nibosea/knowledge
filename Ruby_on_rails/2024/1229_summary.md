# Rails開発で学んだこと

## モデルとマイグレーション

### モデル生成
```bash
rails generate model Book
rails generate model BooksHistory
```

### マイグレーションファイルでのカラム定義
- idカラムは自動で生成される
- マイグレーションファイルでカラムを指定することで、テーブルのスキーマを定義できる



## テスト関連

### Factory Bot
- テストデータを簡単に生成するためのgem
- テストコードでデータ作成を自動化できる
- `book_spec.rb`でモデルのテストを記述する[2]

### バリデーションテスト
- モデルの制約をテストできる
- `bundle exec rspec`でテスト実行
- coverage/index.htmlでテストカバレッジを確認可能[2][4]

## 認証関連
- `sign_out`はDeviseが提供する認証機能
- ビューでリンクを作成する場合は`link_to`ヘルパーを使用

## 環境構築・パッケージ管理

### Bundler
- Rubyのパッケージ（gem）管理ツール
- `Gemfile.lock`でバージョンを固定
- プラットフォーム追加時は`bundle lock --add-platform`を使用

### Docker関連コマンド
```bash
docker compose exec web bundle install
docker-compose exec web rails db:migrate
docker-compose exec web bundle lock --add-platform aarch64
```

## Rails基礎知識
- gemはRubyのライブラリ
- Railsは大規模なWebアプリケーションフレームワーク
- MVCパターンに基づいた構造を提供[1]

Citations:
[1] https://railsguides.jp/active_record_basics.html
[2] https://codeburst.io/writing-simple-validation-tests-using-rails-built-in-test-suites-fc3540eda01b?gi=9cc025c9ed6f
[3] https://qiita.com/mtnkbp/items/20aac3234640f6e6cec9
[4] https://human-se.github.io/rails-demos-n-deets-2020/demo-custom-validations/
[5] https://guides.rubyonrails.org/active_record_migrations.html
[6] https://dexall.co.jp/articles/?p=140
[7] https://guides.rubyonrails.org/v3.2.0/migrations.html
[8] https://guides.rubyonrails.org/testing.html