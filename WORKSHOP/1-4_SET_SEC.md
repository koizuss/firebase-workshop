セキュリティ設定
==================

## セキュリティ(データの検証)設定

### 仕様確認
  - https://firebase.google.com/docs/database/security/
  - ![sec](../images/sec.png)
  - デフォルトで認証済ユーザーのみ許可
  - 各要素毎に指定可能
    - JavaScriptで条件を指定、結果が true:許可/false:拒否
    - 条件判定コード内で以下のデータが参照可能
      - 認証ユーザーを参照可能: auth
      - 反映データ（新/旧）を参照可能: newData / data
      - パスに含まれた値（keyなど）を参照可能: `$` を付けて変数として定義
      - データベースに格納されたその他のデータを参照可能
      - 他にも
        - https://firebase.google.com/docs/database/security/securing-data
  - その他セキュリティのドキュメントはデータの構造を決める参考になる
    - https://firebase.google.com/docs/database/security/user-security

### セキュリティ設定

- デフォルトでは認証していれば誰でもタスクデータを参照できる設定になっている
- タスクデータは登録した本人しか見れない仕様にする

```
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null",
    "task": {
      "$userId": {
        ".read": "auth.uid === $userId"
      }
    }
  }
}
```

