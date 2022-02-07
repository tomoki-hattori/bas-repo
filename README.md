# BAS

## 使用用途

BAS での環境構築に用いる

## 各 ver

- nginx:latest
- php:latest
- mysql:latest
- minio:latest
- mailhog:latest

## 環境構築手順

0. $ pwd で bas フォルダにいるか確認
1. docker-compose up -d
2. docker-compose exec php bash
3. composer create-project laravel/laravel bas-app ※フォルダ名:bas-app 固定
4. cd bas-app で laravel フォルダに移動
5. php artisan key:generate
6. chmod -R 777 laravel/storage
7. .env ファイル変更（.env ファイルが無ければ「cp .env .env.sample」）

```
DB_CONNECTION=mysql
DB_HOST=bas-mysql
DB_PORT=3306
DB_DATABASE=bas
DB_USERNAME=bas_user
DB_PASSWORD=bas_password
```

8. php artisan migrate で実行成功するか確認
9. localhost:8080/
10. localhost:8025/
11. localhost:9001/　の表示確認
12. mysql コンテナに入って接続確認
