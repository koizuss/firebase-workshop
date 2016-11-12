Firebase勉強会（ワークショップ）
==============

## 目的

**" Firebase の基本を知る "**

Firebaseの基本を知ってまずは *"使い始める"* ことができるようになる

## 準備するもの

- git
- エディタ
  - （もちろん）vim推奨
- node
  - v7.0.0推奨
  - ndenv推奨
- Githubアカウント
  - Github上でsrcを共有します
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
  1. [機能（やりたいこと）](#機能やりたいこと)
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

TODOアプリの基本機能でFirebaseの基本的なデータI/O、セキュリティ設定、デプロイ方法を知る

- ログイン
  - Googleアカウントでソーシャルログイン（認証連携）
- タスク表示・追加・変更・削除
- 完了チェック
- セキュリティ設定・デプロイ

---

## ルール説明（branchの使い方とか）

### Repository

<URL>

- ↑はforkしてcloneして使ってください

### Branch

機能単位にブランチを作成しています

- 各機能ブランチは対象機能完了時点のコミットです
- うまく動かないなどあれば進行に合わせて対象ブランチ（解説している1つ前の機能ブランチ）から作業ブランチを切り直して再開してください
