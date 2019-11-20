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

## usersテーブル
  |Column|Type|Options|
  |------|----|-------|
  |name|integer|null: false, foreign_key: true|
  |email|integer|null: false, foreign_key: true|
  |password|integer|null: false, foreign_key: true|

### Association
 - has_many :chat
 - has_many :image

 ## chatテーブル
 |Column|Type|Options|
 |------|----|-------|
 |text|integer|null:false, foreign_key: true|
 |image_id|integer|null:false, foreign_key: true|
 |users_id|integer|null:false, foreign_key: true|
 |group_id|integer|null: false, foreign_key: true|

  ### Association
 - belongs_to :users
 - belongs_to :image

 ## imageテーブル
 |Column|Type|Options|
 |------|----|-------|
 |chat_id|integer|null: false, foreign_key: true|
 |users_id|integer|null: false, foreign_key: true|

  ### Association
 - belongs_to :users
 - has_many :users 

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user