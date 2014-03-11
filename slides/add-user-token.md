## 認証用のトークン

* トークンは長い当てられないような文字列
* 毎回パスワードを送りたくない
* ログイン情報送ったら, トークンを返す
* すべてのリクエストでトークンを送る
* ユーザ一をトークンで判別する



```
リクエスト
POST /api/v1/sessions/create
{
  "email": "foo@bar.jp",
  "password": "foobar"
}

リスポンス
{
  "id": 2,
  "email": "foo@bar.jp",
  "token": "foobarbaz_token"
}
```
