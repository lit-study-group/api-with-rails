## 認証用のトークン

トークンをデータベースに追加する.

```
$ bundle exec rails g migration AddTokenToUser token:string
```

* 速く取り出したい
* ユーザ判別に使うので, ユニークである必要

```
# db/migrate/XXXXX_add_token_to_user.rb
class AddTokenToUser < ActiveRecord::Migration
  def change
    add_column :users, :token, :string
    add_index :users, :token, unique: true
  end
end
```
