# README

# アプリ名

## shohi-kan

# 概要

消費期限や保証期間などが記載された画像を登録することで自動的に期限を入力し管理するアプリケーション

# 制作背景

私自身が契約した電力会社やモバイルwifiのキャッシュバック期限、また冷蔵庫の中の調味料の消費期限等、
期間を空けて期限を設けられ出来たらお得なことを幾つか逃した経験があり、日常の中で冷蔵庫にしまい込んでいる
調味料や食品の消費期限を簡単に確認が取れるアプリがあれば便利になると考え企画しました。

画像を撮影することで自動で期限を読み込み保存し、期限が迫ると段階的に通知がきて予定を忘れないようにしようと考えています。

# DEMO

※現在製作中ですので随時スタイル等変更していきます。

## 新規登録画面
<img width="783" alt="登録画面" src="https://user-images.githubusercontent.com/78348935/112430067-fb841600-8d80-11eb-9930-b7b9a2dfa5ae.png">


## ログイン画面
<img width="701" alt="ログイン画面" src="https://user-images.githubusercontent.com/78348935/112430134-0d65b900-8d81-11eb-9894-6ec1e1dcb3f6.png">


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
