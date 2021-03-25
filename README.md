# README

# アプリ名

shohi-kan

# 概要

消費期限や保証期間などが記載された画像を登録することで自動的に期限を入力し管理するアプリケーション

# 制作背景

私自身が契約した電力会社やモバイルwifiのキャッシュバック期限、また冷蔵庫の中の調味料の消費期限等、
期間を空けて期限を設けられ出来たらお得なことを幾つか逃した経験があるので、冷蔵庫にしまい込んでいる
調味料や食品の消費期限を簡単に確認が取れるアプリがあれば便利になると考え企画しました。

画像を撮影することで自動で期限を読み込み保存し、期限が迫ると段階的に通知がきて予定を忘れないようにしようと考えています。

# DEMO


# 実装予定の内容
・User管理機能
・商品管理機能
・商品一覧表示
・編集機能
・画像読み取り機能
・アラート機能
・Basic認証、S3認証
・SNS認証

# DB設計

## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| nickname           | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |


### Association

- has_many :items

## items テーブル

| Column      | Type       | Options                       |
| ----------- | ---------- | ----------------------------- |
| name        | string     | null: false                   |
| dead_line   | text       | null: false                   |
| comment     | integer    | null: false                   |


### Association

- belongs_to :user
