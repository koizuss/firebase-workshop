デプロイ
==================

## Firebase tools インストール

Firebase tools: Firebaseを操作するためのCLIツール

- https://firebase.google.com/docs/cli/?hl=ja

```
npm i -D firebase-tools
$(npm bin)/firebase --help
```

## Firebase tools でログイン

```
$(npm bin)/firebase login
```

## プロジェクトディレクトリを初期化

ローカルディレクトリをデプロイ用に初期化

```
$(npm bin)/firebase init
```

1. `Hosting: Configure and deploy Firebase Hosting sites` を選択
1. 今回作成したFirebaseプロジェクト名を選択
1. 後はデフォルトでいいのでEnter連打

### 初期化時に作成されるファイル

- .firebaserc
  - プロジェクトのメタデータ
- database.rules.json
  - データベースルールファイル
  - 今後は基本このファイルを編集してデプロイする流れ
  - **間違うとルールが全部消えるとかあるので注意** （後述）
  - セキュリティホールになりかねないのでパブリックなリポジトリでは公開しない方が吉
- firebase.json
  - プロジェクトディレクトリの設定ファイル
- public/
  - Hostingされる静的ファイルを格納する用のディレクトリ

## ビルド成果物出力先を調整

webpackの設定を変更

- webpack-dev-server.config.js
- webpack-production.config.js

## ビルド

```
npm run build
```

- `plublic/` に各種ファイルが出力されていることを確認

## デプロイ

```
$(npm bin)/firebase deploy
```

コンソールに表示される `Hosting URL` にアクセスすると作成したアプリが使える（はず）

**お疲れ様でした！！**

---

## ※※※デプロイ時の注意！！！

上記 `firebase deploy` コマンドはローカルの `./database.rules.json` でクラウド上のルールを **問答無用で上書き** します。
データベースルールはセキュリティリスクがかなり高いです（とゆーかデータを守る唯一の手段です）。
ローカルファイルが間違った状態で知らずに上がってしまったみたいなケースは十分に注意してください。

> ちなみに僕はそこそこ完成形のルールを1度白紙に戻しました。（リポジトリでも管理していなかったので涙すらでませんでした）

デプロイはコマンドオプションでデータベースルール反映をスキップできます。

```
$(npm bin)/firebase deploy --only Hosting  # Hosting資材のみデプロイ
```

デプロイは↑のみで対応し、ルールはコンソールでしか変更しない運用とかもありです。
（間違ってオプション無しで叩かないよう、CIツールでデプロイする等の検討が必要）
