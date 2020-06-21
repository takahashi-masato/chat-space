# README

# Chat-space DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_name|string|null: false, unique: true|
|email|string|null: false, unique: true|
|password|string|null: false, unique: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- has_many :groups
- has_many :messages


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- has_many :users
- has_many :messages


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|authorization_id|integer|null: false, foreign_key: true|
|text|text||
|image|text||
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :authorization


## authorizationsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group