# エラー系
```ruby
gem 'better_errors'
gem 'binding_of_caller'
```
## better_errors
デフォルトのエラー画面を整形してくれるgem
```ruby
gem 'better_errors'
```
## binding_of_caller
エラー画面にirbをつけてくれるgem \
better_errorsとセットで用いられることが多い。
```ruby
gem 'binding_of_caller'
```
## gem 'pry-byebug'
```ruby
gem 'pry-byebug'
```

# テスト関連
## gem 'faker'
```ruby
gem 'faker'
```
## gem 'rubocop-rails'
(https://github.com/rubocop/rubocop-rails)
```ruby
gem 'rubocop-rails'
```
## gem 'rspec-rails'
```ruby
gem 'rspec-rails'
```
## gem 'factory_bot_rails'
```ruby
gem 'factory_bot_rails'
```
# バリデーション関連
## date_validator
(https://github.com/codegram/date_validator)
```ruby
gem 'date_validator'
```
### サンプルコード
```ruby
  validates :birthday, date: {
    after: Date.new(1900, 1, 1),
    before: ->(_obj) { Date.today },
    allow_blank: true
  }
```
## gem 'valid_email2'
正規表現を使わずにバリデーションを行う
```ruby
gem 'valid_email2'
```


# 設定関連
## config
環境ごとに変数を設定できるgem
```ruby
gem 'config'
```
```
rails g config:install
```
## fog_aws
(https://github.com/fog/fog-aws)
```ruby
gem 'fog-aws'
```
### サンプルコード
```ruby
require 'carrierwave/storage/abstract'
require 'carrierwave/storage/file'
require 'carrierwave/storage/fog'

CarrierWave.configure do |config|
    config.storage :fog
    config.fog_provider = 'fog/aws'
    config.fog_directory  = 'comment-picture-0506' # 作成したバケット名を記述
    config.fog_credentials = {
      provider: 'AWS',
      aws_access_key_id: ENV['AWS_ACCESS_KEY_ID'], # 環境変数
      aws_secret_access_key: ENV['AWS_SECRET_ACCESS_KEY'], # 環境変数
      region: 'ap-northeast-3',   # アジアパシフィック(東京)を選択した場合
      path_style: true
    }
end 
```
## gem 'dotenv-rails'
```ruby
gem 'dotenv-rails'
```
### サンプルコード
```
AWS_ACCESS_KEY_ID= AKIA5S
AWS_SECRET_ACCESS_KEY= t5+lPmfFCT1DU0ji0pseNRdnF/D
ENV['AWS_ACCESS_KEY_ID']
ENV['AWS_SECRET_ACCESS_KEY']
```
## gem 'rails-i18n'
```ruby
gem 'rails-i18n'
```
# フロントエンド
```ruby
gem 'bootstrap'
gem 'jquery-rails'
```
## boostrap
CSSフレームワーク
```ruby
gem 'bootstrap'
gem 'jquery-rails'
```
## jquery-rails
jquery(ジェイクエリー)
```ruby
gem 'bootstrap'
gem 'jquery-rails'
```
# 認証系
## sorcery
```ruby
gem 'sorcery'
```
# デザインパターン
## draper
```ruby
gem 'draper'
```
(https://github.com/drapergem/draper)
# 機能系
## 画像投稿
## carrierwave 
(https://github.com/carrierwaveuploader/carrierwave)
```ruby
gem 'carrierwave'
```
### サンプルコード
```
mount_uploader :avatar, AvatarUploader
<%= image_tag current_user.avatar_url,class: "rounded-circle",style:"width: 150px;height: 150px;" %>
<div class="form-group">
 <%= f.label "写真" %>
 <%= f.file_field :avatar, class: 'mb-3', accept: 'image/*' %>
 <%= f.hidden_field :avatar_cache %>
</div>
```
## ページネーション
## gem 'kaminari'
```ruby
gem 'kaminari'
```
## スクレイピング
## gem 'nokogiri'
```ruby
gem 'nokogiri'
```
### チュートリアル
(https://nokogiri.org/tutorials/toc.html)
## 検索機能
(https://github.com/activerecord-hackery/ransack)
## gem 'ransack'
```ruby
gem 'ransack'
```
### サンプルコード
```
def index
  @q = Person.ransack(params[:q])
  @people = @q.result(distinct: true)
end
<%= search_form_for @q do |f| %>

  # Search if the name field contains...
  <%= f.label :name_cont %>
  <%= f.search_field :name_cont %>

  # Search if an associated articles.title starts with...
  <%= f.label :articles_title_start %>
  <%= f.search_field :articles_title_start %>

  # Attributes may be chained. Search multiple attributes for one value...
  <%= f.label :name_or_description_or_email_or_articles_title_cont %>
  <%= f.search_field :name_or_description_or_email_or_articles_title_cont %>

  <%= f.submit %>
<% end %>
```









 

