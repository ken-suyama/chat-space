# README

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


**establish database**

## Users Table

|Column|Type|Options|
|------|----|-------|
|id|integer||
|nickname|string|null: false|
|password|string|null :false|
|email|string|null: false|
### Association
- has_many :groups
- has_many :messeges
- has_many :group_users

## Groups Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|group_name|string|null: false|
### Association
- has_many :messages
- has_many :group_users
- belongs_to :user


## Group_Users Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|user_id|references||
|group_id|references||
### Association
- belongs_to :group
- belongs_to :user

## Messages Table
|Column|Type|Options|
|------|----|-------|
|id|integer||
|text|text|null: false|
|image|string||
|user_id|references||
|group_id|references||
### Association
- belongs_to :user
- belongs_to :group