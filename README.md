# README

# Chat-Space DB設計

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|name|string|null: false|
### Association
- has_many :messeages
- has_many :groups, through: : users_groups
- has_many :groups_users

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null :false|

### Association
- has_many :messeages
- has_many :users, through: :users_groups
- has_many :groups_users

## messageテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null :false|
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user