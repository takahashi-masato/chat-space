# README

# Chat-space DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
|email|string|null: false, unique: true|
|password|string|null: false, unique: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- has_many :groups, through: user_groups
- has_many :messages
- has_many :user_groups


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- has_many :users, through: user_groups
- has_many :messages
- has_many :user_groups


## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|text|text||
|image|text||
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group


## user_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|created_at|integer|null: false|
|update_at|integer|null: false|

### Association
- belongs_to :user
- belongs_to :group