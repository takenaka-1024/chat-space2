## usersテーブル
|Column|Type|Options|
|------|----|-------|
|username|string|null: false, index: true|
|email|string|null: false, unique: true|
|password|string|null: false|
|group_id|reference|null: false, foreign_key: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|message|text| |
|image|text| |
|user_id|reference|null: false, foreign_key: true|
|group_id|reference|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group
- has_many :groups_users

## groups
|Column|Type|Options|
|------|----|-------|
|groupname|string|null: false, index: true|
|user_id|reference|null: false, foreign_key: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users

## groups_users
|Column|Type|Options|
|------|----|-------|
|user_id|reference|null: false, foreign_key: true|
|group_id|reference|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group


