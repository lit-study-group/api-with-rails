## ユーザ認証動作確認

ユーザのトークンを取ってくる

```
$ bundle exec rails console
> User.first.token
foobarbaz
```

以上得たトークンを使って

* 1回目認証せず
* 2回目認証する

```
$ curl -H 'Content-Type: application/json' localhost:3000/api/v1/posts
$ curl -H 'Content-Type: application/json' -H 'X-Token: foobarbaz' localhost:3000/api/v1/posts
```
