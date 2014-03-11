## 認証用のトークンの生成

* ランダムな文字列を生成
* 存在するかを確認
* 存在するとやり直し
* 存在しないと保存
* 一度しか初期化しない

```
# app/models/user.rb
class User < ActiveRecord::Base
  before_create :initialize_token!
...
  def initialize_token!
    return unless self.token.nil?
    self.token = loop do
      token = SecureRandom.urlsafe_base64(20, false)
      break token unless User.exists?(token: token)
    end
  end
...
end
```
