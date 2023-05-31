# Laravel-api-example

## インストール

1. リポジトリをクローンする: `git clone https://github.com/IESKA2KHobbyLink/Laravel-api-exmple.git`
2. 必要なパッケージをインストールする: `composer install`
3. .env.example ファイルを.env にコピーして、データベースの認証情報を更新する
4. MySQL は autocommit (自動コミットモード)を無効化する方は　 autocommit を設定してください。
5. アプリケーションキーを生成する: `php artisan key:generate`
6. データベースマイグレーションを実行する: `php artisan migrate`
7. 開発用サーバーを起動する: `php artisan serve`

## Routings
```
GET /api/users: すべてのユーザーを取得する
GET /api/users/{id}: ユーザーをIDで取得する
POST /api/users: ユーザー制作
PUT /api/users/{id}: IDでユーザーの情報を更新
DELETE /api/users/{id}: IDでユーザー削除する
```
## 使い方
例：ブラウザで　GET リクエスト`http://localhost:8000` 
```
{"Laravel":"10.12.0"}
```
GET リクエストはブラウザでできるけど　POST PUT DELETE は　[Postman](https://www.postman.com/),CURL を使ってください。

例: Curl でPOST   
```
curl -X POST -d "name=user01&email=user01@email.com&password=password" http://localhost:8000/api/users/
```
戻り値
```
{
"name":"user01",
"email":"user01@email.com",
"updated_at":"2023-05-31T04:47:37.000000Z",
"created_at":"2023-05-31T04:47:37.000000Z",
"id":1
}
```
IDで確認
```
curl http//localhost:8000/api/1
```

戻り値
```
{
"id":1,
"name":"user01",
"email":"user01@email.com",
"email_verified_at":null,
"created_at":"2023-05-31T04:47:37.000000Z",
"updated_at":"2023-05-31T04:47:37.000000Z"
}
```
