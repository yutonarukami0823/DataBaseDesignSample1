# README

T# README
# Chatspace DB設計
## user テーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false: index: true|
### Association
- has_many :group_users: 
- has_many :group,through: :group_users


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|image|string||
|body|text||
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- has_many :messages
## groupテーブル
|Column|Type|Options|
|------|----|-------|

|nickname|string|null: false: index: true|
### Association
## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user
