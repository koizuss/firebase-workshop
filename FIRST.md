Firebase勉強会（ワークショップ）
==============

## 目的

*" Firebase の基本を知る "*

Firebaseの基本を知ってまずは *"使い始める"* ことができるようになる

## 準備するもの

- git
- エディタ
  - （もちろん）vim推奨
- node
  - v7.0.0推奨
  - ndenv推奨
- Githubアカウント
  - github上でsrcを共有します
- Googleアカウント
  - 会社のアカウントでOK
- 楽しむ気持ち
  - 必須！！！

## アジェンダ

1. オープニング
  1. (m)BaaSってなに？
    - http://e-words.jp/w/BaaS.html
  1. Firebaseってなに？
    - http://qiita.com/kohashi/items/43ea22f61ade45972881
    - Googleが提供するサービス
      - 高品質のセキュリティー・パフォーマンス
      - Analytics技術との連携によるデジタルマーケティング
      - （あと、潤沢なリソースがあるので開発速そう、たぶん）
  1. [Firebaseの機能](#Firebaseの機能)
1. 概要説明
  1. [機能（やりたいこと）](#機能（やりたいこと）)
  1. [ルール説明（repos/branchの使い方）](#ルール説明（repos/branchの使い方）)
1. [Workshop](WORKSHOP/index.md)
1. and more...
  1. Firebaseの弱点
    1. ロックイン
  1. Firebase Analytics

---

## Firebaseの機能

https://firebase.google.com/features/?hl=ja

### ワークショップで使用する機能

- 認証 (Authentication)
  - ソーシャルログイン
- Realtime Database ★
  - CRUD
    - リアルタイムなデータ変更反映
  - セキュリティ
  - トランザクション
- Hosting
  - CIでデプロイ

---

## 機能（やりたいこと）

### Ph-1 基本実装

TODOアプリの基本機能でFirebaseの基本的なデータI/O、セキュリティ設定、デプロイ方法を知る

- ログイン
  - Googleアカウントでソーシャルログイン（認証連携）
- TODOの追加・変更・削除
- TODOの表示
- 完了チェック
- セキュリティ設定・デプロイ

### Ph-2 グループ

複数エンティティにまたがるグループ単位でのセキュリティ設定を知る

- グループ追加・削除
- グループの詳細表示
- グループ一覧表示
- グループ承認・取り消し

### Ph-3 サブタスク

条件を指定してデータを取得する方法を知る

- サブタスク追加・変更・削除
- サブタスク数表示

---

## ルール説明（branchの使い方とか）

### Repository

<URL>

- ↑はforkしてcloneして使ってください

### Branch

- 機能 x before/afterでブランチを作成しています
  - 1-1_login/before: ログイン機能の開始ポイント
  - 1-1_login/afer: ログイン機能の完成形
- 各機能実装開始時は `foo/before` ブランチから `foo/dev` ブランチを作成
  - `git checkout -b foo/before foo/dev`