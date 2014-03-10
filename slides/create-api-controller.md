## 基本のコントローラを作る

```
$ mkdir app/controllers/api/v1
```


```
<!-- app/controllers/api/v1/application_controller.rb -->
class Api::ApplicationController < ActionController::Base
  protect_from_forgery with: :null_session
end

```
