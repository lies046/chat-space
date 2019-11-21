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
  |name|integer|null: false|
  |email|integer|null: false|
  |password|integer|null: false|

### Association
 - has_many :chats
 - has_many :groups, through: :groups_users
 - has_many :groups_users

 ## chatテーブル
 |Column|Type|Options|
 |------|----|-------|
 |text|integer||
 |image|string||
 |user_id|integer|null:false, foreign_key: true|
 |group_id|integer|null: false, foreign_key: true|

  ### Association
 - belongs_to :user
 - belongs_to :groups

 ## groupテーブル
 Column|Type|Options|
|------|----|-------|
|name|integer|null: false|
|user_id|integer|null: false, foreign_key: true|

- has_many :groups_users
- has_many :users, through: :groups_users

## groups_usersテーブル
## 中間テーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
