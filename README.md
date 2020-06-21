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


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|comment_id|integer|null: false, foreign_key: true|
|title|string|null: false|
|text|text||
|image|text||
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :group_users


## group_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false|
|user_name|string|null: false|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group