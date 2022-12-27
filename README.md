# README

## usersテーブル

|Column             |Type   |Options                   |
|-------------------|-------|--------------------------|
|nikuname           |string |null: false               |
|encrypted_passward |string |null: false               |
|birthday           |date   |null: false               |
|email              |string |null: false, unique: true |
|first_name         |string |null: false               |
|first_name name    |string |null: false               |
|last_name_kana     |string |null: false               |
|first_name_kana    |string |null: false               |


### Association
has_many :items
has_many :records



## itemsテーブル

|Column             |Type       |Options                        |
|-------------------|-----------|-------------------------------|
|user               |references |null: false, foreign_key: true |
|title              |string     |null: false                    |
|category_id        |integer    |null: false                    |
|status_id          |integer    |null: false                    |
|delivery_charge_id |integer    |null: false                    |
|area_id            |integer    |null: false                    |
|day_id             |integer    |null: false                    |
|price_id           |integer    |null: false                    |


### Association
belongs_to :users
has_one :record


## recordsテーブル

|Column             |Type       |Options                       |
|-------------------|-----------|------------------------------|
|user               |references |null: false foreign_key: true |
|item               |references |null: false foreign_key: true |
|addresse           |references |null: false foreign_key: true |


### association
belongs_to :users
belongs_to :items
has_one :address



## addressesテーブル

|Column             |Type       |Options                       |
|-------------------|-----------|------------------------------|
|postal_code        |string     |null: false                   |
|prefecture_id      |integer    |null: false                   |
|city               |string     |null: false                   |
|address_line       |string     |null: false                   |
|building           |string     |                              |
|phone              |string     |null: false                   |
|record             |references |null: false foreign_key: true |


### Association
belongs_to :record
