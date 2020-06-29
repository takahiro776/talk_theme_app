# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## talksテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|
|content|text|null: false|
|point|text|---|
### Association
- has_many :categorys, through: :talks_categorys
- has_many :talks_categorys
- has_many :likes


## categorysテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
### Association
- has_many :talks, through: :talks_categorys
- has_many :talks_categorys


## likesテーブル
|Column|Type|Options|
|------|----|-------|
|talk|references|null: false, foreign_key: true|
### Association
- belongs_to :talk


## talks_categorysテーブル
|Column|Type|Options|
|------|----|-------|
|talk|references|null: false, foreign_key: true|
|category|references|null: false, foreign_key: true|
### Association
- belongs_to :talk
- belongs_to :category