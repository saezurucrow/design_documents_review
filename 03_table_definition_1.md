# テーブル定義書1
## 全体
- railsの命名規則に従ったテーブル名で記述していない。
- PKの命名はidでよい。
- PKにINDEXが必要。
- created_at: カラム説明の「ユーザ」が不必要。
- updated_at: カラム説明の「ユーザ」が不必要。

## Admin
- id: AUTO INCREMENTがあるべき。
- PKが指定されていない。

## Users
- user_l_name: 備考に名前とあるが説明が抽象的、性の漢字が違う、INDEXがあるべき。
- user_f_name: NOT NULLであるべき、INDEXがあるべき。
- user_l_name_kana: 性の漢字が違う。
- user_f_name_kana: NOT NULLであるべき。
- ship_address: 複数の配送先情報を格納できるように考慮されていない。
- member_status: 備考にFALSE, TRUEそれぞれの値の意味を書くべき。

## Products
- disc_id: 1テーブルに複数の値が入る可能性があることに考慮していない。
- genre_id: FKである必要がある。
- label_id: FKである必要がある。
- artist_id: FKである必要がある。
- cd_image: refileで管理することが想定されるため、命名の最後に_idが必要でstring型であるべき。
- stock: 変動する事が多いため不必要。
- stock_status: enumで管理し、defaultを指定するべき、備考にそれぞれのキーに対応する値を記述するべき。

## Discs
- products_id: 単数形でよい。
- track_num: 命名が曖昧で役割が分かりづらい。
- ディスク名を管理できるように考慮していない。

## Songs
- song: 命名が分かりづらい、カラムの説明と型が一致していない。
- PKがない。
- 曲順を管理できるよう考慮していない。

## Labels
- products_id: 不必要、Products側から呼び出されるべき。
- label: カラム説明含めて役割が分かりづらい。
- PKがない。

## Artists
- products_id: 不必要、Products側から呼び出されるべき。
- artist: 命名が分かりづらい、文字列を保存できる型でない。
- アーティスト名の読み仮名を管理できるように考慮されていない。
- PKがない。

## Genre
- products_id: 不必要、Products側から呼び出されるべき。
- genre: 命名が分かりづらい、文字列を保存できる型でない。

## Cart item
- user_id: AUTO INCREMENT、INDEXは不必要。
- products_id: 単数形で命名するべき、データ型を記述していない。
- buy num: railsの命名規則に則っていない。
- subtotal: buy numと商品の価格から算出できるため不必要。
- PKがない。

## Buy details
- buy num: railsの命名規則に則っていない。
- どのBuyの詳細なのか情報が不足している。
- Buyの中のどのProductの詳細なのか情報が不足している。
- 管理側に考慮した命名でない。
- 購入時の価格を保存するカラムがない。

## Buy
- buy_details: 1テーブルに複数の値が入る可能性があることに考慮していない。
- pay: 役割が理解しづらい命名、enumで管理し、備考にキーに対応する値を記述するべき。
- stock: カラムの説明と命名に矛盾がある。
- buy_at: 不必要。created_atと役割が同一。
- 管理側に考慮した命名でない。

# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。
# 注意
* マークダウン形式で記入してください。
* 全体を通しての指摘事項の場合、テーブル名の部分を「全体」「共通」などとしてください。

## 指摘事項
## users
- カラム名に略語は不適です。
- member_statusがstring型になっています。
- 郵便番号、電話番号がinteger型だと0始まりの時に保存ができません。
- userという接頭辞が必要ありません。(テーブルから判断できるため)

## products
- productという接頭辞が必要ありません。(テーブルから判断できるため)

## discs
- discという接頭辞が必要ありません。(テーブルから判断できるため)
