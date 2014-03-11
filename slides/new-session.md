## トークン取得

* メールアドレスとパスワードを確認
* あってる場合はトークンを返す

```
# app/controllers/api/v1/sessions_controller.rb

class Api::V1::SessionsController < Api::ApplicationController
  skip_before_action :authenticate_user!, only: [:create]

  def create
    @user = User.find_by(email: params[:user][:email]) if params[:user]
    if @user && @user.authenticate(params[:user][:password])
      @user.initialize_token!
      render @user
    else
      render json: { error: 'メールアドレスあるいはパスワードが異なる'}, status: 403
    end
  end
end
```
