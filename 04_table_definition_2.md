# テーブル定義書2
## 全体
- PKはidでよい。
- 入荷を管理するテーブルがない。

## admins
- admin_id: INDEXがあるべき。

## users
- user_l_name: 性の漢字が違う、備考の内容が抽象的、INDEXがあるべき、略語で書くべきでない。
- user_f_name: INDEXがあるべき、略語で書くべきでない。
- user_l_name_kana: 性の漢字が違う、略語で書くべきでない。
- member_status: データ型とDEFAULTの記述に矛盾がある。備考やDEFAULTに合わせるならば、データ型はboolean。
- テーブル名と同一なため、userという接続語はいらない。

## ships
- ship_id: INDEXがあるべき。
- テーブル名と同一だからshipという接続語はいらない。

## products
- stock: 入荷と受注数との計算結果であり。変動する事が多いため不必要。
- stock_status: DEFAULTがあるべき、備考にはenumのそれぞれのキーに対応する値も記述するべき。

## discs
- dics_id: PKだからINDEXがあるべき。
- products_id: railsの外部キーの命名規則に則ってない。
- テーブル名と同一だから、discという接続語はいらない。
- ディスク名を保存するカラムがない。

## songs
- song: 命名が曖昧で役割が理解されづらい。

## labels
- label: 命名が曖昧で役割が理解されづらい。
- レーベルの読みカナについて管理できるカラムがあるべき。

## artists
- artist: 命名が曖昧で役割が理解されづらい。
- アーティストの読みカナについて管理できるカラムがあるべき。

## genres
- genre: 命名が曖昧で役割が理解されづらい。

## cart items
- Cart item_id: PKであるからINDEXがあるべき。
- products_id: railsの外部キーの命名規則に則ってない。
- buy num: カラム名がrailsの命名規則に則っていなく、管理側に考慮した命名でない。
- テーブル名がrailsのテーブル名の命名規則に則っていない。

## sell details
- products_id: FKであるべき、railsの命名規則に則っていない。
- sell_num: 管理側に考慮した命名でない。
- テーブル名がrailsの命名規則に則っていなく、管理側に考慮した命名でない、order_details等にするべき。
- 購入時の価格を保存するカラムがない。

## sells
- sell_id: PKなのでINDEXがあるべき。
- sell_details_id: 1テーブルに複数の値が入る可能性があることに考慮していない、よって不必要。
- pay: DEFAULTを指定するべきで備考にenumのそれぞれのキーに対応する値を記述するべき。
- 配送状況を管理するテーブルがない。
- テーブル名が管理側に考慮して命名でない、orders等にするべき。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
