# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| -----------------  | ------ | ----------- |
| email              | string | null: false |
| encrypted_password | string | null: false |
| first_name         | string | null: false |
| last_name          | string | null: false |
| first_name_kana    | string | null: false |
| last_name_kana     | string | null: false |
| birth_day          | date   | null: false |



### Association

- belong_to :products
- has_many :comments

## products テーブル

| Column           | Type       | Options                         |
| ---------------- | ---------- | ------------------------------- |
| item_name        | string     | null: false                     | 
| category_id      | integer    | null: false                     |
| status_id        | integer    | null: false                     |
| delivery_fee_id  | integer    | null: false                     |
| area_id          | integer    | null: false                     | 
| delivery_days_id | integer    | null: false                     |
| price            | integer    | null: false                     |
| description      | text       | null: false                     |
| user             | references | null: false,  foreign_key: true |

### Association

- has_many :comments
- has_many :users


## comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| product   | references | null: false, foreign_key: true |

### Association

- belongs_to :users
- belongs_to :products

## products テーブル

| Column           | Type       | Options                         |
| ---------------- | ---------- | ------------------------------- |
| postal_code      | text       | null: false                     | 
| prefecture       | integer    | null: false                     |
| city             | integer    | null: false                     |
| numbering        | integer    | null: false                     |
| building_name    | integer    | null: false                     | 
| telephone_number | integer    | null: false                     |
|                  | integer    | null: false                     |

### Association

- has_many :comments
- has_many :users

