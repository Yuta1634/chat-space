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

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null :false|

### Association
- has_many :messeages
- has_many :users, through: :users_groups

## message

|Column|Type|Options|
|------|----|-------|
|body|text|null :false|
|image|string|null :false|
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