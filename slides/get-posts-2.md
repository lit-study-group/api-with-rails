## 投稿取得

ディレクトリを作成.

```
$ mkdir -p app/views/api/v1/posts
```

JBuilderを使ってビューを作る

<br>

投稿の部分テンプレート

```
# app/views/api/v1/posts/_post.json.jbuilder
json.(post, :id, :body, :created_at, :updated_at)
```

投稿一覧のテンプレート

```
# app/views/api/v1/posts/index.json.jbuilder
json.array! @posts, partial: 'api/v1/posts/post', as: :post
```
