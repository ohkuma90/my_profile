# テーブル設計

## usersテーブル

| Column             | Type    | Options                    |
| ------------------ | ------- | -------------------------- |
| name               | string  | null: false                |
| email              | string  | null: false , unique: true |
| encrypted_password | string  | null: false                |
| x_id               | string  | null: false                |
| birth              | integer | null: false                |
| nickname           | string  | null: false                |
| favorite_food      | string  | null: false                |
| hated_food         | string  | null: false                |
| holiday            | string  | null: false                |
| hobby              | string  | null: false                |
| first_band         | string  | null: false                |
| first_live         | string  | null: false                |

### Association

- has_many :books
- hes_many :cards, through: :books


## cardsテーブル

| Column | Type       | Options                       |
| ------ | ---------- | ----------------------------- |
| live   | string     | null: false                   |
| rank1  | string     | null: false                   |
| rank2  | string     | null: false                   |
| rank3  | string     | null: false                   |
| user   | references | null:false, foreign_key: true |

### Association

- has_many :books
- hes_many :users, through: :books


## purchases テーブル

| Column      | Type       | Options                       |
| ----------- | ---------- | ----------------------------- |
| card        | references | null:false, foreign_key: true |
| user        | references | null:false, foreign_key: true |

### Association

- belongs_to :card
- belongs_to :user
