## 投稿取得

コントローラを作る


```
# app/controllers/api/v1/posts_controller.rb

class Api::V1::PostsController < Api::ApplicationController
  def index
    @posts = Post.all
  end
end
```

