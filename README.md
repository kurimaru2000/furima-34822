# テーブル設計

## users テーブル

| Column             | Type   | Options                   |
| -----------------  | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false               |
| encrypted_password | string | null: false, unique: true |               
| first_name         | string | null: false               |
| last_name          | string | null: false               |
| first_name_kana    | string | null: false               |
| last_name_kana     | string | null: false               |
| birth_day          | date   | null: false               |



### Association

- has_many :products
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
- belongs_to :user
- belongs_to :buyer


## comments テーブル

| Column    | Type       | Options                        |
| --------- | ---------- | ------------------------------ |
| text      | text       | null: false                    |
| user      | references | null: false, foreign_key: true |
| product   | references | null: false, foreign_key: true |

### Association

- belongs_to :users
- belongs_to :product

## buyers テーブル

| Column           | Type       | Options                         |
| ---------------- | ---------- | ------------------------------- |
| postal_code      | string     | null: false                     | 
| city             | string     | null: false                     |
| numbering        | string     | null: false                     |
| building_name    | string     |                                 | 
| telephone_number | string     | null: false                     |


### Association

- has_many :products


## product_users テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| product_id | text       | null: false, foreign_key: true |
| user_id    | references | null: false, foreign_key: true |


### Association

- belongs_to :user
- belongs_to :product

