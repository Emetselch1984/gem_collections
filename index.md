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
# 画像投稿
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





 

