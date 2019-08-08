# README

##usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true|

###Asssociation
- has_many :members
- has_many :groups, through: :members
- has_many :messages

##groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique: true|

###Association
- has_many :members
- has_many :users, through :members
- has_many :messages

##messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|references|null: false,foreign_key: true|
|user_id|references|null: false,foreign_key: true|

##Association
- belongs_to :users
- belongs_to :groups

##membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false,foreign_key: true|
|group_id||references||null: false, foreign_key: true|

###Association
- belongs_to :groups
- belongs_to :users

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
