## トークン初期化の動作確認

* ユーザ作成時にトークンが生成される
* 明示的に消さないと, 最初期化されない

```
$ bundle exec rails console
> u = User.create()
> u.token
> u.initialize_token!
> u.token
```
