## トークン取得ルート

トークン取得のルートを作成.

```
# config/routes.rb
...
  scope :api, module: 'api' do
    scope :v1, module: 'v1' do

      resources :posts, only: [:index]

      post 'sessions', to: 'sessions#create'

    end
  end
```
