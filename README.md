# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false|
|email|string|null: false|
|password|string|null: false|
### Association
- has_many :groups,  throuh:  :groups_usrs
- has_many :massages

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group|integer|null: false|
|user_id|integer||null: false, foreign_key: true||
### Association
- has_many :users,  throuh:  :groups_usrs
- has_many :massages


##massagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user