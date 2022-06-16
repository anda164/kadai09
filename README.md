# 課題09 PHP2 汎用情報登録機能DB版(ログイン認証後の表示変更機能追加)
## ①課題内容（PHP3）
- 前回作成の商品等各種情報登録・参照の機能（ログイン認証付）に、ログイン後の表示切り替え処理を追加
- 画面遷移：
-- index.php →(認証：login.php)→item_read.php（一覧表示）
　　　　　　(前回作成分)item_add.php（登録・更新・削除 受付） ⇨ item_write.php（保存・更新・削除処理） ⇨  item_read.php（一覧表示）
　　　　　　※index画面でユーザーID、パスワードを入力しSubmitするとユーザー認証（login.php）を実行
- 表示切り替え内容：
-- ユーザーログイン有： 名前を含んだ挨拶メッセージ＋ログアウトへのリンクを表示、追加・編集画面ではボタン表示（一覧画面はログイン有無に関係なく検索可）
-- ユーザーログイン無： ログインを促すメッセージ＋追加・編集画面ではボタン非表示
      
## ②工夫した点・こだわった点
- 冒頭のsession_start()の振る舞いについて、共通関数に切り出し可能か確認してみた。結果、単純に切り出し先でそれを含む関数を新たに作成しても、共通関数ファイル内で直接呼び出し（関数化無し）でも問題なく動作した。
-- 今回のデモのようにsession_start()だけであれば、共通関数を呼び出すことと大差ないのでメリットはあまりないが、セッション開始後、ログイン成功・失敗（exit等）の処理を帯同する形であれば毎回”session_start()”を呼び出し忘れることがなく、使い道はあるのかと感じた

## ③質問・疑問
- 特に無し
