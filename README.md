# 概要
自身の趣味で撮った写真を紹介するための個人サイトです。
インスタやツイッターもありますが、個人的にあまり好きなデザインでは無いため
それなら自分の趣味のサイトを作ってみようと思い立ち、作成をしています。

## DB 設計

## posts table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| id(PK)             | デフォルト          | null: false             |
| nickname           | devise のデフォルト | null: false,index: true |
| email              | devise のデフォルト | null: false             |
| encrypted_password | integer             | null: false             |
| first_name         | string              | null: false             |
| last_name          | string              | null: false             |
| first_name_kana    | string              | null: false             |
| last_name_kana     | string              | null: false             |
| birth_date         | date                | null: false             |

### Association

* belongs_to :users
* has_many :comments

## users table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| id(PK)             | デフォルト          | null: false             |
| nickname           | devise のデフォルト | null: false,index: true |
| email              | devise のデフォルト | null: false             |
| encrypted_password | integer             | null: false             |
| first_name         | string              | null: false             |
| last_name          | string              | null: false             |
| first_name_kana    | string              | null: false             |
| last_name_kana     | string              | null: false             |
| birth_date         | date                | null: false             |

### Association

* has_many :posts
* has_many :comments

## comments table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| id(PK)             | デフォルト            | null: false             |
| comment            | devise のデフォルト   | null: false             |
| user_id            | devise のデフォルト   | null: false             |
| post_id            | devise のデフォルト   | null: false             |

### Association

* belongs_to :post
* belongs_to :user

・いいね機能
・お気に入り登録
・ランサックによる、検索機能
・パンくずつける？
・デプロイ先はあくまでもテスト的なものなので、herokuにあげる
・画像が消えてしまうので、これはS3を使用する
・時間で背景を変えたい（朝、昼、夜）
