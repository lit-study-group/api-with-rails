## ユーザのビュー

ユーザのJSONを返すためのビューを作成.

```
# app/views/api/v1/users/_user.json.jbuilder
json.(user, :id, :email, :token, :name, :created_at, :updated_at)
```

動作確認

```
curl -X POST -d '{"email":"foo@foo.jp","password": "foobar"}' localhost:3000/api/v1/sessions/create
```
