# README

##userテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false,foreign_key:true|
|user_name|string||
|email|string||
|password|string|null: false|

###Asssociation
- has_many :members
- has_many :group, through: :members
- has_many :message

##groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false,foreign_key: true|
|group_name|string|null: false,unique: true|

###Association
- has_many :members
- has_many :user, through :members
- has_many :message

##messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null: false,foreign_key: true|
|user_id|integer|null: false,foreign_key: true|

##Association
- belongs_to :user
- belongs_to :group

##membersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false,foreign_key: true|
|group_id||integer||null: false, foreign_key: true|

###Association
- belongs_to :group
- belongs_to :user

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
