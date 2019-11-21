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

## userテーブル
  |Column|Type|Options|
  |------|----|-------|
  |name|integer|null: false, foreign_key: true|
  |email|integer|null: false, foreign_key: true|
  |password|integer|null: false, foreign_key: true|

### Association
 - has_many :chat
 - has_many :group
 - has_many :group, through: :groups_users

 ## chatテーブル
 |Column|Type|Options|
 |------|----|-------|
 |text|integer|null:false, foreign_key: true|
 |image|string|null:false, foreign_key: true|
 |user_id|integer|null:false, foreign_key: true|
 |group_id|integer|null: false, foreign_key: true|

  ### Association
 - belongs_to :users
 - belongs_to :groups

 ## groupテーブル
 Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

- has_many :user
- has_many :chat
- has_many :user, through: :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :users
- belongs_to :groups
- 
