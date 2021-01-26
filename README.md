# テーブル設計

## users テーブル

| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| name        | string | null: false |
| email       | string | null: false |
| password    | string | null: false |
| profession  | text   | null: false |



### Association

- has_many : books
- has_many : comments


## books テーブル

| Column     | Type       | Options                        |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| author     | text       | null: false                    |
| memo       | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

### Association

- has_many : comments
- belongs_to : user

## comments テーブル

| Colum       | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| text        | text       | null: false
| user        | references | null: false, foreign_key: true |
| book        | references | null: false, foreign_key: true |

### Association

- belongs_to : user 
- belongs_to : book

