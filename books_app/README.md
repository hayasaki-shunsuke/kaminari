# kaminariでページング処理

kaminariを使って書籍一覧のページング処理を行う。

参考URL：https://github.com/kaminari/kaminari

# やること

## ページング処理
- 書籍一覧のテーブルの下にページャーを表示させ、ページング処理ができるようにする。

# やったこと
- kaminariのインストール
  - Gemfileに`gem 'kaminari'` を記述
  - `bundle`でインストールする
  - books_controller.rbに処理を記述
- ソースに処理を記述
~~~ruby
# books_controller.rb
# 1ページに表示する書籍数
SHOW_PER_PAGE = 5
def index
  @books = Book.page(params[:page]).per(SHOW_PER_PAGE)
  @items = Book.page(params[:page]).per(SHOW_PER_PAGE)
end
~~~


~~~ruby
# index_html.erb
<%= paginate @items %>
~~~





