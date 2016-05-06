# laravel

## インストール手順

1. cygwinをインストール
2. cygwinの/binに相当するディレクトリのパスと通す
   - C:\cygwinにインストールした場合は、C:\cygwin\bin
3. vagrantとVirtualBoxのインストール
4. git clone https://github.com/kazuman-com/laravel.git
5. vagrant up
6. ターミナルで「php」と入力
7. cd /var/www/laravel
8. cp -p .env.example .env
9. composer install
10. chmod -R www-data:www-data /var/www/laravel/storage
11. chmod -R www-data:www-data /var/www/laravel/bootstrap/cache

## トラブルシューティング

* The cipher and / or key length are invalid
   - 以下コマンドでキーを再生成
      - php artisan key:generate