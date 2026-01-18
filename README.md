# Dockerコンテナをビルドして起動

docker-compose up -d --build

# Laravelプロジェクトを作成 (srcが空の場合)

docker-compose exec php composer create-project "laravel/laravel=12.\*" .

# LaravelとBreezeをインストール

~~docker-compose exec php composer require laravel/breeze --dev~~
~~docker-compose exec php php artisan breeze:install vue~~

# 依存関係のインストールと初期設定

docker-compose exec php npm install
docker-compose exec php php artisan key:generate
docker-compose exec php php artisan migrate

# Laravel画面表示

http://localhost:8080

# ２回目以降のdockerコンテナ起動

# Fortify パッケージをインストール

docker-compose exec php composer require laravel/fortify
docker-compose exec php php artisan fortify:install
docker-compose exec php php artisan migrate
