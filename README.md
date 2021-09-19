# テーブル設計
## users テーブル
| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| email              | string | null: false |
| password           | string | null: false |
| name               | string | null: false |
| profile            | text   | null: false |
| occupation         | text   | null: false |
| position           | text   | null: false |
-has_many :comments
-has_many :prototype
## comments テーブル
| Column | Type   | Options     |
| ------ | ------ | ----------- |
| text   | text   | null: false |
| user   | references|          |
| prototype | references|       |
-belongs_to : users
-belongs_to : prototype
## prototypes テーブル
| Column  | Type       | Options                        |
| ------  | ---------- | ------------------------------ |
| title   | string     | null: false,                   |
| catch_copy | text    | null: false,                   |
| image   | ActuveStorageで実装|                         |
| user    | references |                                |
-belongs_to : users
-has_many : comments
