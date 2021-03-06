・アプリ名：
FamilyPhotos

・概要：
家族写真等が、共有できるアプリケーションです。

・本番環境:
https://family-photos-31747.herokuapp.com/

・制作背景(意図)：
コロナ禍で離れて住む、不祖母や親戚と写真共有することが出来る。

・DEMO(gif動画)
app/assets/images/demo.gif

・工夫したポイント:
1.投稿編集、削除が出来る。
2.マイページ機能がある。

・使用技術(開発環境)
○マークアップ言語
HTML,CSS

○サーバーサイド
Ruby,Ruby on Rails

○データベース
MySQL

○ツール
Git,GitHub,Heroku,Sequel Pro,Trello

・課題や今後実装したい機能
リスポンシィブWebデザイン

・DB設計
## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| nickname   | string | null: false |
| email      | string | null: false |
| password   | string | null: false |

### Association

- has_many :tweets
- has_many :comments

## tweets テーブル

| Column                   | Type       | Options     |
| ------------------------ | ---------- | ----------- |
| text                     | string     | null: false |
| image                    | text       | null: false |
| user_id                  | references | foreign_key |

- belongs_to :users
- belongs_to :comments

## comments テーブル

| Column    | Type       | Options     |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user_id   | references |             |
| tweet_id  | references |             |

### Association

- belongs_to :users
- belongs_to :tweets