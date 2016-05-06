# laravel

## インストール手順

1. cygwinをインストール
2. cygwinの/binに相当するディレクトリのパスと通す
   - C:\cygwinにインストールした場合は、C:\cygwin\bin
3. vagrantとVirtualBoxのインストール
4. git clone https://github.com/kazuman-com/laravel.git
5. vagrant up
6. コンテナ起動
   - cd /home/vagrant/sync
   - dc up -d
7. phpコンテナに入る
   - ターミナル上で「php」と入力
8. cd /var/www/laravel
9. cp -p .env.example .env
   - DBの接続情報などを修正（後で修正でもOK）
10. composer install
11. chmod -R www-data:www-data /var/www/laravel/storage
12. chmod -R www-data:www-data /var/www/laravel/bootstrap/cache

## トラブルシューティング

* The cipher and / or key length are invalid
   - 以下コマンドでキーを再生成
      - php artisan key:generate