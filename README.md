# 🏛 Kaz's ItoLog (技術資産リポジトリ)

フリーランスエンジニア **Kaz** の技術ノート兼、プログラム資産置き場です。
再利用可能な短いコードをメモしています。

[//]: # (設計の考え方や、再利用可能なコード（C#/Java等）を体系的に蓄積しています。)

---

## 🛠 共通ルール（全リポジトリ共通）

履歴をきれいに保ち、後で検索しやすくするために以下のルールで運用しています。

### コミットメッセージの書き方
`[プレフィックス]: [やったこと]（[なぜやったか]）`

| プレフィックス | 意味（使い分け） | 書き方の例 |
| :--- | :--- | :--- |
| **feat:** | **新しい追加**<br>クラス、ファイル、サンプルコードを足した時。 | `feat: 共通関数を追加（再利用のため）` |
| **fix:** | **直し**<br>バグ、タイポ、間違いを直した時。 | `fix: 計算ロジックのミスを修正` |
| **refactor:** | **整理**<br>動きは変えず、コードを読みやすく書き換えた時。 | `refactor: メソッドを分割して整理` |
| **docs:** | **説明書き**<br>READMEやソース内の解説コメントを書いた時。 | `docs: 使い方をREADMEに追記` |
---

## 🚀 Git 基本操作 (1人作業用)

### ■ 1. 最新化
```bash
# mainブランチに移動
git switch main

# リモートの最新状態を取り込む
git pull
```

### ■ 2. 作業開始（ブランチ作成～コミット）
```bash
# 新規作成(-c)して切り替え (feature/1231、feature/1231_2、feature/1231_xxx)
git switch -c feature/9999

# 変更内容の確認（新規フォルダ名）
git status

# 変更内容の確認（変更ファイルの差分）
git diff

# 全てステージング
git add .

# コミット内容の最終確認（commit前）
git diff --cached

# コミット (feat/fix/refactor/docs: [やったこと] ([なぜやったか]))
git commit -m "feat: 〇〇を実装"
```
　
### ■ 3. mainへ反映（マージ～プッシュ）
```bash
# mainブランチに戻る
git switch main

# 作業「ログを1つにまとめて(--squash)」マージ（途中のミスを消す）
git merge --squash feature/xxxx

# mainに確定ログを記録（ルールに沿ったメッセージ）
git commit -m "feat: 〇〇機能を追加"

# リモートへ反映
git push origin HEAD
```

### ■ 4. 不要ブランチ削除
```bash
# 役割を終えたブランチを削除
git branch -d feature/xxxx

# 現在のブランチ状態を確認
git branch
```

---

## 📂 リポジトリ一覧

| 大カテゴリ | 中カテゴリ | 小カテゴリ         | リポジトリ名                                                       | 内容                        |
| :--------- | :--------- | :----------------- | :----------------------------------------------------------------- | :-------------------------- |
| **ユニット** | **言語** | **C++**          | [unit-lang-cpp](https://github.com/kaz-it-log/unit-lang-cpp)       | C++のCUIやWin32APIなど。    |
| **ユニット** | **言語** | **C#**           | [unit-lang-cs](https://github.com/kaz-it-log/unit-lang-cs)         | C#のCUIやWindows Formなど。 |
| **ユニット** | **言語** | **Java**         | [unit-lang-java](https://github.com/kaz-it-log/unit-lang-java)     | JavaのCUIやJavaEEなど。     |
| **ユニット** | **言語** | **Go**           | [unit-lang-go](https://github.com/kaz-it-log/unit-lang-go)         | GoのCUIなど。               |
| **ユニット** | **言語** | **Rust**         | [unit-lang-rust](https://github.com/kaz-it-log/unit-lang-rust)     | RustのCUIなど。             |
| **ユニット** | **言語** | **Python**       | [unit-lang-python](https://github.com/kaz-it-log/unit-lang-python) | PythonのCUIやPysideなど。   |
| **ユニット** | **言語** | **PHP**           | [unit-lang-php](https://github.com/kaz-it-log/unit-lang-php)      | PHPのCUIなど。              |
| **ユニット** | **言語** | **JavaScript**   | [unit-lang-js](https://github.com/kaz-it-log/unit-lang-js)         | JavaScriptのCUIやGUIなど。 |
| **ユニット** | **言語** | **TypeScript**   | [unit-lang-ts](https://github.com/kaz-it-log/unit-lang-ts)         | TypeScriptのCUIやGUIなど。 |
| **ユニット** | **言語** | **Dart**          | [unit-lang-dart](https://github.com/kaz-it-log/unit-lang-dart)     | DartのCUIやFlutterなど。   |
| **ユニット** | **言語** | **Front**         | [unit-lang-front](https://github.com/kaz-it-log/unit-lang-front)   | FrontのHTMLやCSSなど。     |
| **ユニット** | **DB** | **Oracle**          | [unit-db-oracle](https://github.com/kaz-it-log/unit-db-oracle)     | OracleのDDLやDMLなど。     |
| **ユニット** | **DB** | **MySQL**           | [unit-db-mysql](https://github.com/kaz-it-log/unit-db-mysql)       | MySQLのDDLやDMLなど。      |
| **ユニット** | **DB** | **PostgreSQL**     | [unit-db-postgres](https://github.com/kaz-it-log/unit-db-postgres) | PostgreSQLのDDLやDMLなど。  |
| **ユニット** | **DB** | **SQLite**         | [unit-db-sqlite](https://github.com/kaz-it-log/unit-db-sqlite)     | SQLiteのDDLやDMLなど。      |

---

## 📂 リポジトリの命名規則
上記リポジトリ一覧の大カテゴリ、中カテゴリは全リポジトリで共通にしています。<br>
リポジトリ名は、以下の括弧の中の英字を使っています。

### 1. 大カテゴリ
- **ユニット (unit)** : 単体で完結する機能、コマンド

[//]: # (フロー flow : 複数の部品をつなぐ一連の処理フロー)

### 2. 中カテゴリ
- **言語 (lang)** : C#, Java, etc...

[//]: # (os OS : Linux, Windows, etc...)
[//]: # (virtual 仮想化 : Docker, WSL2, etc...)
[//]: # (db DB : PostgreSQL, SQLite, etc...)
[//]: # (service サービス : Jenkins, Tomcat, etc...)
[//]: # (other その他 : 環境構築, 文書ツール, etc...)

---

## 📫 連絡先
- **サイト:** [ItoLog（https://itolog.moo.jp/）]
- **得意分野:** C# / Java / システム設計
