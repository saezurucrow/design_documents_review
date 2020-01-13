# テーブル定義書2
## 全体
- 主キーは~idという命名規則ではなくid
- カラム命名規則(adminテーブルのadmin_emailカラムではなくadminテーブルのemaiカラム)

<!-- 追記-->
## admins
- idにindexがない
- admin_passwordの命名規則

## users
- l_name,f_name等意味合いを省略して書くとカラムの役割がわかりづらい
- telだけだと用途がわかりづらい
<!-- 追記-->
- メンバーステータスの命名規則、ユーザーのなんのステータスを取り扱うのかわかりづらい、退会ステータスという役割がわかるような命名にしてほしい

## discs
- disc_num 基本的にカラムの命名は省略けいを使わない
<!-- 追記-->
- products_id → product_id

## cart_items
- テーブル名がスネークケースで書かれていない
- Cart item_idはidのみで記述
- buy_numの命名がわかりづらい

## sell_details
- テーブルの命名が不適切、order_detailsとかがいい
<!-- 追記-->
- 親である注文(ここではsells)を作成したのち子であるsell_detailsが作成されるので関係性が逆転している

## sells
- テーブルの命名が不適切、orderとかがいい
<!-- 追記-->
- totalカラムの命名がわかりづらい第三者がみて支払い合計だとわかるように命名
- sell_details_Idを持っていると親子関係が逆なってしまう

**研修担当レビュー**
<font color="red">再提出の際はこのレビューを残しておいてください。</font>

## order_details
- 購入時の価格はどのように保持しますか？
