# テーブル設計

## users テーブル

| Column          | Type   | Options     |
| --------------- | ------ | ----------- |
| email           | string | null: false |
| password        | string | null: false |
| first_name      | string | null: false |
| last_name       | string | null: false |
| first_name_kana | string | null: false |
| last_name_kana  | string | null: false |
| yyy             | date   | null: false |
| mm              | date   | null: false |
| dd              | date   | null: false |



### Association

- has_many :furimas
- has_many :comments

## furimas テーブル

| Column        | Type       | Options                         |
| ------------- | ---------- | ------------------------------- |
| item_name     | text       | null: false                     | 
| category      | string     | null: false                     |
| status        | string     | null: false                     |
| delivery_fee  | string     | null: false                     |
| area          | string     | null: false                     | 
| delivery_days | strin      | null: false                     |
| price         | integ      | null: false                     |
| user          | references | null: false,  foreign_key: true |

### Association

- has_many :comments
- belongs_to :users


## comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| furima    | references | null: false, foreign_key: true |

### Association

- belongs_to :users
- belongs_to :furimas
