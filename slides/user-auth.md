## ユーザ認証

基本のコントローラで認証用のロジック


```
# app/controllers/api/application_controller.rb
class Api::ApplicationController < ActionController::Base
  protect_from_forgery with: :null_session
  before_action :authenticate_user!

  def user_signed_in?
    !current_user.nil?
  end

  def current_user
    @current_user ||= User.find_by(token: request_token)
  end

  def authenticate_user!
    render json: { error: "認証失敗" }, status: 403 unless user_signed_in?
  end

  private
  def request_token
    request.headers['x-token'] || false
  end
end
```
