##  add-api-routes

* API専用のルートを作る
* APIのバージョンを1にする

```ruby
# config/routes.rb
...
  scope :api, module: 'api' do
    scope :v1, module: 'v1' do
      get 'foo'
    end
  end
...
```


```
$ bundle exec rake routes
```

で以下を探す.

```
foo GET    /api/v1/foo(.:format)                         api/v1#foo
```

確認できたら, `get 'foo'`を消す.
