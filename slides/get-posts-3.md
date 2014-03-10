## 投稿取得

ルートの追加

```
# config/routes.rb
...
  scope :api, module: 'api' do
    scope :v1, module: 'v1' do
      resources :posts, only: [:index]
    end
  end
...
```

動作を確認する

```
$ curl -H 'Content-Type: application/json' localhost:3000/api/v1/posts
```
