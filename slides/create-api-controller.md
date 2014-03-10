## 基本のコントローラを作る

```
$ mkdir -p app/controllers/api/v1
```

コントローラを作る

```
<!-- app/controllers/api/v1/application_controller.rb -->
class Api::ApplicationController < ActionController::Base
  protect_from_forgery with: :null_session
end

```
