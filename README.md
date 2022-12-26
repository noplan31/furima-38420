# README

## usersテーブル

|Column             |Type   |Options                |
|-------------------|-------|-----------------------|
|nikuname           |string |null: false            |
|encrypted_passward |string |null: false            |
|birthday           |integer|null: false            |
|email              |string |null: false            |
|family name        |string |null: false            |
|first name name    |string |null: false            |

### Association
has_many :items
has_many :records



## itemsテーブル

|Column             |Type       |Options                       |
|-------------------|-----------|------------------------------|
|title              |string     |null: false                   |
|price              |integer    |null: false                   |
|cach_copy          |txet       |null: false                   |
|email              |string     |null: false                   |
|user               |references |null: false foreign_key: true |

### Association
belongs_to :users
has_one :records


## recordsテーブル

|Column             |Type       |Options                       |
|-------------------|-----------|------------------------------|
|user               |references |null: false foreign_key: true |
|items              |references |null: false foreign_key: true |


### association
belongs_to :users
belongs_to :items
has_one :addresses

## addressesテーブル

|Column             |Type       |Options                       |
|-------------------|-----------|------------------------------|
|postal_code        |integer    |null: false                   |
|prefectures        |integer    |null: false                   |
|city               |string     |null: false                   |
|address_line       |string     |null: false                   |
|phone              |integer    |null: false                   |

### Association
belongs_to :records