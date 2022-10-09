## usersテーブル

|  Column               |  Type       |  Options                       |
|  -------------------  |  ---------- |  -------------------------     |
|  email                |  string     |  null: false, unique: true     |
|  encrypted_password   |  string     |  null: false                   |
|  name                 |  string     |  null: false                   |
|  profile              |  text       |  null: false                   |
|  occupation           |  text       |  null: false                   |
|  position             |  text       |  null: false                   |

## アソシエーション

- has_many :comments
- has_many :prototypes, through: :comments

## comments

|  Column               |  Type       |  Options                        |
|  -------------------- |  ---------- |  ------------------------------ |
|  content              |  text       |  null: false                    |
|  prototype            |  references |  null: false, foreign_key: true |
|  user                 |  references |  null: false, foreign_key: true |


##　 アソシエーション

- belongs_to :prototype
- belongs_to :users

## prototypesテーブル

|  Column               |  Type       |  Option                         |
|  -------------------- |  ---------- |  ------------------------------ |
|  title                |  string     |  null: false                    |
|  catch_copy           |  text       |  null: false                    |
|  concept              |  text       |  null: false                    |
|  user                 |  references |  null: false, foreign_key: true |
